---
description: Après l’installation, le certificat numérique émis par l’Adobe agit comme une clé qui vous permet d’exécuter Report Server.
title: Revalidation du certificat numérique
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 13%

---

# Revalidation du certificat numérique{#re-validating-the-digital-certificate}

Après l’installation, le certificat numérique émis par l’Adobe agit comme une clé qui vous permet d’exécuter Report Server.

**Fréquence recommandée :** si nécessaire

Pour fonctionner correctement, un certificat numérique doit être à jour.

Pour rester à jour, votre certificat numérique doit être revalidé régulièrement (généralement tous les 30 jours, mais cela peut varier selon votre accord avec l’Adobe). Si votre machine dispose d’un accès Internet, le processus de revalidation est entièrement transparent. [!DNL Report Server] se connecte automatiquement au serveur de licences d’Adobe et révalide le certificat si nécessaire. Si votre ordinateur n’a pas accès à Internet, vous devez télécharger un nouveau certificat validé à partir du serveur de licence d’Adobe et l’installer sur votre ordinateur en suivant les étapes fournies dans [Téléchargement et installation du certificat numérique](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
