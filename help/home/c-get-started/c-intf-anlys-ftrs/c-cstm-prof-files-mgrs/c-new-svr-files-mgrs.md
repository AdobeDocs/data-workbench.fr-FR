---
description: Le Gestionnaire de fichiers du serveur affiche tous les répertoires du répertoire d’installation du serveur de Data Workbench, y compris les fichiers de configuration et de recherche.
title: Créer un gestionnaire de fichiers de serveur
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# Créer un gestionnaire de fichiers de serveur{#create-a-server-files-manager}

Le Gestionnaire de fichiers du serveur affiche tous les répertoires du répertoire d’installation du serveur de Data Workbench, y compris les fichiers de configuration et de recherche.

Vous pouvez accéder à une partie de [!DNL Server Files Manager] sans avoir à parcourir l’ensemble de sa structure de répertoires ou afficher seulement quelques-uns des sous-répertoires pour répondre à un besoin particulier. Par exemple, vous pouvez créer un [!DNL Server Files Manager] distinct qui affiche uniquement les sous-répertoires Access Control et Users , ce qui vous permet de gérer vos utilisateurs et leur accès.

Chaque gestionnaire que vous créez doit comporter un fichier [!DNL .vw]. Vous pouvez utiliser le fichier [!DNL Server Files.vw] comme modèle.

Pour plus d’informations sur [!DNL Server Files Manager], voir [Gestionnaire des fichiers serveur](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**Pour créer un gestionnaire de fichiers de serveur**

1. Dans le répertoire [!DNL Profile Manager], cliquez sur le répertoire **[!UICONTROL Menu]**, puis sur le répertoire **[!UICONTROL Admin]**. Le fichier [!DNL Server Files.vw] se trouve ici.
1. Dans la colonne *nom du profil*, cliquez avec le bouton droit de la souris sur la coche du fichier [!DNL Server Files.vw] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour le fichier apparaît dans la colonne [!DNL User].
1. Cliquez avec le bouton droit de la souris sur la coche du fichier [!DNL Server Files.vw] dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Le fichier [!DNL Server Files.vw] s’ouvre.
1. Pour supprimer un répertoire, cliquez avec le bouton droit sur la bordure supérieure de [!DNL Server Files Manager] et cliquez sur **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]***.
1. Pour ajouter un répertoire, cliquez avec le bouton droit de la souris sur la bordure supérieure de [!DNL Server Files Manager], cliquez sur **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Saisissez l’URI du répertoire dans le champ URI, puis cliquez sur **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Vous pouvez désigner plusieurs répertoires dans le champ URI. Par exemple, si vous tapez [!DNL Profiles\Marketing\], le gestionnaire de fichiers du serveur contient le sous-répertoire Marketing, mais pas d’autre sous-répertoire dans le répertoire Profils .

1. Cliquez avec le bouton droit de la souris sur la bordure supérieure de la balise [!DNL Server Files Manager] et cliquez sur **[!UICONTROL Save]**.
1. Pour créer un gestionnaire, modifiez le nom du fichier dans le champ [!DNL File Name], puis cliquez sur **[!UICONTROL Save]**. Pour remplacer le gestionnaire existant, cliquez sur **[!UICONTROL Save]**.
1. (Facultatif) Pour mettre les modifications à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit sur la coche du fichier [!DNL .vw] dans la colonne [!DNL User].

   Ensuite, cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
