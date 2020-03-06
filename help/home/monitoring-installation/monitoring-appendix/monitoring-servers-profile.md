---
description: Les dimensions suivantes peuvent être utilisées dans le profil d’état du serveur de l’outil de données.
solution: Analytics
title: Dimensions dans le profil d’état du serveur Outils de données
topic: Data workbench
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensions dans le profil d’état du serveur Outils de données{#dimensions-in-the-data-workbench-server-status-profile}

Les dimensions suivantes peuvent être utilisées dans le profil d’état du serveur de l’outil de données.

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Serveur</b> </td> 
   <td colname="col2"> Construit à partir du champ x-trackingid, cette dimension dénombrable représente les serveurs exécutant actuellement l’outil de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Version de l'agent</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(af) est utilisée pour cette dimension simple. Il s’agit de la valeur Dernier non vide pour un serveur. Vous affichez ainsi la date et l’heure de génération des versions de l’agent de surveillance en cours d’exécution. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tout retraitement de profil</b> </td> 
   <td colname="col2"> Le champ cs-uri-query(aa) est utilisé pour cette dimension numérique, il s’agit de la valeur de la dernière ligne pour un serveur donné, sous réserve que cs-uri-query(k) ne soit pas vide. Cette dimension sert à indiquer si des profils sont en cours de retraitement. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de lignes de capacité</b> </td> 
   <td colname="col2"> Le champ cs-uri-query(r) est utilisé pour cette dimension numérique, il s’agit de la valeur de la dernière ligne pour un serveur donné, sous réserve que cs-uri-query(k) ne soit pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de la taille de la capacité</b> </td> 
   <td colname="col2"> Le champ cs-uri-query(n) est utilisé pour cette dimension numérique, il s’agit de la valeur de la dernière ligne pour un serveur donné, sous réserve que cs-uri-query(k) ne soit pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nom commun</b> </td> 
   <td colname="col2"> Le champ sc-ur-query(am) est utilisé pour cette dimension simple. Il s’agit de la valeur de la valeur Last Nonblank pour un serveur donné. Il affiche le nom commun des serveurs surveillés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite du contrôle des composants</b> </td> 
   <td colname="col2"> Le champ cs-uri-query(v) est utilisé pour cette dimension simple. Il s’agit de la valeur de la dernière ligne pour un serveur donné. Cette dimension vérifie que les composants du serveur fonctionnent correctement. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Composants en erreur</b> </td> 
   <td colname="col2"> Une transformation Crossrows prend la valeur Dernière ligne de la requête cs-uri(ao) et la copie dans le champ x-components-in-error. Cette dimension de plusieurs à plusieurs affiche tous les composants en erreur sur les serveurs contrôlés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Environnement</b> </td> 
   <td colname="col2">La valeur cs-uri-query(c) est utilisée pour l’ID d’environnement. La dernière ligne d’un bloc est utilisée comme valeur pour la dimension. Cette dimension simple affiche l’environnement dans lequel vos serveurs sont exécutés (à condition qu’il soit correctement configuré). <p><p>Remarque :  Cette dimension est définie dans insight_monitor_agent.cfg. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimation des dekasecondes de balayage</b> </td> 
   <td colname="col2"> Le champ x-estimation-sweep-dekaseconds est utilisé dans cette dimension numérique. Il s’agit du temps de balayage estimé des serveurs divisé par dix (résolution réduite de la mesure de balayage pour rendre la dimension plus raisonnable). <p><p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(b) est utilisée pour cette dimension. La valeur de la dimension Simple est la dernière ligne d’un bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernier ping</b> </td> 
   <td colname="col2"> x-last-ping est divisé par 10 (pour tenir compte des contraintes de taille des dimensions numériques). Le dernier ping est la dernière ligne d'un bloc donné et représente la dernière fois que l'agent de surveillance a consigné l'intégrité du système. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Moyenne de charge</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la dernière ligne pour la valeur cs-uri-query(i) d’un serveur donné. Il est conditionné sur cs-uri-query(k) ne pas être vide. Cette dimension permet de calculer la charge moyenne sur les serveurs du système surveillé. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage du fichier de la page Mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la dernière ligne pour la valeur cs-uri-query(o) d’un serveur donné. Il est conditionné sur cs-uri-query(k) ne pas être vide. Cette dimension permet de calculer le pourcentage d’utilisation de la mémoire des fichiers de page. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Total MégaBytes physiques de mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la dernière ligne pour la valeur cs-uri-query(ag) d’un serveur donné. Il est conditionné sur cs-uri-query(k) ne pas être vide. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage physique de mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la dernière ligne pour la valeur cs-uri-query(ag) d’un serveur donné. Il est conditionné sur cs-uri-query(k) ne pas être vide. Cette dimension permet de calculer le pourcentage d’utilisation de la mémoire physique de chaque serveur. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de requête mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la dernière ligne pour la valeur cs-uri-query(s) d’un serveur donné. Il est conditionné sur cs-uri-query(k) ne pas être vide. Cette dimension permet de calculer le pourcentage d’utilisation de la mémoire de requête de chaque serveur. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connexions réseau</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la dernière ligne pour la valeur cs-uri-query(q) d’un serveur donné. Il est conditionné sur cs-uri-query(k) ne pas être vide. Elle est utilisée pour indiquer le nombre de connexions réseau disponibles pour un serveur donné. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Centisecondes de latence du sondage</b> </td> 
   <td colname="col2"> Cette dimension est utilisée pour calculer la latence du sondage. La valeur cs-uri-query(m) est divisée par 10 pour réduire la taille de la dimension et copiée dans le champ x-poll-latency-centiseconds. Il s’agit d’une dimension numérique qui prend la dernière ligne pour un serveur donné. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite de la vérification rapide</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension simple créée à partir de la valeur cs-uri-query(g) de la dernière ligne pour un serveur donné. Il est utilisé pour calculer la mesure de vérification rapide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage d’espace de base de données temporaire</b> </td> 
   <td colname="col2"> La dernière ligne de la valeur cs-uri-query(an) est copiée dans le champ x-temp-db-space-percent. Il s’agit d’une dimension numérique utilisée pour calculer le pourcentage d’espace de base de données temporaire utilisé sur un serveur donné. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Version d’Insight</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(ab) est utilisée pour cette dimension simple. Il s’agit de la valeur Dernier non vide pour un serveur. Cette option affiche la ou les versions du serveur de l’outil de données s’exécutant sur chaque serveur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Groupe</b> </td> 
   <td colname="col2"> Regroupement de mots qui vous donne une autre façon de filtrer le jeu de données résultant. <p>Remarque :  Cette dimension est définie dans insight_monitor_agent.cfg. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mesures</b> </td> 
   <td colname="col2"> Vous trouverez ci-dessous la liste des mesures incluses dans le profil de surveillance des profils de l’outil de données et la manière dont elles sont dérivées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Capacité globale</b> </td> 
   <td colname="col2"> Il s’agit de la mesure Taille de la capacité deux fois plus la mesure Rangée de capacité divisée par 3. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Rangée de capacité</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage de lignes de capacité pour chaque serveur divisé par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Taille de la capacité</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage de capacité pour chaque serveur divisé par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Vérification du composant</b> </td> 
   <td colname="col2"> Il s’agit du nombre de serveurs pour lesquels le succès de vérification des composants est égal à un, divisé par le serveur sur lequel le service est DPU ou FSU, le tout multiplié par 100 (pour en faire un pourcentage). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Disque "x"</b> </td> 
   <td colname="col2"> Les mesures Disque sont calculées en prenant la somme de leur pourcentage d'utilisation de disque pour chaque serveur, divisée par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimation des minutes de balayage</b> </td> 
   <td colname="col2"> Il s’agit de la somme des Dekasecondes de balayage estimées pour chaque serveur, divisée par la mesure Serveurs où l’estimation des dekasecondes de balayage est supérieure à zéro, toutes divisées par 6. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Heure du dernier ping</b> </td> 
   <td colname="col2"> Somme du dernier ping pour chaque bloc divisé par des blocs, puis multipliée par 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Load</b> </td> 
   <td colname="col2"> Il s’agit de la somme de la moyenne de charge pour chaque serveur, divisée par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fichier de page mémoire</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage de fichier de page de mémoire pour chaque serveur, divisée par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mémoire physique</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage physique de mémoire pour chaque serveur, divisé par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Requête mémoire</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage de requête de mémoire pour chaque serveur, divisée par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connexions réseau</b> </td> 
   <td colname="col2"> Il s’agit de la somme des connexions réseau pour chaque serveur divisée par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Latence du sondage en millisecondes</b> </td> 
   <td colname="col2"> Il s’agit de la somme des centisecondes de latence du sondage pour chaque serveur, divisée par la mesure Serveurs, qui sont toutes multipliées par 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Vérification rapide</b> </td> 
   <td colname="col2"> Il s’agit du nombre de serveurs pour lesquels la réussite de la vérification rapide est égale à un, divisé par la mesure Serveurs, qui est multiplié par 100. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Serveurs</b> </td> 
   <td colname="col2"> Il s’agit de la somme d’un pour chaque serveur ou du nombre total de serveurs surveillés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Base de données temporaire</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage d’espace de base de données temporaire pour chaque serveur, divisé par la mesure Serveurs. </td> 
  </tr> 
 </tbody> 
</table>

