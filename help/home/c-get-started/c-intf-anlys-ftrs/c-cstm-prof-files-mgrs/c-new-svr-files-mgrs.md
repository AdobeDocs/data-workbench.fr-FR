---
description: Le Gestionnaire de fichiers du serveur affiche tous les répertoires du répertoire d’installation du serveur Outils de données, y compris les fichiers de configuration et de recherche.
solution: Analytics
title: Création d’un gestionnaire de fichiers serveur
topic: Data workbench
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Création d’un gestionnaire de fichiers serveur{#create-a-server-files-manager}

Le Gestionnaire de fichiers du serveur affiche tous les répertoires du répertoire d’installation du serveur Outils de données, y compris les fichiers de configuration et de recherche.

Vous pouvez accéder à une partie du [!DNL Server Files Manager] répertoire sans avoir à parcourir l’intégralité de sa structure de répertoires ou afficher uniquement quelques-uns des sous-répertoires pour répondre à un besoin particulier. Par exemple, vous pouvez créer une fenêtre distincte [!DNL Server Files Manager] qui affiche uniquement les sous-répertoires Access Control et Users, ce qui vous permet de gérer vos utilisateurs et leur accès.

Chaque gestionnaire que vous créez doit avoir un [!DNL .vw] fichier. Vous pouvez utiliser le [!DNL Server Files.vw] fichier comme modèle.

Pour plus d’informations sur le [!DNL Server Files Manager], voir [Le Gestionnaire](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4)de fichiers du serveur.

**Pour créer un Gestionnaire de fichiers serveur**

1. Dans [!DNL Profile Manager], cliquez sur le **[!UICONTROL Menu]** répertoire, puis sur le **[!UICONTROL Admin]** répertoire. Le [!DNL Server Files.vw] fichier se trouve ici.
1. Dans la colonne Nom *du* profil, cliquez avec le bouton droit de la souris sur la coche du [!DNL Server Files.vw] fichier, puis cliquez sur **[!UICONTROL Make Local]**. Une coche du fichier apparaît dans la [!DNL User] colonne.
1. Cliquez avec le bouton droit de la souris sur la coche du [!DNL Server Files.vw] fichier dans la [!DNL User] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Le [!DNL Server Files.vw] fichier s&#39;ouvre.
1. Pour supprimer un répertoire, cliquez avec le bouton droit de la souris sur la bordure supérieure du répertoire [!DNL Server Files Manager] , puis cliquez sur **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Pour ajouter un répertoire, cliquez avec le bouton droit de la souris sur la bordure supérieure du [!DNL Server Files Manager], puis cliquez sur **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Tapez l’URI du répertoire dans le champ URI, puis cliquez sur **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Vous pouvez désigner plusieurs répertoires dans le champ URI. Par exemple, si vous saisissez [!DNL Profiles\Marketing\], le gestionnaire de fichiers du serveur contient le sous-répertoire Marketing, mais pas d’autre sous-répertoire dans le répertoire Profils.

1. Cliquez avec le bouton droit de la souris sur la bordure supérieure de la [!DNL Server Files Manager] zone, puis cliquez sur **[!UICONTROL Save]**.
1. Pour créer un nouveau gestionnaire, modifiez le nom du fichier dans le [!DNL File Name] champ, puis cliquez sur **[!UICONTROL Save]**. Pour remplacer le gestionnaire existant, cliquez sur **[!UICONTROL Save]**.
1. (Facultatif) Pour rendre les modifications accessibles à tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche du [!DNL .vw] fichier dans la [!DNL User] colonne.

   Ensuite, cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

