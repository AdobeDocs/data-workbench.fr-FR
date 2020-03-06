---
description: Les outils de données comprennent des mesures intégrées.
solution: Analytics
title: Mesures intégrées
topic: Data workbench
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mesures intégrées{#built-in-metrics}

Les outils de données comprennent des mesures intégrées.

Le tableau suivant répertorie les mesures intégrées disponibles pour les outils de données :

| Mesure intégrée | Description |
|---|---|
| À partir de | A partir du moment du jeu de données dans des intervalles de 100 nanosecondes depuis le 1er janvier 1600 00:00 UTC. L’horodatage A partir de est la dernière heure du jeu de données pour laquelle toutes les données ont définitivement été traitées. |
| Octets du journal lus | Quantité totale de données compressées (en octets) qui ont été traitées jusqu’à présent pendant la phase de traitement du journal. |
| Nombre total d&#39;octets du journal | Quantité totale de données compressées (en octets) dans les fichiers journaux correspondant aux critères des sources de fichiers journaux configurés et à la plage de dates de début et de fin du jeu de données. Si le traitement du journal est suspendu dans le fichier de configuration Mode de traitement du journal, le total des octets du journal sera identique à celui des octets du journal lus. |
| Progression du traitement du journal | Pourcentage d’achèvement de la phase de traitement du journal du traitement des données d’Insight Server. |
| Nombre total d’entrées de journal décodées | Nombre d’entrées dans les fichiers journaux qui ont été décodées avec succès dans le cadre de la phase de traitement des journaux du traitement des données d’Insight Server. |
| Nombre total d’entrées de journal filtrées | Nombre d’entrées dans les fichiers journaux qui, après leur décodage, ont été acceptées par le filtre robot, les conditions d’entrée du journal et d’autres filtres appliqués dans le cadre de la phase de traitement du journal du traitement des données d’Insight Server. |
| Nombre total d’entrées du journal | Nombre d’entrées dans les fichiers journaux qui ont jusqu’à présent été traitées par la phase de traitement des journaux du traitement des données d’Insight Server. |
| Nombre total d’entrées de journal traitées | Nombre d’entrées de journal filtrées qui ont été intégrées au jeu de données Adobe. |
| Progression de la transformation | Pourcentage d’achèvement de la phase de transformation du traitement des données d’Insight Server. |
| Octets journaux non compressés lus | Quantité totale de données non compressées (en octets) qui a été jusqu’à présent traitée au cours de la phase de traitement du journal. |

