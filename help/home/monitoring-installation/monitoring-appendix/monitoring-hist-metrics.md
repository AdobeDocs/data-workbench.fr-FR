---
description: Les listes suivantes concernent les mesures incluses dans le Profil de surveillance historique des outils de données et la manière dont elles sont dérivées.
title: Mesures dans le profil de surveillance historique de Data Workbench
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
exl-id: 65f0f605-f128-45bb-8f6c-95284b2da740
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 2%

---

# Mesures dans le profil de surveillance historique de Data Workbench{#metrics-in-the-data-workbench-historical-monitoring-profile}

Les listes suivantes concernent les mesures incluses dans le Profil de surveillance historique des outils de données et la manière dont elles sont dérivées.

| **Critiques des alertes** | Somme de la dimension Critique d&#39;alerte pour chaque ping. |
|---|---|
| **Annonces d&#39;alerte** | Somme de la dimension Alerte vers le bas pour chaque ping. |
| **Avertissements d&#39;alerte** | Somme de la dimension Avertissement d&#39;alerte pour chaque ping. |
| **Tous les composants** | Nombre de pings pour lesquels la réussite de la vérification des composants est égale à &quot;1&quot; divisé par la mesure Pings multiplié par 100. |
| **À Compter Du Délai** | Cette mesure correspond à la somme des minutes de délai A partir de chaque ping, puis divisée par la mesure Anneaux. |
| **Blocs** | Somme de un pour chaque bloc. |
| **Bloquer tout** | Tous les blocs. |
| **Capacité globale** | La mesure Taille de la capacité multiplie 2 par la mesure Rangée de capacité, divisée par 3. |
| **Rangée de capacité** | Somme de la dimension Pourcentage de rangées de capacité pour chaque ping divisée par la mesure Anneaux. |
| **Taille de capacité** | Somme de la dimension Pourcentage de taille de capacité pour chaque ping, divisée par la mesure Anneaux. |
| **Communications** | Nombre de pings pour lesquels la réussite de la vérification rapide correspond à &quot;1&quot;, divisé par la mesure Pings. |
| **Secondes de vérification détaillées** | Somme de la dimension Secondes de vérification détaillées pour chaque ping dont le type est &quot;serveur&quot;, divisée par la mesure Anneaux. |
| **Dimension GigaBytes** | Somme en gigaoctets de Dimension pour chaque ping, divisée par la mesure Anneaux. |
| **Disque &quot;x&quot;** | Les mesures Disque sont calculées en prenant la somme de leur pourcentage d&#39;utilisation de disque pour chaque Ping, divisée par la mesure Pings. |
| **Estimation des minutes de balayage** | Il s’agit de la somme des Dekaseconds de balayage estimés pour chaque Ping, divisée par la mesure Pings où l’estimation des dekaseconds de balayage est supérieure à zéro, tous divisés par 6. |
| **Entrée rapide Mo par minute** | La somme des méga-octets d&#39;entrée rapide par minute pour chaque ping divisée par le nombre de ping lorsque la valeur MégaBytes d&#39;entrée rapide par minute est supérieure à zéro. |
| **Mode d’entrée rapide** | Pings pour lesquels la dimension Mode de traitement est égale à &quot;Entrée rapide&quot; divisée par Pings. |
| **Fusion rapide MégaBytes par minute** | Somme des mégaoctets de fusion rapide par minute pour chaque ping, divisée par la mesure Pings. |
| **Mode de fusion rapide** | Chaînes dont le mode de traitement est égal à &quot;fusion rapide&quot; divisée par la mesure Chaînes. |
| **Champ GigaBytes** | Somme de la dimension en gigaoctets de champ pour chaque ping divisée par la mesure Anneaux. |
| **Load** | Somme de la dimension Moyenne de charge pour chaque ping, divisée par la mesure Anneaux. |
| **Lecture du journal** | Somme de la dimension Traitement de la lecture du journal pour chaque ping, divisée par la mesure Anneaux, toutes divisées par 10. |
| **Page de mémoire** | Somme du pourcentage de fichier de page mémoire pour chaque ping, divisée par la mesure Pings. |
| **Mémoire physique** | Somme de la dimension Pourcentage physique de la mémoire pour chaque ping, divisée par la mesure Anneaux. |
| **Requête de mémoire** | Somme du pourcentage de Requête de mémoire pour chaque ping, divisée par la mesure Pings. |
| **Mémoire totale Go** | Somme de la dimension Mémoire physique MegaBytes Total pour chaque ping, divisée par la mesure Anneaux. |
| **Connexions réseau** | Il s’agit de la somme des connexions réseau pour chaque ping divisée par la mesure Pings. |
| **Pings x Capacité totale** | Mesure Pings multipliée par la mesure Capacité totale. |
| **Latence du sondage en millisecondes** | Somme de la dimension Centisecondes de latence du sondage pour chaque ping, divisée par la mesure Anneaux, le tout multiplié par 10. |
| **Requête en cours** | La somme d’un pour chaque ping pour lequel l’estimation des dekaseconds de balayage est supérieure à &quot;0&quot;, divisée par la mesure Pings où Type de ping est égal à &quot;serveur&quot;. |
| **Secondes de vérification rapide** | Somme des secondes de vérification rapide pour chaque ping où le type de ping est égal à &quot;serveur&quot;, divisée par la mesure Anneaux. |
| **Lignes de sortie** | Somme de la dimension Lignes de sortie pour chaque ping divisée par la mesure Anneaux, multipliée par 100 000. |
| **Mode Temps réel** | Nombre de ping pour lesquels la dimension Mode de traitement est égale à &quot;temps réel&quot;, divisé par la mesure Chaînes, le tout multiplié par 100. |
| **Mode de retraitement** | 100 moins le nombre de ping où le mode de traitement est égal à &quot;temps réel&quot; divisé par la mesure Pings, multiplié par 100. |
| **Bloqué** | Somme de la dimension Traitement bloqué dans le profil Insight [État du Profil](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64). |
| **Base de données temporaire** | Somme du pourcentage d’espace de la base de données temporaire pour chaque ping, divisée par la mesure Anneaux. |
| **Transformation** | Somme du pourcentage de transformation pour chaque ping divisée par la mesure Pings, divisée par 10. |
