---
description: Chaque unité de traitement de données à partir de laquelle le tableau de bord doit visualiser les données doit disposer d’une licence d’API de requête.
solution: Analytics
title: Vérification de l'activation de l'API de requête
topic: Data workbench
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Vérification de l&#39;activation de l&#39;API de requête{#verifying-query-api-enablement}

Chaque unité de traitement de données à partir de laquelle le tableau de bord doit visualiser les données doit disposer d’une licence d’API de requête.

Vous trouverez ci-dessous quelques instructions pour valider l’installation et l’activation de l’API de requête.

1. Recherchez le certificat du serveur de l’outil de données.
1. Ouvrez ce certificat dans un éditeur de texte.
1. Vérifiez que la ligne `Product = Query API` existe dans le certificat.
1. Dans le **[!UICONTROL Trace]** dossier, ouvrez [!DNL InsightServer64.log] dans un éditeur de texte.
1. Dans les dernières entrées du journal de démarrage, vérifiez que la ligne `Enabling Query API (licensed)` s’affiche.

* Si l’API de requête n’est pas activée, l’entrée `Not enabling Query API (not licensed)`.
* Si vous ne voyez aucune entrée de journal ou si vous pensez que le serveur de l&#39;outil de données a été redémarré depuis l&#39;ajout de l&#39;API de requête, redémarrez le serveur de l&#39;outil de données et vérifiez le journal.

   Si vous ne parvenez pas à valider l’activation de l’API de requête, contactez le service à la clientèle Adobe pour obtenir de l’aide.
