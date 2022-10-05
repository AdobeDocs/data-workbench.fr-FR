---
description: Le Gestionnaire de fichiers du serveur affiche tous les répertoires du répertoire d’installation du serveur de Data Workbench, y compris les fichiers de configuration et de recherche.
title: Créer un gestionnaire de fichiers de serveur
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# Créer un gestionnaire de fichiers de serveur{#create-a-server-files-manager}

{{eol}}

Le Gestionnaire de fichiers du serveur affiche tous les répertoires du répertoire d’installation du serveur de Data Workbench, y compris les fichiers de configuration et de recherche.

Vous pouvez accéder à une partie de la variable [!DNL Server Files Manager] sans avoir à parcourir l’ensemble de sa structure de répertoires ni à afficher seulement quelques sous-répertoires pour répondre à un besoin particulier. Par exemple, vous pouvez créer un [!DNL Server Files Manager] qui affiche uniquement les sous-répertoires Access Control et Users , ce qui vous permet de gérer vos utilisateurs et leur accès.

Chaque gestionnaire que vous créez doit comporter une [!DNL .vw] fichier . Vous pouvez utiliser la variable [!DNL Server Files.vw] comme modèle.

Pour plus d’informations sur la variable [!DNL Server Files Manager], voir [Gestionnaire des fichiers serveur](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**Pour créer un gestionnaire de fichiers de serveur**

1. Dans le [!DNL Profile Manager], cliquez sur le bouton **[!UICONTROL Menu]** , puis le **[!UICONTROL Admin]** répertoire . Le [!DNL Server Files.vw] se trouve ici.
1. Dans le *nom du profil* , cliquez avec le bouton droit de la souris sur la coche de la colonne [!DNL Server Files.vw] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour le fichier apparaît dans la variable [!DNL User] colonne .
1. Cliquez avec le bouton droit de la souris sur la coche correspondant au [!DNL Server Files.vw] dans le fichier [!DNL User] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Le [!DNL Server Files.vw] s’ouvre.
1. Pour supprimer un répertoire, cliquez avec le bouton droit de la souris sur la bordure supérieure de l’objet [!DNL Server Files Manager] et cliquez sur **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Pour ajouter un répertoire, cliquez avec le bouton droit de la souris sur la bordure supérieure de l’objet [!DNL Server Files Manager], cliquez sur **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Saisissez l’URI du répertoire dans le champ URI, puis cliquez sur **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Vous pouvez désigner plusieurs répertoires dans le champ URI. Par exemple, si vous saisissez [!DNL Profiles\Marketing\], le gestionnaire de fichiers du serveur contient le sous-répertoire Marketing, mais pas d’autre sous-répertoire dans le répertoire Profils .

1. Cliquez avec le bouton droit de la souris dans la partie supérieure de la bordure du [!DNL Server Files Manager] et cliquez sur **[!UICONTROL Save]**.
1. Pour créer un nouveau gestionnaire, modifiez le nom du fichier dans le [!DNL File Name] , puis cliquez sur **[!UICONTROL Save]**. Pour remplacer le gestionnaire existant, cliquez sur **[!UICONTROL Save]**.
1. (Facultatif) Pour mettre les modifications à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche correspondant au [!DNL .vw] dans le fichier [!DNL User] colonne .

   Ensuite, cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
