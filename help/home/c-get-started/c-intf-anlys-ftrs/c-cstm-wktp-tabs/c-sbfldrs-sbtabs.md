---
description: Par défaut, les nouveaux onglets affichent les sous-dossiers du répertoire associé sous la forme de sous-répertoires hiérarchiques et déroulants au lieu de sous-onglets.
solution: Analytics
title: Afficher les sous-dossiers sous forme de sous-onglets
topic: Data workbench
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Afficher les sous-dossiers sous forme de sous-onglets{#display-subfolders-as-subtabs}

Par défaut, les nouveaux onglets affichent les sous-dossiers du répertoire associé sous la forme de sous-répertoires hiérarchiques et déroulants au lieu de sous-onglets.

Vous pouvez afficher les sous-dossiers sous forme de sous-onglets (comme illustré dans l’exemple suivant) en plaçant un [!DNL empty folder.useTabs] fichier dans le dossier *du profil de* travail \Workspaces\*nom_onglet* du répertoire d’installation des outils de données.

L’exemple suivant illustre l’ [!DNL Custom] onglet avec des sous-répertoires déroulants.

![](assets/client-sub.png)

Si vous placez un [!DNL empty folder.useTabs] fichier dans le dossier Workspaces\Custom, tous les sous-dossiers du dossier Custom s’affichent sous la forme [!DNL Worktop] de sous-onglets, comme illustré dans l’exemple suivant :

![](assets/client-sub2.png)

**Pour afficher des sous-dossiers sous forme de sous-onglets dans le[!DNL Worktop]**

>[!NOTE]
>
>Chaque niveau de répertoire doit disposer d’un [!DNL Tab Name.useTabs] fichier pour que le contenu du sous-dossier s’affiche sous forme de sous-onglets au lieu de sous-répertoires hiérarchiques déroulants.

1. Dans la [!DNL Profile Manager], cliquez **[!UICONTROL Workspaces]** pour en afficher le contenu.
1. Dans la colonne Nom *du profil de* travail, cliquez avec le bouton droit de la souris sur la coche de l’un des [!DNL folder.useTabs] fichiers, puis cliquez sur **[!UICONTROL Copy]**.
1. Cliquez avec le bouton droit dans la [!DNL User] colonne du dossier Workspaces\*tab name*, puis cliquez sur **[!UICONTROL Paste]**. Les sous-dossiers de cet onglet s’affichent désormais sous forme de sous-onglets.
1. (Facultatif) Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche blanche du [!DNL new folder.useTabs] fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

