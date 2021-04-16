---
description: Chaque unité de traitement de données à partir de laquelle le tableau de bord doit visualiser les données doit disposer d’une licence d’API de Requête.
title: Vérification de l’activation de l’API de requête
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# Vérification de l’activation de l’API de requête{#verifying-query-api-enablement}

Chaque unité de traitement de données à partir de laquelle le tableau de bord doit visualiser les données doit disposer d’une licence d’API de Requête.

Vous trouverez ci-dessous quelques instructions sur la façon de valider l’installation et l’activation de l’API de Requête.

1. Recherchez le certificat de votre serveur de l’outil de données.
1. Ouvrez ce certificat dans un éditeur de texte.
1. Assurez-vous que la ligne `Product = Query API` existe dans le certificat.
1. Dans le dossier **[!UICONTROL Trace]**, ouvrez [!DNL InsightServer64.log] dans un éditeur de texte.
1. Dans les dernières entrées du journal de démarrage, vérifiez que la ligne `Enabling Query API (licensed)` apparaît.

* Si l&#39;API de Requête n&#39;est pas activée, l&#39;entrée `Not enabling Query API (not licensed)` s&#39;affiche.
* Si vous ne voyez aucune entrée de journal ou si vous pensez que le serveur de l’outil de données a été redémarré depuis l’ajout de l’API de Requête, redémarrez le serveur de l’outil de données et vérifiez le journal.

   Si vous ne parvenez pas à valider l’activation de l’API de Requête, contactez le service à la clientèle Adobe pour obtenir de l’aide.
