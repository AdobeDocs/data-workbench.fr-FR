---
description: La liste suivante répertorie les mesures incluses dans le profil de surveillance historique de l’outil de données et leur origine.
solution: Analytics
title: Mesures du profil de surveillance historique des outils de données
topic: Data workbench
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mesures du profil de surveillance historique des outils de données{#metrics-in-the-data-workbench-historical-monitoring-profile}

La liste suivante répertorie les mesures incluses dans le profil de surveillance historique de l’outil de données et leur origine.

| **Critiques d&#39;alerte** | Somme de la dimension Critique d’alerte pour chaque ping. |
|---|---|
| **Annonces d&#39;alerte** | Somme de la dimension Alerte vers le bas pour chaque ping. |
| **Avertissements d&#39;alerte** | Somme de la dimension Avertissement d’alerte pour chaque ping. |
| **Tous les composants** | Nombre de pings pour lesquels la réussite de la vérification des composants est égale à &quot;1&quot; divisé par la mesure Pings multiplié par 100. |
| **À Compter Du Délai** | Cette mesure correspond à la somme des minutes de délai A partir de chaque ping, puis divisée par la mesure Pings. |
| **Blocs** | Somme d’un pour chaque bloc. |
| **Bloquer tout** | Tous les blocs. |
| **Capacité globale** | La mesure Taille de la capacité multiplie 2 par la mesure Rangée de capacité, divisée par 3. |
| **Rangée de capacité** | Somme de la dimension Pourcentage de rangée de capacité pour chaque ping divisée par la mesure Anneaux. |
| **Taille de la capacité** | Somme de la dimension Pourcentage de taille de capacité pour chaque ping, divisée par la mesure Anneaux. |
| **Communications** | Nombre de pings pour lesquels la réussite de la vérification rapide correspond à &quot;1&quot;, divisé par la mesure Pings. |
| **Secondes de vérification détaillées** | Somme de la dimension Secondes de vérification détaillées pour chaque ping dont le type est &quot;serveur&quot;, divisée par la mesure Pings. |
| **Dimension gigaoctets** | Somme des gigaoctets de dimension pour chaque ping, divisée par la mesure Pings. |
| **Disque &quot;x&quot;** | Les mesures Disque sont calculées en prenant la somme de leur pourcentage d&#39;utilisation de disque pour chaque Ping, divisée par la mesure Pings. |
| **Estimation des minutes de balayage** | Il s’agit de la somme des Dekasecondes de balayage estimées pour chaque Ping, divisée par la mesure Pings où l’estimation des Dekasecondes de balayage est supérieure à zéro, toutes divisées par 6. |
| **Entrée rapide Mo par minute** | Somme des méga-octets d’entrée rapide par minute pour chaque ping divisée par le nombre de pings lorsque la valeur Méga-octets d’entrée rapide par minute est supérieure à zéro. |
| **Mode d’entrée rapide** | Pings dont la dimension Mode de traitement est égale à &quot;Entrée rapide&quot; divisée par Pings. |
| **Fusion rapide MégaOctets par minute** | Somme des mégaoctets de fusion rapide par minute pour chaque ping, divisée par la mesure Pings. |
| **Mode de fusion rapide** | Pings pour lesquels le mode de traitement est égal à &quot;fusion rapide&quot; divisé par la mesure Pings. |
| **Champ GigaBytes** | Somme de la dimension Champ en gigaoctets pour chaque ping divisé par la mesure Pings. |
| **Load** | Somme de la dimension Moyenne de charge pour chaque ping, divisée par la mesure Anneaux. |
| **Lecture du journal** | Somme de la dimension Traitement de la lecture du journal pour chaque ping, divisée par la mesure Pings, toutes divisées par 10. |
| **Page Mémoire** | Somme du pourcentage de fichier de page mémoire pour chaque ping, divisée par la mesure Pings. |
| **Mémoire physique** | Somme de la dimension Pourcentage physique de la mémoire pour chaque ping, divisée par la mesure Anneaux. |
| **Requête mémoire** | Somme du pourcentage de requête en mémoire pour chaque ping, divisée par la mesure Pings. |
| **Mémoire totale Go** | Somme de la dimension Mémoire physique MégaOctets totaux pour chaque ping, divisée par la mesure Pings. |
| **Connexions réseau** | Il s’agit de la somme des connexions réseau pour chaque ping divisée par la mesure Pings. |
| **Pings x Capacité globale** | Mesure Pings multipliée par la mesure Capacité totale. |
| **Latence du sondage en millisecondes** | Somme de la dimension Centisecondes de latence du sondage pour chaque ping, divisée par la mesure Pings, toutes multipliées par 10. |
| **Requête en cours** | La somme d’un pour chaque ping pour lequel l’estimation des dekaseconds de balayage est supérieure à &quot;0&quot;, divisée par la mesure Pings où Type de ping est égal à &quot;serveur&quot;. |
| **Secondes de vérification rapide** | Somme des secondes de vérification rapide pour chaque ping dont le type Ping est égal à &quot;serveur&quot;, divisée par la mesure Pings. |
| **Lignes de sortie** | Somme de la dimension Lignes de sortie pour chaque ping divisée par la mesure Anneaux, multipliée par 100 000. |
| **Mode Temps réel** | Nombre de ping pour lesquels la dimension Mode de traitement est égale à &quot;temps réel&quot;, divisé par la mesure Anneaux, le tout multiplié par 100. |
| **Mode de retraitement** | 100 moins le nombre de pings pour lesquels le mode de traitement est égal à &quot;temps réel&quot; divisé par la mesure Pings, multiplié par 100. |
| **Bloqué** | Somme de la dimension Traitement bloqué dans le profil d’état [du](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64) profil Insight. |
| **Base de données temporaire** | Somme de l’espace de base de données temporaire pour chaque ping, divisée par la mesure Anneaux. |
| **Transformation** | Somme du pourcentage de transformation pour chaque ping divisée par la mesure Pings, toutes divisées par 10. |

