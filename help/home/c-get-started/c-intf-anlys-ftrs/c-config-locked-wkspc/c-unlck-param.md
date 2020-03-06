---
description: Le paramètre Déverrouiller dans le fichier Insight.cfg d’un utilisateur indique s’il est autorisé à déverrouiller temporairement les espaces de travail verrouillés pour modification.
solution: Analytics
title: Définition du paramètre de déverrouillage
topic: Data workbench
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Définition du paramètre de déverrouillage{#set-the-unlock-parameter}

Le paramètre Déverrouiller dans le fichier Insight.cfg d’un utilisateur indique s’il est autorisé à déverrouiller temporairement les espaces de travail verrouillés pour modification.

Si le paramètre Déverrouiller est déjà présent dans le [!DNL Insight.cfg] fichier de l’utilisateur, vous pouvez le modifier à l’aide des outils de données. S’il n’est pas déjà présent dans le [!DNL Insight.cfg] fichier de l’utilisateur, vous devez l’ajouter au fichier à l’aide d’un éditeur de texte, tel que le Bloc-notes.

**Pour définir un[!DNL Unlock]paramètre existant dans le fichier Insight.cfg**

1. Dans un espace de travail, cliquez avec le bouton droit **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. Le [!DNL Insight.cfg] fichier s&#39;ouvre.
1. Pour le paramètre Déverrouiller, saisissez true ou false. True permet à l’utilisateur de déverrouiller temporairement un espace de travail verrouillé, contrairement à false.
1. Pour enregistrer vos modifications de configuration, cliquez avec le bouton droit **[!UICONTROL Insight.cfg (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save as Insight.cfg]**.

**Pour ajouter le paramètre Unlock au fichier Insight.cfg**

1. Accédez au répertoire d’installation des outils de données et ouvrez le [!DNL Insight.cfg] fichier à l’aide d’un éditeur de texte, tel que le Bloc-notes.
1. Ajoutez le paramètre Unlock à la fin du fichier, comme dans l’exemple suivant :

[!DNL Unlock = bool: false]

1. Définissez la valeur sur true ou false. True permet à l’utilisateur de déverrouiller temporairement un espace de travail verrouillé, contrairement à false.
1. Enregistrez et fermez le fichier.

