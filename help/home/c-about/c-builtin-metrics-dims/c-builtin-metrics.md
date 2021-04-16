---
description: Les outils de données comprennent des mesures intégrées.
title: Mesures intégrées
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
exl-id: a8a2a8dd-dc13-4eb3-92ce-09f02252ecf0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 1%

---

# Mesures intégrées{#built-in-metrics}

Les outils de données comprennent des mesures intégrées.

Le tableau suivant liste les mesures intégrées disponibles pour les outils de données :

| Mesure intégrée | Description |
|---|---|
| À partir de | A partir de la date du jeu de données en 100 nanosecondes d&#39;intervalles depuis le 1er janvier 1600 00:00 UTC. L’horodatage A partir de est la dernière heure du jeu de données pour laquelle toutes les données ont définitivement été traitées. |
| Journal Octets lus | Quantité totale de données compressées (en octets) qui ont été traitées jusqu’à présent au cours de la phase de traitement du journal. |
| Nombre total d&#39;octets de journal | Quantité totale de données compressées (en octets) dans les fichiers journaux correspondant aux critères des sources de journal configurées et à la plage de dates de début et de fin du jeu de données. Si le traitement du journal est suspendu dans le fichier de configuration Mode de traitement du journal, le total des octets du journal sera identique à celui des octets du journal lus. |
| Progression du traitement du journal | Pourcentage d’achèvement de la phase de traitement du journal du traitement des données d’Insight Server. |
| Nombre total d&#39;entrées de journal décodées | Nombre d’entrées dans les fichiers journaux qui ont été décodées avec succès dans le cadre de la phase de traitement des journaux du traitement des données d’Insight Server. |
| Nombre total d&#39;entrées de journal filtrées | Nombre d’entrées dans les fichiers journaux qui, après leur décodage, ont été acceptées par le filtre robot et les conditions d’entrée dans le journal ainsi que d’autres filtres appliqués dans le cadre de la phase de traitement du journal du traitement des données d’Insight Server. |
| Nombre total d&#39;entrées de journal | Nombre d’entrées dans les fichiers journaux qui ont jusqu’à présent été traitées par la phase de traitement des journaux du traitement des données d’Insight Server. |
| Nombre total d&#39;entrées de journal traitées | Nombre d’entrées de journal filtrées qui ont été incorporées dans le jeu de données d’Adobe. |
| Progression de la transformation | Pourcentage d’achèvement de la phase de transformation du traitement des données d’Insight Server. |
| Octets journaux non compressés lus | Quantité totale de données non compressées (en octets) qui a été jusqu’à présent traitée durant la phase de traitement du journal. |
