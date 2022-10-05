---
description: Après l’installation, le certificat numérique émis par Adobe agit comme une clé qui vous permet d’exécuter le serveur de rapports.
title: Revalidation du certificat numérique (présentation)
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 10%

---

# Revalidation du certificat numérique{#re-validating-the-digital-certificate}

{{eol}}

Après l’installation, le certificat numérique émis par Adobe agit comme une clé qui vous permet d’exécuter le serveur de rapports.

**Fréquence recommandée :** Selon les besoins

Pour fonctionner correctement, un certificat numérique doit être à jour.

Pour rester à jour, votre certificat numérique doit être régulièrement revalidé (généralement tous les 30 jours, mais cela peut varier en fonction de votre contrat avec Adobe). Si votre machine dispose d’un accès Internet, le processus de revalidation est entièrement transparent. [!DNL Report Server] se connecte automatiquement au serveur de licences d’Adobe et re-valide le certificat si nécessaire. Si votre machine ne dispose pas d’un accès Internet, vous devez télécharger un nouveau certificat validé à partir du serveur de licences d’Adobe et l’installer sur votre machine en suivant les étapes fournies dans la section [Téléchargement et installation du certificat numérique](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
