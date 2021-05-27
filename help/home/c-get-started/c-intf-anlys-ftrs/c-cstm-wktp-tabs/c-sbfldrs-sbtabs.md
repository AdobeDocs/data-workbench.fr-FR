---
description: Par défaut, les onglets nouvellement créés affichent les sous-dossiers du répertoire associé sous la forme de sous-répertoires hiérarchiques et déroulants au lieu de sous-onglets.
title: Afficher les sous-dossiers comme sous-onglets
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Afficher les sous-dossiers comme sous-onglets{#display-subfolders-as-subtabs}

Par défaut, les onglets nouvellement créés affichent les sous-dossiers du répertoire associé sous la forme de sous-répertoires hiérarchiques et déroulants au lieu de sous-onglets.

Vous pouvez afficher les sous-dossiers sous forme de sous-onglets (comme illustré dans l’exemple suivant) en plaçant un fichier [!DNL empty folder.useTabs] dans le *nom du profil de travail*\Workspaces\*dossier du nom de l’onglet* du répertoire d’installation du Data Workbench.

L’exemple suivant illustre l’onglet [!DNL Custom] avec des sous-répertoires de liste déroulante.

![](assets/client-sub.png)

Si vous placez un fichier [!DNL empty folder.useTabs] dans le dossier Espaces de travail\Personnalisés , tous les sous-dossiers du dossier personnalisé s’affichent sous la forme de sous-onglets dans le dossier [!DNL Worktop], comme illustré dans l’exemple suivant :

![](assets/client-sub2.png)

**Pour afficher des sous-dossiers sous forme de sous-onglets dans la[!DNL Worktop]**

>[!NOTE]
>
>Chaque niveau de répertoire doit comporter un fichier [!DNL Tab Name.useTabs] pour que le contenu du sous-dossier s’affiche sous forme de sous-onglets au lieu de sous-répertoires hiérarchiques déroulants.

1. Dans la balise [!DNL Profile Manager], cliquez sur **[!UICONTROL Workspaces]** pour en visualiser le contenu.
1. Dans la colonne *nom du profil de travail* , cliquez avec le bouton droit de la souris sur la coche de l’un des fichiers [!DNL folder.useTabs] et cliquez sur **[!UICONTROL Copy]**.
1. Cliquez avec le bouton droit de la souris dans la colonne [!DNL User] du dossier Workspaces\*tab name* et cliquez sur **[!UICONTROL Paste]**. Les sous-dossiers de cet onglet s’affichent désormais sous forme de sous-onglets.
1. (Facultatif) Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche blanche du fichier [!DNL new folder.useTabs] dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Save to]** > &lt; &lt;a3/&quot;.**[!UICONTROL working profile name]**
