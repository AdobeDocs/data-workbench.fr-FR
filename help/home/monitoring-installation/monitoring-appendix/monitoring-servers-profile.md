---
description: Les dimensions suivantes peuvent être utilisées dans le profil du statut du serveur de Data Workbench.
title: Dimensions dans le profil du statut du serveur de Data Workbench
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Dimensions dans le profil du statut du serveur de Data Workbench{#dimensions-in-the-data-workbench-server-status-profile}

Les dimensions suivantes peuvent être utilisées dans le profil du statut du serveur de Data Workbench.

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Serveur</b> </td> 
   <td colname="col2"> Créée à partir du champ x-trackingid , cette dimension dénombrable représente les serveurs exécutant actuellement Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Version de l’agent</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(af) est utilisée pour cette Dimension simple. Il s’agit de la valeur Last Nonblank pour un serveur. Cette option affiche la date et l’heure de génération de la ou des versions de l’agent de surveillance en cours d’exécution. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tout retraitement de profil</b> </td> 
   <td colname="col2"> Le champ cs-uri-query(aa) est utilisé pour cette Dimension numérique. Il s’agit de la valeur de la Dernière ligne pour un serveur donné, la condition cs-uri-query(k) n’est pas vide. Cette dimension sert à indiquer si des profils sont en retraitement. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de la ligne de capacité</b> </td> 
   <td colname="col2"> Le champ cs-uri-query(r) est utilisé pour cette Dimension numérique. Il s’agit de la valeur de la Dernière ligne pour un serveur donné, la condition cs-uri-query(k) n’est pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Taille de la capacité, pourcentage</b> </td> 
   <td colname="col2"> Le champ cs-uri-query(n) est utilisé pour cette Dimension numérique. Il s’agit de la valeur de la Dernière ligne pour un serveur donné, la condition cs-uri-query(k) n’est pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nom commun</b> </td> 
   <td colname="col2"> Le champ sc-ur-query(am) est utilisé pour cette Dimension Simple. Il s’agit de la valeur de la valeur Dernière valeur non vide pour un serveur donné. Il affiche le Nom commun des serveurs surveillés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite du contrôle des composants</b> </td> 
   <td colname="col2"> Le champ cs-uri-query(v) est utilisé pour cette Dimension Simple. Il s’agit de la valeur de la Dernière ligne pour un serveur donné. Cette dimension vérifie que les composants du serveur fonctionnent correctement. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Composants en erreur</b> </td> 
   <td colname="col2"> Une transformation de lignes croisées prend la valeur Dernière ligne de la requête cs-uri-query(ao) et la copie dans le champ x-components-in-error . Cette dimension De plusieurs à plusieurs affiche les composants en erreur sur les serveurs surveillés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Environnement</b> </td> 
   <td colname="col2">La valeur cs-uri-query(c) est utilisée pour l’ID d’environnement. La dernière ligne d’un bloc est utilisée comme valeur de la dimension. Cette Dimension simple affiche l’environnement dans lequel s’exécutent vos serveurs (à condition qu’il soit correctement configuré). <p><p>Remarque :  Cette dimension est définie dans insight_monitor_agent.cfg. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimation des secondes de balayage</b> </td> 
   <td colname="col2"> Le champ x-estimated-sweep-dekaseconds est utilisé dans cette Dimension numérique. Il s’agit de la durée estimée du balayage des serveurs divisée par dix (résolution réduite de la mesure du balayage pour rendre la dimension plus raisonnable). <p><p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Hôte</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(b) est utilisée pour cette dimension. La valeur de la dimension Simple est la Dernière ligne d’un bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernier ping</b> </td> 
   <td colname="col2"> x-last-ping est divisé par 10 (pour tenir compte des contraintes de taille des dimensions numériques). Le dernier ping est la dernière ligne d’un bloc donné et il représente la dernière fois que l’agent de surveillance a consigné l’intégrité du système. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Load Average</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique qui utilise la Dernière ligne pour la valeur cs-uri-query(i) d’un serveur donné. Elle est conditionnée sur le fait que cs-uri-query(k) ne soit pas vide. Cette dimension permet de calculer la charge moyenne sur les serveurs du système surveillé. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de fichier de page mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique qui utilise la Dernière ligne pour la valeur cs-uri-query(o) d’un serveur donné. Elle est conditionnée sur le fait que cs-uri-query(k) ne soit pas vide. Cette dimension est utilisée pour calculer le pourcentage d’utilisation de la mémoire de fichier de page. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nombre total de méga-octets physiques de la mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique qui utilise la Dernière ligne pour la valeur cs-uri-query(ag) d’un serveur donné. Elle est conditionnée sur le fait que cs-uri-query(k) ne soit pas vide. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de mémoire physique</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique qui utilise la Dernière ligne pour la valeur cs-uri-query(ag) d’un serveur donné. Elle est conditionnée sur le fait que cs-uri-query(k) ne soit pas vide. Cette dimension est utilisée pour calculer le pourcentage d’utilisation de la mémoire physique de chaque serveur. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de requête mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique qui utilise la Dernière ligne pour la ou les valeurs cs-uri-query(s) d’un serveur donné. Elle est conditionnée sur le fait que cs-uri-query(k) ne soit pas vide. Cette dimension est utilisée pour calculer le pourcentage de l’utilisation de la mémoire de requête de chaque serveur. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connexions réseau</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique qui utilise la Dernière ligne pour la valeur cs-uri-query(q) d’un serveur donné. Elle est conditionnée sur le fait que cs-uri-query(k) ne soit pas vide. Elle permet d’afficher le nombre de connexions réseau disponibles pour un serveur donné. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Centisecondes de latence du sondage</b> </td> 
   <td colname="col2"> Cette dimension est utilisée pour calculer la latence du sondage. La valeur cs-uri-query(m) est divisée par 10 pour réduire la taille de dimension et copiée dans le champ x-poll-latency-centiseconds . Il s’agit d’une dimension numérique qui prend la dernière ligne pour un serveur donné. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite du contrôle rapide</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension simple créée à partir de la valeur cs-uri-query(g) de la Dernière ligne pour un serveur donné. Il est utilisé pour calculer la mesure de vérification rapide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage d’espace de base de données temporaire</b> </td> 
   <td colname="col2"> La dernière ligne de la valeur cs-uri-query(an) est copiée dans le champ x-temp-db-space-percent. Il s’agit d’une Dimension numérique utilisée pour calculer le pourcentage de l’espace de base de données temporaire utilisé sur un serveur donné. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Version d’Insight</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(ab) est utilisée pour cette Dimension simple. Il s’agit de la valeur Last Nonblank pour un serveur. Cette option affiche la ou les versions du serveur Data Workbench exécuté sur chaque serveur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Groupe</b> </td> 
   <td colname="col2"> Mot de groupement qui vous donne une autre manière de filtrer le jeu de données obtenu. <p>Remarque :  Cette dimension est définie dans insight_monitor_agent.cfg. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mesures</b> </td> 
   <td colname="col2"> Vous trouverez ci-dessous la liste des mesures incluses dans le profil de surveillance de profil de Data Workbench et la manière dont elles sont dérivées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Capacité globale</b> </td> 
   <td colname="col2"> Il s’agit de la mesure Taille de la capacité deux fois plus la mesure Ligne de capacité divisée par 3. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ligne de capacité</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage de la ligne de capacité pour chaque serveur divisé par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Taille de la capacité</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage de taille de capacité pour chaque serveur divisé par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Vérification du composant</b> </td> 
   <td colname="col2"> Il s’agit du nombre de serveurs sur lesquels la vérification de composant est égale à un, divisé par le serveur sur lequel le service est DPU ou FSU, tous multipliés par 100 (pour en faire un pourcentage). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Disque "x"</b> </td> 
   <td colname="col2"> Les mesures Disque sont calculées en prenant la somme de leur pourcentage d’utilisation du disque pour chaque serveur, divisé par la mesure Serveurs . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nombre estimé de minutes de balayage</b> </td> 
   <td colname="col2"> Il s’agit de la somme des Dekasecondes de balayage estimées pour chaque serveur, divisée par la mesure Serveurs où l’écart de balayage estimé est supérieur à zéro, tous divisés par 6. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernière heure de ping</b> </td> 
   <td colname="col2"> Somme du dernier ping pour chaque bloc divisé par des blocs, puis multipliée par 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Load</b> </td> 
   <td colname="col2"> Il s’agit de la somme de la moyenne de chargement pour chaque serveur, divisée par la mesure Serveurs . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fichier de page mémoire</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage de fichier de page mémoire pour chaque serveur, divisée par la mesure Serveurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mémoire physique</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage physique de la mémoire pour chaque serveur, divisé par la mesure Serveurs . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Requête mémoire</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage de requête mémoire pour chaque serveur, divisée par la mesure Serveurs . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connexions réseau</b> </td> 
   <td colname="col2"> Il s’agit de la somme des connexions réseau pour chaque serveur divisée par la mesure Serveurs . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Latence du sondage, millisecondes</b> </td> 
   <td colname="col2"> Il s’agit de la somme des centisecondes de latence du sondage pour chaque serveur, divisée par la mesure Serveurs, qui sont tous multipliés par 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Vérification rapide</b> </td> 
   <td colname="col2"> Il s’agit du nombre de serveurs pour lesquels la réussite de la vérification rapide est égale à un, divisé par la mesure Serveurs, qui est tous multiplié par 100. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Serveurs</b> </td> 
   <td colname="col2"> Il s’agit de la somme d’un pour chaque serveur ou du nombre total de serveurs surveillés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Temp DB</b> </td> 
   <td colname="col2"> Il s’agit de la somme du pourcentage d’espace de base de données temporaire pour chaque serveur, divisé par la mesure Serveurs. </td> 
  </tr> 
 </tbody> 
</table>
