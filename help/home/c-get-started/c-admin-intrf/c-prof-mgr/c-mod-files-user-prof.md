---
description: Vous pouvez utiliser le Gestionnaire de Profils pour télécharger les fichiers à modifier.
title: Modifier des fichiers locaux dans le profil d’utilisateur
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
exl-id: 187d67a1-e436-4bfd-87ad-17b6c70dbee4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# Modifier des fichiers locaux dans le profil d’utilisateur{#modify-local-files-in-the-user-profile}

Vous pouvez utiliser le Gestionnaire de Profils pour télécharger les fichiers à modifier.

Vous pouvez télécharger un fichier pour remplacer votre fichier local existant par la version originale du fichier ou ouvrir, vue et modifier des fichiers inaccessibles à partir des menus de l&#39;espace de travail.

**Pour télécharger un fichier**

1. Dans [!DNL Profile Manager], ouvrez les dossiers et sous-dossiers nécessaires pour localiser le fichier à télécharger.
1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom du fichier et cliquez sur **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Les fichiers de configuration ( [!DNL .cfg]), de dimension ( [!DNL .dim]) et de mesure ( [!DNL .metric]) peuvent être modifiés directement dans un dossier de profil et enregistrés sur le serveur sans les rendre locaux et les enregistrer séparément sur le serveur. Il vous suffit de cliquer avec le bouton droit de la souris sur la coche en regard du nom du fichier et de cliquer sur **[!UICONTROL Open]** > **dans la station de travail**.

Une fois le fichier téléchargé sur l&#39;ordinateur local, une coche apparaît dans la colonne [!DNL User], ce qui indique qu&#39;une copie locale du fichier réside dans le dossier User\*profil name* de votre ordinateur. Notez que la coche est de la même couleur que la coche dans la colonne *nom du profil*. Cela indique que le fichier local a la même date et heure modifiées que le fichier dans le dossier *nom du profil*.

**Pour modifier le fichier**

1. Cliquez avec le bouton droit de la souris sur la coche située en regard du nom de fichier dans la colonne [!DNL User].
1. Cliquez sur l’une des options de menu suivantes, selon la manière dont vous souhaitez modifier le fichier :

   * **[!UICONTROL Open]** >  **[!UICONTROL in workstation]** si vous modifiez un  [!DNL .vw] fichier ou un  [!DNL .cfg] fichier dans un espace de travail.

   * **Ouvrir** > **in vw. Editeur **si vous modifiez un fichier .vw pour ajouter de nouveaux paramètres.

   * **[!UICONTROL Open]** >  **[!UICONTROL In Notepad]** si vous ouvrez un fichier texte ou devez ajouter de nouveaux paramètres à un  [!DNL .cfg] fichier.

   * **[!UICONTROL Open]** >  **[!UICONTROL folder]** si vous souhaitez ouvrir le dossier contenant le fichier sur votre ordinateur

1. Modifiez le fichier selon vos besoins, puis enregistrez-le.

Dans le [!DNL Profile Manager], notez que la coche de la colonne [!DNL User] du fichier que vous avez modifié a changé de couleur. Cela indique que le fichier local est désormais différent de la version du dossier *nom du profil*. Si nécessaire, vous pouvez publier la version révisée du fichier sur le profil pour l’utiliser par d’autres utilisateurs travaillant avec ce profil.
