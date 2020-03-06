---
description: Lorsque vous configurez un profil de jeu de données pour qu’il s’exécute sur une grappe de serveurs Insight, tous les ordinateurs de la grappe partagent tous les fichiers de configuration de jeu de données pour ce profil.
solution: Insight
title: Configuration d’un profil à exécuter sur une grappe
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration d’un profil à exécuter sur une grappe{#configuring-a-profile-to-run-on-a-cluster}

Lorsque vous configurez un profil de jeu de données pour qu’il s’exécute sur une grappe de serveurs Insight, tous les ordinateurs de la grappe partagent tous les fichiers de configuration de jeu de données pour ce profil.

Par conséquent, les entrées des paramètres de ces fichiers doivent s’appliquer à tous les paramètres [!DNL Insight Servers] de la grappe. Par exemple, les emplacements des fichiers journaux à lire, les fichiers de recherche à utiliser [!DNL Insight Server]et l’emplacement de la sortie des données par [!DNL Insight Server] doivent être identiques sur tous les ordinateurs de la grappe.

Vous effectuez toutes les tâches de configuration sur le maître de la grappe [!DNL Insight Server], qui est [!DNL Insight Server] utilisé pour modifier vos fichiers de configuration. Toutes les modifications apportées au fichier de configuration enregistré sur le fichier maître [!DNL Insight Server] sont automatiquement synchronisées avec les fichiers du traitement [!DNL Insight Servers] de la grappe.

Pour exécuter un profil de jeu de données sur une [!DNL Insight Server] grappe, vous devez exécuter les processus suivants dans l’ordre indiqué :

1. [Détermination des serveurs Insight qui traitent les données d’événement](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Spécification des serveurs de traitement dans Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Si nécessaire) [Modification des fichiers de configuration des jeux de données pour le profil](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Détermination des serveurs Insight qui traitent les données d’événement {#section-59b8e3f2b34f49739d544c8740a62fba}

Il n’est pas nécessaire que toutes les données [!DNL Insight Servers] de l’événement de processus de la grappe soient traitées. Vous pouvez désigner une unité [!DNL Insight Server] de serveur de fichiers de la grappe comme unité de serveur de fichiers qui stocke les fichiers source (fichiers VSL et journaux) et les diffuse dans toutes les unités de traitement des données (serveurs de traitement) de la grappe. Cette configuration offre les avantages d’un référentiel de données d’événement unique et exploite la puissance de traitement de tous les serveurs de traitement de la grappe. Les serveurs de traitement divisent les fichiers de données entre eux et garantissent que le même fichier n’est pas traité plus d’une fois.

Pour plus d’informations sur la désignation d’une unité [!DNL Insight Server] à exécuter en tant qu’unité de serveur de fichiers, voir le chapitre Fichier de configuration de traitement des journaux du Guide *de configuration des jeux de* données.

Si vous décidez de stocker les fichiers de données source sur chacun des serveurs de traitement plutôt que sur une unité de serveur de fichiers unique, vous devez répartir les fichiers de manière égale entre les serveurs de traitement. Ne stockez pas tous les fichiers source du jeu de données sur chacun des serveurs de traitement. Si plusieurs copies du même fichier sont disponibles pour plusieurs serveurs de traitement, les données sont lues plusieurs fois (une fois par ordinateur) et faussent vos données.

Pour plus d’informations sur la procédure à suivre pour [!DNL Insight Servers] traiter les fichiers journaux, contactez le service de conseil d’Adobe.

## Spécification des serveurs de traitement dans Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

Dans le [!DNL profile.cfg] fichier, spécifiez les serveurs de traitement qui traitent les données du profil.

**Pour accéder au fichier profile.cfg**

Vous accédez au fichier de configuration du profil à l’aide de la [!DNL Profile Manager] section [!DNL Insight].

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez le fichier [!DNL Profile Manager] en cliquant avec le bouton droit dans un espace de travail et en cliquant sur **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**, ou en ouvrant l’espace de travail Gestion des profils dans l’ [!DNL Admin] onglet.

1. Dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] , puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.

1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La fenêtre de configuration du profil s’affiche.

**Pour ajouter les serveurs de traitement**

1. Dans le [!DNL profile.cfg] fichier, cliquez sur **[!UICONTROL Profile]**, puis sur **[!UICONTROL Processing Servers]** pour afficher son contenu.

1. Cliquez avec le bouton droit de la souris **[!UICONTROL Processing Servers]** , puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. Dans le paramètre Common Name, saisissez le nom commun du premier serveur de traitement de la grappe. Par exemple : [!DNL server1.mycompany.com]
1. Répétez les étapes 2 et 3 jusqu’à ce que vous ayez ajouté les noms communs de tous les serveurs de traitement de la grappe.

   >[!NOTE]
   >
   >Si le maître [!DNL Insight Server] traite les données, vous devez également les ajouter.

1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

1. Cliquez avec le bouton droit de la souris sur la coche dans la [!DNL User] colonne en regard de [!DNL profile.cfg]. Cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Modification des fichiers de configuration des jeux de données pour le profil {#section-99bf9248e4e5483cb518f453b0a2f278}

**Pour modifier les fichiers de configuration du jeu de données**

Si vous devez apporter des modifications aux fichiers de configuration du jeu de données ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], le jeu de données inclut des fichiers [!DNL Log Processing Mode.cfg], etc.), effectuez-le uniquement sur le fichier maître [!DNL Insight Server].

1. Accédez aux fichiers à modifier :

   Pour obtenir des instructions sur l’accès aux fichiers, consultez le Guide *de configuration des jeux de* données.
1. Effectuez vos modifications. Consultez le Guide *de configuration des jeux de* données pour plus d’informations sur les paramètres du ou des fichiers de configuration.
1. Enregistrez le fichier.

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Cliquez avec le bouton droit de la souris sur la coche dans la [!DNL User] colonne en regard du nom de fichier.
   1. Cliquez sur **[!UICONTROL Save to]** et sélectionnez le profil souhaité.

>[!NOTE]
>
>[!DNL Insight] les utilisateurs qui accèdent à un profil de jeu de données s’exécutant sur une grappe identifient uniquement le maître [!DNL Insight Server] dans le fichier [!DNL Insight] de configuration ( [!DNL insight.cfg]). Du point de vue de l&#39; [!DNL Insight] utilisateur, le profil n&#39;est accessible que sur un [!DNL Insight Server] (le gabarit [!DNL Insight Server]); toutefois, les demandes de requête des analystes peuvent être dirigées vers n’importe quel élément de la grappe [!DNL Insight Servers] .

Une [!DNL Insight Server] grappe permet le stockage centralisé des fichiers [!DNL .vsl] journaux (depuis [!DNL Sensor]) sur une seule [!DNL Insight Server] machine appelée Unité de serveur de fichiers (FSU). Pour plus d’informations sur l’installation d’un FSU, voir [Procédure d’installation d’un FSU](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)de serveur Insight. Pour plus d’informations sur la configuration d’un FSU, consultez le Guide *de configuration des jeux de* données.
