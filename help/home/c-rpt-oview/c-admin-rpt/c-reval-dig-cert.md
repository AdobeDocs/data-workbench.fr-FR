---
description: Après l’installation, le certificat numérique émis par Adobe joue le rôle de clé qui vous permet d’exécuter Report Server.
solution: Analytics
title: Nouvelle validation du certificat numérique
topic: Data workbench
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Nouvelle validation du certificat numérique{#re-validating-the-digital-certificate}

Après l’installation, le certificat numérique émis par Adobe joue le rôle de clé qui vous permet d’exécuter Report Server.

**Fréquence recommandée :** Au besoin

Pour fonctionner correctement, un certificat numérique doit être à jour.

Pour rester à jour, votre certificat numérique doit être révalidé régulièrement (généralement tous les 30 jours, mais cela peut varier selon votre accord avec Adobe). Si votre machine a accès à Internet, le processus de revalidation est complètement transparent. [!DNL Report Server] se connecte automatiquement au serveur de licences Adobe et révalide le certificat si nécessaire. Si votre ordinateur n’a pas accès à Internet, vous devez télécharger un nouveau certificat validé à partir du serveur de licences Adobe et l’installer sur votre ordinateur en suivant les étapes décrites dans la section [Téléchargement et installation du certificat](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)numérique.
