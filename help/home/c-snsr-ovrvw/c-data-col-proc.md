---
description: Sensor automatise l'acquisition de données à partir de votre canal Internet en éliminant la majeure partie de la main-d'oeuvre humaine traditionnellement impliquée dans la collecte de données.
title: Comment fonctionne le processus de collecte de données ?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# Comment fonctionne le processus de collecte de données ?{#how-does-the-data-collection-process-work}

Sensor automatise l&#39;acquisition de données à partir de votre canal Internet en éliminant la majeure partie de la main-d&#39;oeuvre humaine traditionnellement impliquée dans la collecte de données.

Dans de nombreux cas, l&#39;utilisation de [!DNL Sensor] peut considérablement simplifier votre processus de data Management.

Les grands sites Internet, extranet et intranet d&#39;aujourd&#39;hui s&#39;exécutent souvent sur une multitude de serveurs Web. Les journaux et les données produits peuvent être très volumineux et lourds à gérer. Par exemple, si votre site exécute 30 serveurs Web, en général l’un de vos employés (ou les employés d’un prestataire externalisé) extrait et consolide chaque fichier journal sur chacun des 30 serveurs, puis exécute des rapports à leur sujet. L&#39;installation de [!DNL Sensor] sur chacun de vos serveurs Web automatise l&#39;ensemble de ce processus, réduisant vos dépenses et rendant les données disponibles en temps réel.

Pour automatiser ce processus, [!DNL Sensor] collecte des informations brutes sur le trafic sur un site Web directement à partir de chaque serveur Web. Les données brutes que [!DNL Sensor] capture sont appelées données de événement et sont similaires au type de données que votre serveur Web enregistre dans ses fichiers journaux.

Pour capturer ces données, l’instrumentation dans [!DNL Sensor] enregistre des informations sur chaque requête HTTP traitée par votre serveur Web. [!DNL Sensor] place ensuite les informations en mémoire tampon afin de les protéger contre les défaillances du réseau et les transmet en toute sécurité via HTTP/S à l’adresse  [!DNL data workbench server] spécifiée.

Une fois que [!DNL data workbench server] a reçu les données, il traite et stocke vos fichiers journaux dans des fichiers au format [!DNL .vsl] très compressés, ce qui vous permet de gérer facilement de très grandes quantités de données sur du matériel peu coûteux.

Pour plus d&#39;informations sur les champs de données de événement collectés par [!DNL Sensor] dans les fichiers [!DNL .vsl], voir [Champs d&#39;enregistrement des données de Événement](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
