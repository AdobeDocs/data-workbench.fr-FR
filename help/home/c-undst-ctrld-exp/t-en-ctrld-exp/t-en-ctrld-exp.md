---
description: Pour activer l’expérimentation contrôlée, une personne disposant d’un accès administrateur à vos serveurs Web ou d’applications doit modifier le paramètre ExpFile dans le fichier de configuration de Sensor (généralement nommé à l’aide de txlogd.conf) sur chaque serveur Web ou d’application de votre grappe Web sur laquelle un capteur est installé.
solution: Analytics,Analytics
title: Activiation de l’expérience contrôlée
topic: Data workbench
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---


# Activiation de l’expérience contrôlée{#enabling-controlled-experimentation}

Pour activer l’expérimentation contrôlée, une personne disposant d’un accès administrateur à vos serveurs Web ou d’applications doit modifier le paramètre ExpFile dans le fichier de configuration de Sensor (généralement nommé à l’aide de txlogd.conf) sur chaque serveur Web ou d’application de votre grappe Web sur laquelle un capteur est installé.

En outre, deux autres paramètres de ce fichier peuvent être modifiés pour implémenter un outil de test (paramètre ExpCookieURL) ou pour remapper de grandes sections de votre site Web (paramètre ExpPartialMatch). Ce chapitre fournit plus d&#39;informations sur ces paramètres.

**Pour modifier le fichier txlogd.conf**

Si vous disposez d’un accès administrateur, suivez les étapes ci-après. Si vous ne disposez pas des droits d’administrateur, contactez votre architecte système pour demander les modifications, en leur fournissant les étapes suivantes.

1. Accédez au dossier [!DNL Sensor] d’installation sur un serveur Web ou d’applications de la grappe Web sur laquelle [!DNL Sensor] est installé un serveur.
1. Ouvrez le fichier [!DNL Sensor] de configuration (généralement nommé [!DNL txlogd.conf]) à l’aide d’un éditeur de texte et modifiez le fichier comme indiqué dans [Modification du paramètre](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)ExpFile.

   (Et éventuellement dans [Modification du paramètre ExpCookieURL (facultatif)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) et [Modification du paramètre ExpPartialMatch (facultatif)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e).)

1. Enregistrez et fermez le fichier.
1. Répétez cette procédure pour chaque serveur Web ou d’applications de la grappe Web sur laquelle un serveur [!DNL Sensor] est installé.
