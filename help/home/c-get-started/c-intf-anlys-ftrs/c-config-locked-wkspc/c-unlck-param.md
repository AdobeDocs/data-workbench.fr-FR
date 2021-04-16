---
description: Le paramètre Déverrouiller dans le fichier Insight.cfg d’un utilisateur indique s’il est autorisé à déverrouiller temporairement les espaces de travail verrouillés pour modification.
title: Définir le paramètre de déverrouillage
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# Définir le paramètre de déverrouillage{#set-the-unlock-parameter}

Le paramètre Déverrouiller dans le fichier Insight.cfg d’un utilisateur indique s’il est autorisé à déverrouiller temporairement les espaces de travail verrouillés pour modification.

Si le paramètre Unlock figure déjà dans le fichier [!DNL Insight.cfg] de l’utilisateur, vous pouvez le modifier à l’aide du Data Workbench. S’il n’est pas déjà présent dans le fichier [!DNL Insight.cfg] de l’utilisateur, vous devez l’ajouter au fichier à l’aide d’un éditeur de texte, tel que le Bloc-notes.

**Pour définir un  [!DNL Unlock] paramètre existant dans le fichier Insight.cfg**

1. Dans un espace de travail, cliquez avec le bouton droit de la souris sur **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. Le fichier [!DNL Insight.cfg] s&#39;ouvre.
1. Pour le paramètre Déverrouiller, saisissez true ou false. True permet à l&#39;utilisateur de déverrouiller temporairement tout espace de travail verrouillé, contrairement à False.
1. Pour enregistrer vos modifications de configuration, cliquez avec le bouton droit de la souris sur **[!UICONTROL Insight.cfg (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save as Insight.cfg]**.

**Pour ajouter le paramètre Déverrouiller au fichier Insight.cfg**

1. Accédez au répertoire d’installation du Data Workbench et ouvrez le fichier [!DNL Insight.cfg] à l’aide d’un éditeur de texte, tel que le Bloc-notes.
1. Ajoutez le paramètre Déverrouiller à la fin du fichier, comme dans l&#39;exemple suivant :

[!DNL Unlock = bool: false]

1. Définissez la valeur sur true ou false. True permet à l&#39;utilisateur de déverrouiller temporairement tout espace de travail verrouillé, contrairement à False.
1. Enregistrez et fermez le fichier.
