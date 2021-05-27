---
description: Chaque unité de traitement des données à partir de laquelle le tableau de bord doit visualiser les données doit disposer d’une licence d’API de requête.
title: Vérification de l’activation de l’API de requête
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# Vérification de l’activation de l’API de requête{#verifying-query-api-enablement}

Chaque unité de traitement des données à partir de laquelle le tableau de bord doit visualiser les données doit disposer d’une licence d’API de requête.

Vous trouverez ci-dessous quelques instructions pour valider l’installation et l’activation de l’API de requête.

1. Recherchez le certificat de votre serveur Data Workbench.
1. Ouvrez ce certificat dans un éditeur de texte.
1. Assurez-vous que la ligne `Product = Query API` existe dans le certificat.
1. Dans le dossier **[!UICONTROL Trace]** , ouvrez la balise [!DNL InsightServer64.log] dans un éditeur de texte.
1. Dans les dernières entrées de journal de démarrage, vérifiez que la ligne `Enabling Query API (licensed)` apparaît.

* Si l’API de requête n’est pas activée, l’entrée `Not enabling Query API (not licensed)` s’affiche.
* Si vous ne voyez aucune entrée de journal ou si vous pensez que le serveur Data Workbench a été redémarré depuis l’ajout de l’API Query, redémarrez le serveur Data Workbench et vérifiez le journal.

   Si vous ne pouvez pas valider l’activation de l’API de requête, contactez le service à la clientèle Adobe pour obtenir de l’aide.
