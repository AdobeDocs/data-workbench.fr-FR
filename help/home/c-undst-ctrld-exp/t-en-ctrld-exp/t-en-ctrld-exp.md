---
description: Pour activer l’expérimentation contrôlée, une personne disposant d’un accès administrateur à votre serveur web ou d’application doit modifier le paramètre ExpFile dans le fichier de configuration de Capteur (généralement nommé à l’aide de txlogd.conf) sur chaque serveur web ou d’application de la grappe web sur laquelle un Capteur est installé.
solution: Analytics
title: Activiation de l’expérience contrôlée
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
exl-id: 53c18524-6050-4708-af63-9e8ef8da389e
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---

# Activiation de l’expérience contrôlée{#enabling-controlled-experimentation}

Pour activer l’expérimentation contrôlée, une personne disposant d’un accès administrateur à votre serveur web ou d’application doit modifier le paramètre ExpFile dans le fichier de configuration de Capteur (généralement nommé à l’aide de txlogd.conf) sur chaque serveur web ou d’application de la grappe web sur laquelle un Capteur est installé.

En outre, deux autres paramètres de ce fichier peuvent être modifiés pour mettre en oeuvre un outil de test (paramètre ExpCookieURL) ou pour supprimer de grandes sections de votre site web (paramètre ExpPartialMatch ). Ce chapitre fournit des informations supplémentaires sur ces paramètres.

**Pour modifier le fichier txlogd.conf**

Si vous disposez d’un accès administrateur, procédez comme suit. Si vous ne disposez pas d’un accès administrateur, contactez votre architecte système pour demander les modifications, en leur indiquant les étapes suivantes.

1. Accédez au [!DNL Sensor] dossier d’installation sur un serveur web ou d’applications de la grappe web sur laquelle un [!DNL Sensor] est installé.
1. Ouvrez le [!DNL Sensor] fichier de configuration (généralement nommé à l’aide de [!DNL txlogd.conf]) à l’aide d’un éditeur de texte et modifiez le fichier comme indiqué dans la section [Modification du paramètre ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   (Et éventuellement dans [Modification du paramètre ExpCookieURL (facultatif)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) et [Modification du paramètre ExpPartialMatch (facultatif)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e).)

1. Enregistrez le fichier, puis fermez-le.
1. Répétez cette procédure pour chaque serveur Web ou d’applications de la grappe Web sur lequel une [!DNL Sensor] est installé.
