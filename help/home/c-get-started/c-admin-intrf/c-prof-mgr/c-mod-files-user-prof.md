---
description: Vous pouvez utiliser le Gestionnaire de profils pour télécharger les fichiers que vous souhaitez modifier.
solution: Analytics
title: Modification des fichiers locaux dans le profil utilisateur
topic: Data workbench
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modification des fichiers locaux dans le profil utilisateur{#modify-local-files-in-the-user-profile}

Vous pouvez utiliser le Gestionnaire de profils pour télécharger les fichiers que vous souhaitez modifier.

Vous pouvez télécharger un fichier pour remplacer votre fichier local existant par la version originale du fichier ou ouvrir, afficher et modifier des fichiers inaccessibles à partir des menus de l’espace de travail.

**Pour télécharger un fichier**

1. Dans la [!DNL Profile Manager]section, ouvrez les dossiers et sous-dossiers nécessaires pour localiser le fichier à télécharger.
1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom du fichier, puis cliquez sur **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Les fichiers de configuration ( [!DNL .cfg]), de dimension ( [!DNL .dim]) et de mesure ( [!DNL .metric]) peuvent être modifiés directement dans un dossier de profil et enregistrés sur le serveur sans les rendre locaux et les enregistrer séparément sur le serveur. Il vous suffit de cliquer avec le bouton droit de la souris sur la coche en regard du nom du fichier et de cliquer sur **[!UICONTROL Open]** > **dans la station de travail**.

Une fois le fichier téléchargé sur l’ordinateur local, une coche apparaît dans la [!DNL User] colonne, indiquant qu’une copie locale du fichier réside dans le dossier User\*profile name* de votre ordinateur. Notez que la coche est de la même couleur que la coche dans la colonne du nom *du* profil. Cela indique que le fichier local a la même date et heure de modification que le fichier dans le dossier du nom *du* profil.

**Pour modifier le fichier**

1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom de fichier dans la [!DNL User] colonne.
1. Cliquez sur l’une des options de menu suivantes, selon la méthode de modification du fichier :

   * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** si vous modifiez un [!DNL .vw] fichier ou un [!DNL .cfg] fichier dans un espace de travail.

   * **Ouvrez** > **in vw. Editeur **si vous modifiez un fichier .vw pour ajouter de nouveaux paramètres.

   * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** si vous ouvrez un fichier texte ou devez ajouter de nouveaux paramètres à un [!DNL .cfg] fichier.

   * **[!UICONTROL Open]** > **[!UICONTROL folder]** si vous souhaitez ouvrir le dossier contenant le fichier sur votre ordinateur

1. Modifiez le fichier suivant vos besoins, puis enregistrez-le.

Dans la [!DNL Profile Manager], notez que la coche de la [!DNL User] colonne pour le fichier que vous avez modifié a changé de couleur. Cela indique que le fichier local est désormais différent de la version dans le dossier du nom *du* profil. Si nécessaire, vous pouvez publier la version révisée du fichier dans le profil pour l’utiliser par d’autres utilisateurs travaillant avec ce profil.
