---
description: Lorsque vous configurez un profil de jeu de données pour qu’il s’exécute sur une grappe de serveurs Insight, toutes les machines de la grappe partagent tous les fichiers de configuration de jeu de données pour ce profil.
title: Configuration d’un profil à exécuter sur un cluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# Configuration d’un profil à exécuter sur un cluster{#configuring-a-profile-to-run-on-a-cluster}

{{eol}}

Lorsque vous configurez un profil de jeu de données pour qu’il s’exécute sur une grappe de serveurs Insight, toutes les machines de la grappe partagent tous les fichiers de configuration de jeu de données pour ce profil.

Par conséquent, les entrées des paramètres de ces fichiers doivent s’appliquer à tous les [!DNL Insight Servers] dans la grappe. Par exemple, les emplacements des fichiers journaux à lire, les fichiers de recherche à utiliser par [!DNL Insight Server]et l’emplacement de la sortie des données par [!DNL Insight Server] doit être identique sur toutes les machines de la grappe.

Vous effectuez toutes les tâches de configuration sur le maître de la grappe. [!DNL Insight Server], qui est la variable [!DNL Insight Server] vous utilisez pour modifier vos fichiers de configuration. Toutes les modifications du fichier de configuration enregistrées apportées au maître [!DNL Insight Server] sont synchronisés automatiquement avec les fichiers du traitement. [!DNL Insight Servers] dans la grappe.

Pour exécuter un profil de jeu de données sur un [!DNL Insight Server] , vous devez exécuter les processus suivants dans l’ordre indiqué :

1. [Détermination des serveurs Insight qui traitent les données d’événement](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Spécification des serveurs de traitement dans Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Si nécessaire) [Modification des fichiers de configuration du jeu de données pour le profil](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Détermination des serveurs Insight qui traitent les données d’événement {#section-59b8e3f2b34f49739d544c8740a62fba}

Il n’est pas nécessaire que tous les [!DNL Insight Servers] dans les données d’événement de processus de grappe. Vous pouvez en désigner une. [!DNL Insight Server] dans la grappe en tant qu’unité de serveur de fichiers qui stocke les fichiers source (fichiers VSL et journaux) et les diffuse à toutes les unités de traitement de données (serveurs de traitement) de la grappe. Cette configuration permet l’utilisation d’un seul référentiel de données d’événement et tire parti de la puissance de traitement de tous les serveurs de traitement de la grappe. Les serveurs de traitement divisent les fichiers de données entre eux et garantissent que le même fichier n’est pas traité plus d’une fois.

Pour plus d’informations sur la désignation d’un [!DNL Insight Server] pour exécuter en tant qu’unité de serveur de fichiers, reportez-vous au chapitre Fichier de configuration de traitement du journal de la section *Guide de configuration des jeux de données*.

Si vous décidez de stocker les fichiers de données sources sur chacun des serveurs de traitement plutôt que sur une seule unité de serveur de fichiers, vous devez répartir les fichiers de manière égale entre les serveurs de traitement. Ne stockez pas tous les fichiers source du jeu de données sur chacun des serveurs de traitement. Si plusieurs copies du même fichier sont disponibles pour plusieurs serveurs de traitement, les données sont lues plusieurs fois (une par chaque ordinateur) et faussent vos données.

Pour déterminer laquelle [!DNL Insight Servers] Pour traiter les fichiers journaux, contactez Adobe Consulting.

## Spécification des serveurs de traitement dans Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

Dans le [!DNL profile.cfg] , spécifiez les serveurs de traitement qui traitent les données du profil.

**Pour accéder au fichier profile.cfg**

Vous accédez au fichier de configuration du profil à l’aide du [!DNL Profile Manager] in [!DNL Insight].

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez la variable [!DNL Profile Manager] en cliquant avec le bouton droit dans un espace de travail, puis en cliquant sur **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]** ou en ouvrant l’espace de travail de la gestion des profils sur le [!DNL Admin] .

1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .

1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La fenêtre de configuration du profil s’affiche.

**Ajout des serveurs de traitement**

1. Dans le [!DNL profile.cfg] fichier, cliquez sur **[!UICONTROL Profile]**, puis cliquez sur **[!UICONTROL Processing Servers]** pour afficher son contenu.

1. Clic droit **[!UICONTROL Processing Servers]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. Dans le paramètre Common Name , saisissez le nom commun du premier serveur de traitement de la grappe. Par exemple : [!DNL server1.mycompany.com]
1. Répétez les étapes 2 et 3 jusqu’à ce que vous ayez ajouté les noms communs de tous les serveurs de traitement de la grappe.

   >[!NOTE]
   >
   >Si le maître [!DNL Insight Server] traite les données, vous devez les ajouter également.

1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

1. Cliquez avec le bouton droit de la souris sur la coche dans la [!DNL User] en regard de [!DNL profile.cfg]. Cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Modification des fichiers de configuration du jeu de données pour le profil {#section-99bf9248e4e5483cb518f453b0a2f278}

**Modification des fichiers de configuration du jeu de données**

Si vous devez apporter des modifications aux fichiers de configuration du jeu de données ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], les fichiers d’inclusion de jeux de données, [!DNL Log Processing Mode.cfg], etc.), ne le faites que sur le maître [!DNL Insight Server].

1. Accédez aux fichiers à modifier :

   Pour obtenir des instructions sur l’accès aux fichiers, voir *Guide de configuration des jeux de données*.
1. Effectuez vos modifications. Voir *Guide de configuration des jeux de données* pour plus d’informations sur les paramètres du ou des fichiers de configuration.
1. Enregistrez le fichier.

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Cliquez avec le bouton droit de la souris sur la coche dans la [!DNL User] en regard du nom du fichier.
   1. Cliquez sur **[!UICONTROL Save to]** et sélectionnez le profil souhaité.

>[!NOTE]
>
>[!DNL Insight] les utilisateurs qui accèdent à un profil de jeu de données s’exécutant sur une grappe identifient uniquement le maître [!DNL Insight Server] dans le [!DNL Insight] fichier de configuration ( [!DNL insight.cfg]). Du point de vue de la [!DNL Insight] utilisateur, le profil est accessible sur un seul [!DNL Insight Server] (le maître [!DNL Insight Server]); toutefois, les requêtes des analystes peuvent être adressées à l’un des [!DNL Insight Servers] dans la grappe.

Un [!DNL Insight Server] La grappe permet le stockage centralisé de [!DNL .vsl] fichiers journaux (depuis [!DNL Sensor]) sur une seule [!DNL Insight Server] machine appelée FSU (File Server Unit). Pour plus d’informations sur l’installation d’un FSU, voir [Procédures d’installation d’un FSU de serveur Insight](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). Pour plus d’informations sur la configuration d’un FSU, voir la section *Guide de configuration des jeux de données*.
