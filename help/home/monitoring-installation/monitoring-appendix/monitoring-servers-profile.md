---
description: Les dimensions suivantes peuvent être utilisées dans le profil d’état du serveur de l’outil de données.
title: Dimensions dans le profil du statut du serveur de Data Workbench
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Dimensions dans le profil du statut du serveur de Data Workbench{#dimensions-in-the-data-workbench-server-status-profile}

Les dimensions suivantes peuvent être utilisées dans le profil d’état du serveur de l’outil de données.

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Serveur</b> </td> 
   <td colname="col2"> Créée à partir du champ x-trackingid, cette dimension dénombrable représente les serveurs exécutant actuellement l’outil de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Version de l'agent</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(af) est utilisée pour cette Dimension simple. Il s’agit de la valeur Dernier non vide pour un serveur. Cette option affiche la date et l'heure de création des versions de l'agent de surveillance en cours d'exécution. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tout retraitement de Profil</b> </td> 
   <td colname="col2"> Le champ cs-uri-requête(aa) est utilisé pour cette Dimension numérique. Il s’agit de la valeur de la dernière ligne pour un serveur donné, sous réserve que cs-uri-requête(k) ne soit pas vide. Cette dimension sert à indiquer si des profils sont en cours de retraitement. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de lignes de capacité</b> </td> 
   <td colname="col2"> Le champ cs-uri-requête(r) est utilisé pour cette Dimension numérique. Il s’agit de la valeur de la dernière ligne pour un serveur donné, sous réserve que cs-uri-requête(k) ne soit pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de capacité</b> </td> 
   <td colname="col2"> Le champ cs-uri-requête(n) est utilisé pour cette Dimension numérique. Il s’agit de la valeur de la dernière ligne pour un serveur donné, sous réserve que cs-uri-requête(k) ne soit pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nom commun</b> </td> 
   <td colname="col2"> Le champ sc-ur-requête(am) est utilisé pour cette Dimension simple. Il s’agit de la valeur de la valeur Dernier non vierge pour un serveur donné. Il affiche le nom commun des serveurs surveillés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite de la vérification des composants</b> </td> 
   <td colname="col2"> Le champ cs-uri-requête(v) est utilisé pour cette Dimension simple, c'est la valeur de la dernière ligne pour un serveur donné. Cette dimension vérifie les composants du serveur pour s’assurer qu’ils fonctionnent correctement. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Composants dans une erreur</b> </td> 
   <td colname="col2"> Une transformation Crossrows prend la valeur Last Row de cs-uri-requête(ao) et la copie dans le champ x-components-in-error. Cette dimension De plusieurs à plusieurs affiche tous les composants en erreur sur les serveurs surveillés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Environnement</b> </td> 
   <td colname="col2">La valeur cs-uri-requête(c) est utilisée pour l'ID d'Environnement. La dernière ligne d'un bloc est utilisée comme valeur de la dimension. Cette Dimension simple affiche l'Environnement d'exécution de vos serveurs (à condition qu'il soit correctement configuré). <p><p>Remarque :  Cette dimension est définie dans insight_monitor_agent.cfg. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimation des dekasecondes de balayage</b> </td> 
   <td colname="col2"> Le champ x-estimation-sweep-dekaseconds est utilisé dans cette Dimension numérique. Il s'agit du temps de balayage estimé des serveurs divisé par dix (résolution réduite de la mesure de balayage pour rendre la dimension plus raisonnable). <p><p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Hôte</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(b) est utilisée pour cette dimension. La valeur de la dimension Simple est la dernière ligne d’un bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernier ping</b> </td> 
   <td colname="col2"> x-last-ping est divisé par 10 (pour tenir compte des dimensions numériques). Le dernier ping est la dernière ligne d'un bloc donné et représente la dernière fois que l'agent de surveillance a consigné l'état du système. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Charge moyenne</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la dernière ligne pour la valeur cs-uri-requête(i) d’un serveur donné. Il est conditionné sur cs-uri-requête(k) ne pas être vide. Cette dimension permet de calculer la charge moyenne sur les serveurs du système surveillé. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de fichiers de la page mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la dernière ligne pour la valeur cs-uri-requête(o) d’un serveur donné. Il est conditionné sur cs-uri-requête(k) ne pas être vide. Cette dimension est utilisée pour calculer le pourcentage d’utilisation de la mémoire de fichier de page. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Total MégaBytes physiques de mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la dernière ligne pour la valeur cs-uri-requête(ag) d’un serveur donné. Il est conditionné sur cs-uri-requête(k) ne pas être vide. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de mémoire physique</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la dernière ligne pour la valeur cs-uri-requête(ag) d’un serveur donné. Il est conditionné sur cs-uri-requête(k) ne pas être vide. Cette dimension est utilisée pour calculer le pourcentage d'utilisation de la mémoire physique de chaque serveur. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de Requête de mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique qui utilise la dernière ligne pour la ou les requêtes cs-uri-com d’un serveur donné. Il est conditionné sur cs-uri-requête(k) ne pas être vide. Cette dimension est utilisée pour calculer le pourcentage d'utilisation de la mémoire de requête de chaque serveur. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connexions réseau</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la dernière ligne pour la valeur cs-uri-requête(q) d’un serveur donné. Il est conditionné sur cs-uri-requête(k) ne pas être vide. Elle est utilisée pour indiquer le nombre de connexions réseau disponibles pour un serveur donné. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Centisecondes de latence du sondage</b> </td> 
   <td colname="col2"> Cette dimension est utilisée pour calculer la latence du sondage. La valeur cs-uri-requête(m) est divisée par 10 pour réduire la taille de la dimension et copiée dans le champ x-poll-latency-centisecondes. Il s’agit d’une dimension numérique qui prend la dernière ligne pour un serveur donné. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite de la vérification rapide</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension simple créée à partir de la valeur cs-uri-requête(g) de la dernière ligne pour un serveur donné. Il est utilisé pour calculer la mesure de vérification rapide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage d'espace de base de données temporaire</b> </td> 
   <td colname="col2"> La dernière ligne de la valeur cs-uri-requête(an) est copiée dans le champ x-temp-db-space-pourcentage. Il s’agit d’une Dimension numérique utilisée pour calculer le pourcentage d’espace de base de données temporaire utilisé sur un serveur donné. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Version d’Insight</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(ab) est utilisée pour cette Dimension simple. Il s’agit de la valeur Dernier non vide pour un serveur. Cette option affiche la ou les versions du serveur de l’outil de données s’exécutant sur chaque serveur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Groupe</b> </td> 
   <td colname="col2"> Regroupement de mots qui vous donne une autre façon de filtrer le jeu de données résultant. <p>Remarque :  Cette dimension est définie dans insight_monitor_agent.cfg. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mesures</b> </td> 
   <td colname="col2"> Les listes suivantes concernent les mesures incluses dans le Profil de surveillance des Profils de l’outil de données et la manière dont elles sont dérivées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Capacité globale</b> </td> 
   <td colname="col2"> Il s’agit de la mesure Taille de la capacité deux fois plus la mesure Rangée de capacité divisée par 3. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Rangée de capacité</b> </td> 
   <td colname="col2"> Il s'agit de la somme du pourcentage de lignes de capacité pour chaque serveur divisé par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Taille de capacité</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage de capacité pour chaque serveur divisé par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Vérification du composant</b> </td> 
   <td colname="col2"> Il s'agit du nombre de serveurs sur lesquels la réussite de la vérification des composants est égale à un, divisé par le serveur sur lequel le service est DPU ou FSU, tous multipliés par 100 (pour en faire un pourcentage). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Disque "x"</b> </td> 
   <td colname="col2"> Les mesures Disque sont calculées en prenant la somme de leur pourcentage d'utilisation de disque pour chaque serveur, divisé par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimation des minutes de balayage</b> </td> 
   <td colname="col2"> Il s’agit de la somme des Dekaseconds de balayage estimés pour chaque serveur, divisée par la mesure Serveurs où l’écart de balayage estimé est supérieur à zéro, tous divisés par 6. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Heure du dernier ping</b> </td> 
   <td colname="col2"> Somme du dernier ping pour chaque bloc divisée par des blocs, puis multipliée par 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Load</b> </td> 
   <td colname="col2"> Il s’agit de la somme de la moyenne de charge pour chaque serveur, divisée par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fichier de page mémoire</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage de fichiers de la page de mémoire pour chaque serveur, divisée par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mémoire physique</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage physique de mémoire pour chaque serveur, divisée par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Requête de mémoire</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage de Requête de mémoire pour chaque serveur, divisée par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connexions réseau</b> </td> 
   <td colname="col2"> Il s'agit de la somme des connexions réseau pour chaque serveur divisée par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Latence du sondage en millisecondes</b> </td> 
   <td colname="col2"> Il s’agit de la somme des centisecondes de latence du sondage pour chaque serveur, divisée par la mesure Serveurs, qui sont toutes multipliées par 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Vérification rapide</b> </td> 
   <td colname="col2"> Il s’agit du nombre de serveurs sur lesquels la réussite de la vérification rapide est égale à un, divisé par la mesure Serveurs, qui sont tous multipliés par 100. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Serveurs</b> </td> 
   <td colname="col2"> Il s'agit de la somme d'un pour chaque serveur, ou du nombre total de serveurs surveillés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Base de données temporaire</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage d’espace de base de données temporaire pour chaque serveur, divisée par la mesure Serveurs. </td> 
  </tr> 
 </tbody> 
</table>
