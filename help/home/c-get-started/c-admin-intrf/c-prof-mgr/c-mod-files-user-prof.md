---
description: Vous pouvez utiliser le Gestionnaire de profils pour télécharger les fichiers que vous souhaitez modifier.
title: Modifier des fichiers locaux dans le profil d’utilisateur
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
exl-id: 187d67a1-e436-4bfd-87ad-17b6c70dbee4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# Modifier des fichiers locaux dans le profil d’utilisateur{#modify-local-files-in-the-user-profile}

{{eol}}

Vous pouvez utiliser le Gestionnaire de profils pour télécharger les fichiers que vous souhaitez modifier.

Vous pouvez télécharger un fichier pour remplacer votre fichier local existant par la version d’origine du fichier ou ouvrir, afficher et modifier des fichiers inaccessibles à partir des menus de l’espace de travail.

**Pour télécharger un fichier**

1. Dans le [!DNL Profile Manager], ouvrez les dossiers et sous-dossiers nécessaires pour localiser le fichier à télécharger.
1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom du fichier, puis cliquez sur **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Configuration ( [!DNL .cfg]), dimension ( [!DNL .dim]), et la mesure ( [!DNL .metric]) peuvent être modifiés directement dans un dossier de profil et enregistrés sur le serveur sans les rendre locales ni les enregistrer séparément sur le serveur. Il vous suffit de cliquer avec le bouton droit de la souris sur la coche en regard du nom du fichier, puis de cliquer sur **[!UICONTROL Open]** > **dans la station de travail**.

Une fois le fichier téléchargé sur l’ordinateur local, une coche s’affiche dans la variable [!DNL User] qui indique qu’une copie locale du fichier réside dans le dossier User\*profile name* de votre ordinateur. Notez que la coche est de la même couleur que celle de la *nom du profil* colonne . Cela indique que le fichier local a la même date et heure de modification que le fichier dans la variable *nom du profil* dossier.

**Modification du fichier**

1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom du fichier dans la [!DNL User] colonne .
1. Cliquez sur l’une des options de menu suivantes, selon la manière dont vous souhaitez modifier le fichier :

   * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** si vous modifiez une [!DNL .vw] ou un [!DNL .cfg] dans un espace de travail.

   * **Ouvrir** > **dans vw. Éditeur **si vous modifiez un fichier .vw pour ajouter de nouveaux paramètres.

   * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** si vous ouvrez un fichier texte ou devez ajouter de nouveaux paramètres à une [!DNL .cfg] fichier .

   * **[!UICONTROL Open]** > **[!UICONTROL folder]** si vous souhaitez ouvrir le dossier dans lequel se trouve le fichier sur votre ordinateur.

1. Modifiez le fichier selon vos besoins, puis enregistrez-le.

Dans le [!DNL Profile Manager], notez que la coche dans la variable [!DNL User] a modifié la couleur du fichier que vous avez modifié. Cela indique que le fichier local est désormais différent de la version de la variable *nom du profil* dossier. Si nécessaire, vous pouvez publier la version révisée du fichier sur le profil afin qu’il soit utilisé par d’autres utilisateurs travaillant avec ce profil.
