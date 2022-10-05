---
description: Data Workbench comprend des mesures intégrées.
title: Mesures intégrées
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
exl-id: a8a2a8dd-dc13-4eb3-92ce-09f02252ecf0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 1%

---

# Mesures intégrées{#built-in-metrics}

{{eol}}

Data Workbench comprend des mesures intégrées.

Le tableau suivant répertorie les mesures intégrées disponibles pour Data Workbench :

| Mesure intégrée | Description |
|---|---|
| À partir de | À partir de l’heure du jeu de données en 100 nanosecondes d’intervalles depuis le 1er janvier 1600 00:00 UTC. L’horodatage À partir de est la dernière heure du jeu de données pour laquelle toutes les données ont été définitivement traitées. |
| Journal des octets lus | La quantité totale de données compressées (en octets) qui a été jusqu’à présent traitée pendant la phase de traitement du journal. |
| Nombre total d’octets du journal | La quantité totale de données compressées (en octets) dans les fichiers journaux correspondant aux critères des sources de journaux configurées et à la plage de dates de début et de fin du jeu de données. Si le traitement du journal est suspendu dans le fichier de configuration Mode de traitement du journal , le total des octets du journal est identique à celui de la lecture des octets du journal. |
| Progression du traitement du journal | Pourcentage d’achèvement de la phase de traitement des journaux du traitement des données par le serveur Insight. |
| Nombre total d’entrées de journal décodées | Le nombre d’entrées dans les fichiers journaux qui ont été décodées avec succès dans le cadre de la phase de traitement des journaux du traitement des données du serveur Insight. |
| Nombre total d’entrées de journal filtrées | Le nombre d’entrées dans les fichiers journaux qui, après leur décodage, ont été acceptés par le filtre robot, ainsi que les conditions d’entrée du journal et d’autres filtres appliqués dans le cadre de la phase de traitement du journal du traitement des données par le serveur Insight. |
| Nombre total d’entrées du journal | Le nombre d’entrées dans les fichiers journaux qui ont été jusqu’à présent traitées par la phase de traitement des journaux du traitement des données par le serveur Insight. |
| Nombre total d’entrées de journal traitées | Nombre d’entrées de journal filtrées qui ont été intégrées au jeu de données d’Adobe. |
| Progression de la transformation | Pourcentage d’achèvement de la phase de transformation du traitement des données du serveur Insight. |
| Lecture des octets journaux non compressés | La quantité totale de données non compressées (en octets) qui a été jusqu’à présent traitée pendant la phase de traitement du journal. |
