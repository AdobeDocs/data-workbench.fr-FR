---
description: Sensor automatise l’acquisition de données à partir de votre canal Internet en éliminant la majeure partie du travail humain traditionnellement impliqué dans la collecte de données.
solution: Insight
title: Comment fonctionne le processus de collecte de données ?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Comment fonctionne le processus de collecte de données ?{#how-does-the-data-collection-process-work}

Sensor automatise l’acquisition de données à partir de votre canal Internet en éliminant la majeure partie du travail humain traditionnellement impliqué dans la collecte de données.

Dans de nombreux cas, l’utilisation [!DNL Sensor] peut considérablement simplifier votre processus de gestion des données.

Les grands sites Internet, extranet et intranet d&#39;aujourd&#39;hui s&#39;exécutent souvent sur un large éventail de serveurs Web. Les journaux et les données produits peuvent être très volumineux et lourds à gérer. Par exemple, si votre site exécute 30 serveurs Web, en règle générale, l’un de vos employés (ou les employés d’un fournisseur de services externalisé) extrait et consolide chaque fichier journal sur chacun des 30 serveurs, puis exécute des rapports à leur sujet. L’installation [!DNL Sensor] sur chacun de vos serveurs Web automatise l’ensemble du processus, réduisant vos dépenses et rendant les données disponibles en temps réel.

Pour automatiser ce processus, [!DNL Sensor] collecte des informations brutes sur le trafic sur un site Web directement à partir de chaque serveur Web. Les données brutes qui [!DNL Sensor] capturent sont appelées données d’événement et sont similaires au type de données que votre serveur Web enregistre dans ses fichiers journaux.

Pour capturer ces données, l’instrumentation [!DNL Sensor] enregistre les informations sur chaque requête HTTP traitée par votre serveur Web. [!DNL Sensor] place ensuite les informations en mémoire tampon afin de les protéger contre les défaillances du réseau et les transmet en toute sécurité via HTTP/S au serveur [!DNL data workbench server] que vous spécifiez.

Une fois les données [!DNL data workbench server] reçues, il traite et stocke vos fichiers journaux dans des fichiers [!DNL .vsl] compressés, ce qui vous permet de gérer facilement de très grandes quantités de données sur du matériel peu coûteux.

Pour plus d’informations sur les champs de données d’événement collectés par [!DNL Sensor] dans [!DNL .vsl] les fichiers, voir Champs [d’enregistrement des données d’](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)événement.
