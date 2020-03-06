---
description: Pour activer l’expérimentation contrôlée, une personne disposant d’un accès administrateur à votre site Web ou à vos serveurs d’applications doit modifier le paramètre ExpFile dans le fichier de configuration Sensor (généralement nommé à l’aide de txlogd.conf) sur chaque serveur Web ou d’applications de la grappe Web sur laquelle un capteur est installé.
solution: Insight,Analytics
title: Activation de l’expérimentation contrôlée
topic: Data workbench
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Activation de l’expérimentation contrôlée{#enabling-controlled-experimentation}

Pour activer l’expérimentation contrôlée, une personne disposant d’un accès administrateur à votre site Web ou à vos serveurs d’applications doit modifier le paramètre ExpFile dans le fichier de configuration Sensor (généralement nommé à l’aide de txlogd.conf) sur chaque serveur Web ou d’applications de la grappe Web sur laquelle un capteur est installé.

En outre, deux autres paramètres de ce fichier peuvent être modifiés pour implémenter un outil de test (paramètre ExpCookieURL) ou pour remapper de grandes sections de votre site Web (paramètre ExpPartialMatch). Ce chapitre fournit plus d’informations sur ces paramètres.

**Pour modifier le fichier txlogd.conf**

Si vous disposez d’un accès administrateur, procédez comme suit. Si vous ne disposez pas des droits d’administrateur, contactez votre architecte système pour demander les modifications, en leur indiquant les étapes suivantes.

1. Accédez au dossier [!DNL Sensor] d’installation d’un serveur Web ou d’applications dans la grappe Web sur laquelle [!DNL Sensor] est installé un serveur.
1. Ouvrez le fichier de [!DNL Sensor] configuration (généralement nommé [!DNL txlogd.conf]) à l’aide d’un éditeur de texte et modifiez le fichier comme indiqué dans [Modification du paramètre](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)ExpFile.

   (Et éventuellement dans [Modification du paramètre ExpCookieURL (facultatif)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) et [Modification du paramètre ExpPartialMatch (facultatif)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e).)

1. Enregistrez et fermez le fichier.
1. Répétez cette procédure pour chaque serveur Web ou d’applications de votre grappe Web sur laquelle [!DNL Sensor] est installé un serveur.
