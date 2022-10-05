---
description: Le paramètre Déverrouiller dans le fichier Insight.cfg d’un utilisateur indique si cet utilisateur est autorisé à déverrouiller temporairement des espaces de travail pour modification.
title: Définir le paramètre de déverrouillage
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# Définir le paramètre de déverrouillage{#set-the-unlock-parameter}

{{eol}}

Le paramètre Déverrouiller dans le fichier Insight.cfg d’un utilisateur indique si cet utilisateur est autorisé à déverrouiller temporairement des espaces de travail pour modification.

Si le paramètre Déverrouiller est déjà présent dans le [!DNL Insight.cfg] , vous pouvez modifier le paramètre à l’aide de Data Workbench. S’il n’est pas déjà présent dans le [!DNL Insight.cfg] , vous devez l’ajouter au fichier à l’aide d’un éditeur de texte, tel que le Bloc-notes.

**Pour définir une [!DNL Unlock] dans le fichier Insight.cfg**

1. Dans un espace de travail, cliquez avec le bouton droit de la souris **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. Le [!DNL Insight.cfg] s’ouvre.
1. Pour le paramètre Déverrouiller , saisissez true ou false. True permet à l’utilisateur de déverrouiller temporairement un espace de travail verrouillé, contrairement à false.
1. Pour enregistrer les modifications apportées à la configuration, cliquez avec le bouton droit de la souris **[!UICONTROL Insight.cfg (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save as Insight.cfg]**.

**Ajout du paramètre Déverrouiller au fichier Insight.cfg**

1. Accédez au répertoire d’installation de votre Data Workbench et ouvrez le [!DNL Insight.cfg] à l’aide d’un éditeur de texte, tel que le Bloc-notes.
1. Ajoutez le paramètre Déverrouiller à la fin du fichier, comme dans l’exemple suivant :

[!DNL Unlock = bool: false]

1. Définissez la valeur sur true ou false. True permet à l’utilisateur de déverrouiller temporairement un espace de travail verrouillé, contrairement à false.
1. Enregistrez le fichier, puis fermez-le.
