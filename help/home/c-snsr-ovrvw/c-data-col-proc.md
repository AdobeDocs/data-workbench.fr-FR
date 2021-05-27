---
description: Sensor automatise l’acquisition de données à partir de votre canal Internet en supprimant la majeure partie de la main-d’oeuvre traditionnellement impliquée dans la collecte de données.
title: Comment fonctionne le processus de collecte de données ?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# Comment fonctionne le processus de collecte de données ?{#how-does-the-data-collection-process-work}

Sensor automatise l’acquisition de données à partir de votre canal Internet en supprimant la majeure partie de la main-d’oeuvre traditionnellement impliquée dans la collecte de données.

Dans de nombreux cas, l’utilisation de [!DNL Sensor] peut considérablement simplifier votre processus de gestion des données.

Les grands sites Internet, extranet et intranet d’aujourd’hui s’exécutent souvent sur un large éventail de serveurs web. Les logs et les données produits peuvent être très volumineux et encombrants à gérer. Par exemple, si votre site exécute 30 serveurs web, généralement l’un de vos employés (ou les employés du fournisseur de services externalisé) extrait et consolide chaque fichier journal sur chacun des 30 serveurs, puis exécute des rapports à leur sujet. L’installation de [!DNL Sensor] sur chacun de vos serveurs Web automatise l’ensemble de ce processus, ce qui réduit vos dépenses et rend les données disponibles en temps réel.

Pour automatiser ce processus, [!DNL Sensor] collecte des informations brutes sur le trafic sur un site web directement depuis chaque serveur web. Les données brutes capturées par [!DNL Sensor] sont appelées données d’événement et sont similaires au type de données enregistré par votre serveur web dans ses fichiers journaux.

Pour capturer ces données, l’instrumentation dans [!DNL Sensor] enregistre des informations sur chaque requête HTTP que votre serveur web traite. [!DNL Sensor] place ensuite les informations en mémoire tampon afin de les protéger contre les défaillances du réseau et transmet en toute sécurité les informations via HTTP/S à la  [!DNL data workbench server] que vous spécifiez.

Une fois que la [!DNL data workbench server] a reçu les données, elle traite et stocke vos fichiers journaux dans des fichiers au format [!DNL .vsl] hautement compressés, ce qui vous permet de conserver facilement de très grandes quantités de données sur du matériel peu coûteux.

Pour plus d’informations sur les champs de données d’événement collectés par [!DNL Sensor] dans les fichiers [!DNL .vsl], voir [Champs d’enregistrement des données d’événement](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
