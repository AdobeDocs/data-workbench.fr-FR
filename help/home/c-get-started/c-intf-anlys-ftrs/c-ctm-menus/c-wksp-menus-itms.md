---
description: Ces étapes s’appliquent uniquement à la création de sous-menus et d’éléments de menu pour le menu Fenêtre de l’espace de travail.
title: Créer un menu d’espace de travail et un élément de menu
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 3%

---

# Créer un menu d’espace de travail et un élément de menu{#create-a-workspace-menu-and-menu-item}

Ces étapes s’appliquent uniquement à la création de sous-menus et d’éléments de menu pour le menu Fenêtre de l’espace de travail.

Vous pouvez personnaliser les menus de mesure et de dimension en créant des dossiers et de nouvelles mesures et dimensions dérivées. Pour plus d’informations, voir [Création et modification de mesures dérivées](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) et [Création et modification de Dimensions dérivées](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**Pour créer un menu de fenêtre d’espace de travail**

1. Dans le répertoire [!DNL Profile Manager], cliquez sur **[!UICONTROL Menu]** pour en visualiser le contenu.
1. Dans la colonne [!DNL User] du répertoire des menus, cliquez sur **[!UICONTROL Create]** > **[!UICONTROL Folder]**. Un dossier nommé New Folder apparaît dans la colonne [!DNL File] pour [!DNL Menu].

   >[!NOTE]
   >
   >Vous pouvez également créer un dossier pour n’importe quel sous-répertoire du répertoire Menu.

1. Renommez le nouveau dossier en cliquant avec le bouton droit de la souris dans la colonne [!DNL User] du dossier et en saisissant le nouveau nom dans le paramètre Dir.
1. Ajoutez les fichiers de votre choix au nouveau dossier.
1. (Facultatif) Dans la colonne [!DNL User] du nouveau dossier, cliquez sur **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   Un fichier [!DNL order.txt] apparaît dans la colonne [!DNL File] du nouveau dossier, et une coche pour le nouveau fichier apparaît dans la colonne [!DNL User].

1. (Facultatif) Modifiez le fichier [!DNL order.txt] si nécessaire. Voir [Personnalisation des menus à l’aide des fichiers Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Facultatif) Pour mettre les modifications à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit sur la coche blanche du dossier dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]***.

**Pour ajouter un nouvel élément de menu à un menu existant**

1. Effectuez l’une des étapes suivantes :

   * Créez un élément (visualisation, annotation, etc.) à ajouter à un menu :

      1. Ouvrez un espace de travail dans Data Workbench et créez l’élément de votre choix.
      1. Enregistrez l’élément dans le répertoire suivant :

         *Répertoire d’installation de Data Workbench*\User\*nom du profil de travail*\Work

      1. Dans le répertoire [!DNL Profile Manager], cliquez sur **[!UICONTROL Work]** pour en visualiser le contenu.
      1. Dans la colonne [!DNL User] , cliquez avec le bouton droit de la souris sur la coche du fichier souhaité, puis cliquez sur **[!UICONTROL Copy]**.
      1. Dans la colonne [!DNL User] du dossier souhaité, cliquez sur **[!UICONTROL Paste]**.

         Une copie du fichier apparaît dans la colonne [!DNL File] du nouveau dossier, et une coche pour le nouveau fichier apparaît dans la colonne [!DNL User].
   * Copiez et collez un élément existant d’un menu (dossier) vers un autre :

      1. Dans le répertoire [!DNL Profile Manager], cliquez sur **[!UICONTROL Menu]** pour en visualiser le contenu.
      1. Dans la colonne *nom du profil de travail* , cliquez avec le bouton droit de la souris sur la coche du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**.
      1. Cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Copy]**.
      1. Dans la colonne [!DNL User] du dossier souhaité, cliquez sur **[!UICONTROL Paste]**. Une copie du fichier apparaît dans la colonne [!DNL File] du nouveau dossier, et une coche pour le nouveau fichier apparaît dans la colonne [!DNL User].


1. (Facultatif) Modifiez le fichier [!DNL order.txt] si nécessaire. Voir [Personnalisation des menus à l’aide des fichiers Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Facultatif) Pour mettre les modifications à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche blanche pour chaque fichier dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
1. (Facultatif) Pour éviter qu’un élément de menu n’apparaisse dans plusieurs menus, vous devez supprimer le fichier correspondant de son dossier d’origine en cliquant avec le bouton droit de la souris sur la coche du fichier dans la colonne *nom du profil de travail* et en cliquant sur **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Répétez cette étape pour la coche du fichier dans la colonne [!DNL User].
