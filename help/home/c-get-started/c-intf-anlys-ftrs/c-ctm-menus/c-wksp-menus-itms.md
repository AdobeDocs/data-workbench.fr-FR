---
description: Ces étapes s’appliquent uniquement à la création de sous-menus et d’éléments de menu pour le menu Fenêtre de l’espace de travail.
solution: Analytics
title: Création d’un menu et d’une option de menu pour l’espace de travail
topic: Data workbench
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Création d’un menu et d’une option de menu pour l’espace de travail{#create-a-workspace-menu-and-menu-item}

Ces étapes s’appliquent uniquement à la création de sous-menus et d’éléments de menu pour le menu Fenêtre de l’espace de travail.

Vous pouvez personnaliser les menus de mesure et de dimension en créant de nouveaux dossiers et de nouvelles mesures et dimensions dérivées. Pour plus d’informations, voir [Création et modification de mesures](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) dérivées et [Création et modification de dimensions](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93)dérivées.

**Pour créer un menu de fenêtre d&#39;espace de travail**

1. Dans [!DNL Profile Manager], cliquez sur le **[!UICONTROL Menu]** répertoire pour afficher son contenu.
1. Dans la [!DNL User] colonne du répertoire de menus, cliquez sur **[!UICONTROL Create]** > **[!UICONTROL Folder]**. Un dossier nommé Nouveau dossier apparaît dans la [!DNL File] colonne pour [!DNL Menu].

   >[!NOTE]
   >
   >Vous pouvez également créer un dossier pour n’importe quel sous-répertoire du répertoire Menu.

1. Renommez le nouveau dossier en cliquant avec le bouton droit de la souris dans la [!DNL User] colonne du dossier et en saisissant le nouveau nom dans le paramètre Dir.
1. Ajoutez les fichiers de votre choix au nouveau dossier.
1. (Facultatif) Dans la [!DNL User] colonne du nouveau dossier, cliquez sur **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   Un [!DNL order.txt] fichier apparaît dans la [!DNL File] colonne du nouveau dossier et une coche du nouveau fichier apparaît dans la [!DNL User] colonne.

1. (Facultatif) Modifiez le [!DNL order.txt] fichier suivant vos besoins. Voir [Personnalisation des menus à l’aide des fichiers](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.
1. (Facultatif) Pour rendre les modifications accessibles à tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche blanche du dossier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Pour ajouter un nouvel élément de menu à un menu existant**

1. Effectuez l’une des étapes suivantes :

   * Créez un élément (visualisation, annotation, etc.) à ajouter à un menu :

      1. Ouvrez un espace de travail dans Outils de données et créez l’élément souhaité.
      1. Enregistrez l’élément dans le répertoire suivant :

         *Répertoire* d’installation des outils de données \User\*nom du profil de travail*\Work

      1. Dans [!DNL Profile Manager], cliquez sur le **[!UICONTROL Work]** répertoire pour afficher son contenu.
      1. Dans la [!DNL User] colonne, cliquez avec le bouton droit de la souris sur la coche du fichier souhaité, puis cliquez sur **[!UICONTROL Copy]**.
      1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**.

         Une copie du fichier apparaît dans la [!DNL File] colonne du nouveau dossier et une coche du nouveau fichier apparaît dans la [!DNL User] colonne.
   * Copiez et collez un élément existant d’un menu (dossier) vers un autre :

      1. Dans [!DNL Profile Manager], cliquez sur le **[!UICONTROL Menu]** répertoire pour afficher son contenu.
      1. Dans la colonne Nom *du profil de* travail, cliquez avec le bouton droit de la souris sur la coche du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**.
      1. Cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne et cliquez sur **[!UICONTROL Copy]**.
      1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**. Une copie du fichier apparaît dans la [!DNL File] colonne du nouveau dossier et une coche du nouveau fichier apparaît dans la [!DNL User] colonne.


1. (Facultatif) Modifiez le [!DNL order.txt] fichier suivant vos besoins. Voir [Personnalisation des menus à l’aide des fichiers](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.
1. (Facultatif) Pour mettre les modifications à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche blanche pour chaque fichier de la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Facultatif) Pour éviter qu’un élément de menu apparaisse dans plusieurs menus, vous devez supprimer le fichier correspondant de son dossier d’origine en cliquant avec le bouton droit de la souris sur la coche du fichier dans la colonne du nom *du profil de* travail et en cliquant sur **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Répétez cette étape pour la coche du fichier dans la [!DNL User] colonne.

