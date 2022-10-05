---
description: Vous trouverez ci-dessous la liste des mesures incluses dans le profil de surveillance historique de Data Workbench et la manière dont elles sont dérivées.
title: Mesures dans le profil de surveillance historique de Data Workbench
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
exl-id: 65f0f605-f128-45bb-8f6c-95284b2da740
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 2%

---

# Mesures dans le profil de surveillance historique de Data Workbench{#metrics-in-the-data-workbench-historical-monitoring-profile}

{{eol}}

Vous trouverez ci-dessous la liste des mesures incluses dans le profil de surveillance historique de Data Workbench et la manière dont elles sont dérivées.

| **Critiques d’alerte** | Somme de la dimension Critique d’alerte pour chaque ping. |
|---|---|
| **Alertes** | Somme de la dimension Fin de l’alerte pour chaque ping. |
| **Avertissements d’alerte** | Somme de la dimension Avertissement d’alerte pour chaque ping. |
| **Tous les composants** | Le nombre de pings pour lesquels la vérification du composant est égale à &quot;1&quot; divisé par la mesure Pings multiplié par 100. |
| **À Compter Du Délai** | Cette mesure correspond à la somme des minutes &quot;À partir du délai&quot; pour chaque ping, puis divisée par la mesure Pings. |
| **Blocs** | La somme de un pour chaque bloc. |
| **Tout bloquer** | Tous les blocs. |
| **Capacité globale** | La mesure Taille de la capacité est deux fois plus la mesure Ligne de capacité, divisée par 3. |
| **Ligne de capacité** | Somme de la dimension Pourcentage de la ligne de capacité pour chaque ping divisée par la mesure Pings. |
| **Taille de la capacité** | Somme de la dimension Pourcentage de taille de capacité pour chaque ping, divisée par la mesure Pings. |
| **Communications** | Nombre de pings pour lesquels la réussite de la vérification rapide correspond à &quot;1&quot;, divisé par la mesure Pings. |
| **Secondes de vérification détaillées** | Somme de la dimension Détails des secondes de vérification pour chaque ping dont le type de ping est &quot;serveur&quot;, divisée par la mesure Pings. |
| **Dimension giga-octets** | Somme en gigaoctets de Dimension pour chaque ping, divisée par la mesure Pings. |
| **Disque &quot;x&quot;** | Les mesures Disque sont calculées en prenant la somme de leur pourcentage d’utilisation du disque pour chaque ping, divisé par la mesure Pings. |
| **Nombre estimé de minutes de balayage** | Il s’agit de la somme des Dekasecondes de balayage estimées pour chaque ping, divisée par la mesure Pings où l’écart de balayage estimé est supérieur à zéro, tous divisés par 6. |
| **MB d’entrée rapide par minute** | La somme des méga-octets d’entrée rapide par minute pour chaque ping divisée par le nombre de pings lorsque le MegaBytes d’entrée rapide par minute est supérieur à zéro. |
| **Mode d’entrée rapide** | Pings dont la dimension Mode de traitement est égale à &quot;Entrée rapide&quot; divisée par Pings. |
| **Fusion rapide : méga octets par minute** | Somme des mégaoctets de fusion rapide par minute pour chaque ping, divisée par la mesure Pings. |
| **Mode Fusion rapide** | Pings pour lesquels le mode de traitement est égal à &quot;fusion rapide&quot; divisé par la mesure Pings. |
| **Champ GigaBytes** | Somme de la dimension en gigaoctets du champ pour chaque ping divisée par la mesure Pings. |
| **Load** | Somme de la dimension Load Average pour chaque ping, divisée par la mesure Pings. |
| **Lecture du journal** | Somme de la dimension Traitement de la lecture du journal pour chaque ping, divisée par la mesure Pings, toutes divisées par 10. |
| **Page de mémoire** | Somme du pourcentage de fichier de page mémoire pour chaque ping, divisée par la mesure Pings. |
| **Mémoire physique** | Somme de la dimension Pourcentage physique de la mémoire pour chaque ping, divisée par la mesure Pings. |
| **Requête mémoire** | Somme du pourcentage de requête de mémoire pour chaque ping, divisée par la mesure Pings. |
| **Mémoire totale en Go** | Somme de la dimension totale en méga-octets physiques de la mémoire pour chaque ping, divisée par la mesure Pings. |
| **Connexions réseau** | Il s’agit de la somme des connexions réseau pour chaque ping divisée par la mesure Pings. |
| **Pings x Capacité globale** | Mesure Pings multipliée par la mesure Capacité globale. |
| **Latence du sondage, millisecondes** | Somme de la dimension Centisecondes de latence du sondage pour chaque ping, divisée par la mesure Pings, le tout multiplié par 10. |
| **Requête en cours** | La somme de un pour chaque ping pour lequel l’estimation des secondes de balayage est supérieure à &quot;0&quot;, divisée par la mesure Pings où le type de ping est égal à &quot;server&quot;. |
| **Secondes de vérification rapide** | Somme des secondes de vérification rapide pour chaque ping pour lequel le type de ping est égal à &quot;serveur&quot;, divisée par la mesure Pings. |
| **Lignes de sortie** | La somme des lignes de sortie pour chaque ping divisée par la mesure Pings, multipliée par 100000. |
| **Mode temps réel** | Nombre de pings pour lesquels la dimension Mode de traitement est égale à &quot;temps réel&quot;, divisé par la mesure Pings, tous multipliés par 100. |
| **Mode de retraitement** | 100 moins le nombre de pings pour lesquels le mode de traitement est égal à &quot;temps réel&quot; divisé par la mesure Pings, multiplié par 100. |
| **Bloqué** | Somme de la dimension Traitement bloqué dans Insight [État du profil](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64) profile. |
| **Temp DB** | Somme du pourcentage d’espace de la base de données temporaire pour chaque ping, divisée par la mesure Pings. |
| **Transformation** | Somme du pourcentage de transformation pour chaque ping divisée par la mesure Pings, divisée par 10. |
