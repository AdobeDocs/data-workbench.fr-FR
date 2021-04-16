---
description: Lorsque vous configurez un profil de jeux de données pour qu’il s’exécute sur une grappe de serveurs Insight, tous les ordinateurs de la grappe partagent tous les fichiers de configuration de jeux de données pour ce profil.
title: Configuration d’un profil à exécuter sur un cluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# Configuration d’un profil à exécuter sur un cluster{#configuring-a-profile-to-run-on-a-cluster}

Lorsque vous configurez un profil de jeux de données pour qu’il s’exécute sur une grappe de serveurs Insight, tous les ordinateurs de la grappe partagent tous les fichiers de configuration de jeux de données pour ce profil.

Par conséquent, les entrées des paramètres de ces fichiers doivent s&#39;appliquer à tous les éléments [!DNL Insight Servers] de la grappe. Par exemple, les emplacements des fichiers journaux à lire, les fichiers de recherche à utiliser par [!DNL Insight Server] et l&#39;emplacement de la sortie des données par [!DNL Insight Server] doivent être identiques sur tous les ordinateurs de la grappe.

Vous effectuez toutes les tâches de configuration sur le fichier maître [!DNL Insight Server] de la grappe, c’est-à-dire [!DNL Insight Server] que vous utilisez pour modifier vos fichiers de configuration. Toutes les modifications de fichier de configuration enregistrées effectuées sur le fichier maître [!DNL Insight Server] sont automatiquement synchronisées avec les fichiers du traitement [!DNL Insight Servers] de la grappe.

Pour exécuter un profil de jeux de données sur une grappe [!DNL Insight Server], vous devez exécuter les processus suivants dans l&#39;ordre indiqué :

1. [Détermination des serveurs Insight qui traitent les données de Événement](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Spécification des serveurs de traitement dans Profil.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Si nécessaire) [Modification des fichiers de configuration des jeux de données pour le Profil](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Détermination des serveurs Insight qui traitent les données de Événement {#section-59b8e3f2b34f49739d544c8740a62fba}

Il n’est pas nécessaire que toutes les [!DNL Insight Servers] des données du événement de processus du cluster soient traitées. Vous pouvez désigner un [!DNL Insight Server] de la grappe comme unité de serveur de fichiers qui stocke les fichiers source (fichiers VSL et journaux) et les diffuse dans toutes les unités de traitement des données (serveurs de traitement) de la grappe. Cette configuration permet de bénéficier d’un référentiel de données à événement unique et de tirer parti de la puissance de traitement de tous les serveurs de traitement de la grappe. Les serveurs de traitement divisent les fichiers de données entre eux et garantissent que le même fichier n’est pas traité plusieurs fois.

Pour plus d&#39;informations sur la désignation d&#39;une [!DNL Insight Server] à exécuter en tant qu&#39;unité de serveur de fichiers, consultez le chapitre Fichier de configuration de traitement des fichiers journaux du *Guide de configuration des jeux de données*.

Si vous décidez de stocker les fichiers de données source sur chacun des serveurs de traitement plutôt que sur une seule unité de serveur de fichiers, vous devez répartir les fichiers de manière égale entre les serveurs de traitement. Ne stockez pas tous les fichiers source du jeu de données sur chacun des serveurs de traitement. Si plusieurs copies d’un même fichier sont disponibles pour plusieurs serveurs de traitement, les données sont lues plusieurs fois (une fois par ordinateur) et faussent vos données.

Pour savoir comment [!DNL Insight Servers] traiter les fichiers journaux, veuillez contacter Adobe Consulting.

## Spécification des serveurs de traitement dans Profil.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

Dans le fichier [!DNL profile.cfg], spécifiez les serveurs de traitement qui traitent les données pour le profil.

**Pour accéder au fichier profil.cfg**

Vous accédez au fichier de configuration du profil en utilisant [!DNL Profile Manager] dans [!DNL Insight].

1. Lorsque vous travaillez dans votre profil de jeux de données, ouvrez [!DNL Profile Manager] en cliquant avec le bouton droit dans un espace de travail et en cliquant sur **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**, ou en ouvrant l&#39;espace de travail Gestion de Profils dans l&#39;onglet [!DNL Admin].

1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].

1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La fenêtre de configuration du profil s&#39;affiche.

**Pour ajouter des serveurs de traitement**

1. Dans le fichier [!DNL profile.cfg], cliquez sur **[!UICONTROL Profile]**, puis sur **[!UICONTROL Processing Servers]** pour afficher son contenu.

1. Cliquez avec le bouton droit **[!UICONTROL Processing Servers]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. Dans le paramètre Common Name, saisissez le nom commun du premier serveur de traitement de la grappe. Par exemple : [!DNL server1.mycompany.com]
1. Répétez les étapes 2 et 3 jusqu’à ce que vous ayez ajouté les noms communs de tous les serveurs de traitement de la grappe.

   >[!NOTE]
   >
   >Si le maître [!DNL Insight Server] traite les données, vous devez l’ajouter également.

1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

1. Cliquez avec le bouton droit de la souris sur la coche de la colonne [!DNL User] en regard de [!DNL profile.cfg]. Cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Modification des fichiers de configuration des jeux de données pour le Profil {#section-99bf9248e4e5483cb518f453b0a2f278}

**Pour modifier les fichiers de configuration du jeu de données**

Si vous devez apporter des modifications aux fichiers de configuration du jeu de données ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], le jeu de données inclut des fichiers, [!DNL Log Processing Mode.cfg], etc.), effectuez-le uniquement sur le fichier maître [!DNL Insight Server].

1. Accédez aux fichiers à modifier :

   Pour obtenir des instructions sur l&#39;accès aux fichiers, consultez le *Guide de configuration des jeux de données*.
1. Effectuez vos modifications. Consultez le *Guide de configuration des jeux de données* pour plus d&#39;informations sur les paramètres des fichiers de configuration.
1. Enregistrez le fichier.

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Cliquez avec le bouton droit de la souris sur la coche de la colonne [!DNL User] en regard du nom de fichier.
   1. Cliquez sur **[!UICONTROL Save to]** et sélectionnez le profil de votre choix.

>[!NOTE]
>
>[!DNL Insight] les utilisateurs qui accèdent à un profil de jeux de données s’exécutant sur une grappe identifient uniquement le maître  [!DNL Insight Server] dans le fichier de  [!DNL Insight] configuration (  [!DNL insight.cfg]). Du point de vue de l&#39;utilisateur [!DNL Insight], le profil n&#39;est accessible que sur un [!DNL Insight Server] (le maître [!DNL Insight Server]); toutefois, les demandes de requête des analystes peuvent être adressées à n&#39;importe quel [!DNL Insight Servers] de la grappe.

Un cluster [!DNL Insight Server] permet l&#39;enregistrement centralisé des fichiers journaux [!DNL .vsl] (à partir de [!DNL Sensor]) sur une seule machine [!DNL Insight Server] appelée Unité de serveur de fichiers (FSU). Pour plus d’informations sur l’installation d’un FSU, voir [Procédures d’installation d’un FSU de serveur Insight](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). Pour plus d&#39;informations sur la configuration d&#39;un FSU, consultez le *Guide de configuration des jeux de données*.
