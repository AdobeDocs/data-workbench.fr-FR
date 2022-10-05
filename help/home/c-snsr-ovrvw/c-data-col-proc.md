---
description: Sensor automatise l’acquisition de données à partir de votre canal Internet en supprimant la majeure partie de la main-d’oeuvre traditionnellement impliquée dans la collecte de données.
title: Comment fonctionne le processus de collecte de données ?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# Comment fonctionne le processus de collecte de données ?{#how-does-the-data-collection-process-work}

{{eol}}

Sensor automatise l’acquisition de données à partir de votre canal Internet en supprimant la majeure partie de la main-d’oeuvre traditionnellement impliquée dans la collecte de données.

Dans de nombreux cas, l’utilisation de [!DNL Sensor] peut considérablement simplifier votre processus de gestion des données.

Les grands sites Internet, extranet et intranet d’aujourd’hui s’exécutent souvent sur un large éventail de serveurs web. Les logs et les données produits peuvent être très volumineux et encombrants à gérer. Par exemple, si votre site exécute 30 serveurs web, généralement l’un de vos employés (ou les employés du fournisseur de services externalisé) extrait et consolide chaque fichier journal sur chacun des 30 serveurs, puis exécute des rapports à leur sujet. Installation [!DNL Sensor] sur chacun de vos serveurs web automatise l’ensemble du processus, réduisant vos dépenses et rendant les données disponibles en temps réel.

Pour automatiser ce processus, [!DNL Sensor] collecte des informations brutes sur le trafic sur un site web directement à partir de chaque serveur web. Les données brutes qui [!DNL Sensor] La capture est appelée données d’événement et est similaire au type de données enregistré par votre serveur web dans ses fichiers journaux.

Pour capturer ces données, procédez comme suit : [!DNL Sensor] enregistre des informations sur chaque requête HTTP traitée par votre serveur web. [!DNL Sensor] place ensuite les informations en mémoire tampon afin de les protéger contre les défaillances du réseau et transmet en toute sécurité les informations via HTTP/S au [!DNL data workbench server] que vous spécifiez.

Après la [!DNL data workbench server] reçoit les données, traite et stocke vos fichiers journaux dans des fichiers hautement compressés. [!DNL .vsl] fichiers de format, ce qui vous permet de gérer facilement de très grandes quantités de données sur du matériel peu coûteux.

Pour plus d’informations sur les champs de données d’événement collectés par [!DNL Sensor] in [!DNL .vsl] fichiers, voir [Champs d’enregistrement des données d’événement](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
