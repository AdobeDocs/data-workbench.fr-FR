---
description: Par défaut, les onglets nouvellement créés affichent les sous-dossiers du répertoire associé sous la forme de sous-répertoires hiérarchiques et déroulants au lieu de sous-onglets.
title: Afficher les sous-dossiers comme sous-onglets
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Afficher les sous-dossiers comme sous-onglets{#display-subfolders-as-subtabs}

{{eol}}

Par défaut, les onglets nouvellement créés affichent les sous-dossiers du répertoire associé sous la forme de sous-répertoires hiérarchiques et déroulants au lieu de sous-onglets.

Vous pouvez afficher des sous-dossiers sous forme de sous-onglets (comme illustré dans l’exemple suivant) en plaçant un [!DNL empty folder.useTabs] dans le fichier *nom du profil de travail*\Workspaces\*nom de l’onglet* dans le répertoire d’installation du Data Workbench.

L’exemple suivant illustre la variable [!DNL Custom] avec des sous-répertoires déroulants.

![](assets/client-sub.png)

Si vous placez une [!DNL empty folder.useTabs] dans le dossier Espaces de travail\Personnalisés , tous les sous-dossiers du dossier personnalisé s’affichent dans la variable [!DNL Worktop] sous forme de sous-onglets, comme illustré dans l’exemple suivant :

![](assets/client-sub2.png)

**Pour afficher des sous-dossiers sous forme de sous-onglets dans la[!DNL Worktop]**

>[!NOTE]
>
>Chaque niveau de répertoire doit avoir une [!DNL Tab Name.useTabs] pour que le contenu du sous-dossier s’affiche sous forme de sous-onglets au lieu de sous-répertoires hiérarchiques déroulants.

1. Dans le [!DNL Profile Manager], cliquez sur **[!UICONTROL Workspaces]** pour afficher son contenu.
1. Dans le *nom du profil de travail* , cliquez avec le bouton droit de la souris sur la coche de l’une des colonnes [!DNL folder.useTabs] fichiers et cliquez sur **[!UICONTROL Copy]**.
1. Cliquez avec le bouton droit de la souris dans le [!DNL User] pour le dossier Espaces de travail\*nom de l’onglet*, puis cliquez sur **[!UICONTROL Paste]**. Les sous-dossiers de cet onglet s’affichent désormais sous forme de sous-onglets.
1. (Facultatif) Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche blanche pour la variable [!DNL new folder.useTabs] dans le fichier [!DNL User] et cliquez sur **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
