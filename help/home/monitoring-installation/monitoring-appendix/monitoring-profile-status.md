---
description: Les dimensions suivantes peuvent être utilisées dans le profil d’état du profil de l’outil de données.
solution: Analytics
title: Dimensions dans le profil d’état du profil des outils de données
topic: Data workbench
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensions dans le profil d’état du profil des outils de données{#dimensions-in-the-data-workbench-profile-status-profile}

Les dimensions suivantes peuvent être utilisées dans le profil d’état du profil de l’outil de données.

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloc</b> </td> 
   <td colname="col2"> Il s’agit du seul décompte dans cette configuration et il existe comme racine pour toutes les dimensions. Un bloc peut être considéré comme un serveur. Il utilise le champ x-trackingid. L’ID de bloc est un hachage du nom du serveur et du nom d’hôte. Il y aura donc environ un bloc par serveur et par profil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>À compter du délai</b> </td> 
   <td colname="col2"> cs-uri-query(bi) est placé dans le champ x-as-of-delay-minutes et arrondi à la minute la plus proche. A partir du délai minutes est une dimension numérique qui prend la dernière ligne de x-as-of-delay-minutes pour un bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Environnement</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(c) est utilisée pour l’ID d’environnement. La dernière ligne d’un bloc est utilisée comme valeur pour la dimension. Cette dimension simple affiche l’environnement dans lequel vos serveurs sont exécutés (à condition qu’il soit correctement configuré). <p>Cette variable peut être définie dans le fichier insight_monitor_agent.cfg. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MégaOctets d’entrée rapide par minute</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(bj) est utilisée pour cette dimension. La dernière ligne d’un bloc est utilisée comme valeur de la dimension. Si le jeu de données est en entrée rapide, cette valeur de dimension numérique affichera le Mo par minute auquel le système saisit les données. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fusion rapide MégaOctets par minute</b> </td> 
   <td colname="col2">La valeur cs-uri-query(bk) est utilisée pour cette dimension. La dernière ligne d’un bloc est utilisée comme valeur pour la dimension. Si le jeu de données est en fusion rapide, la valeur de cette dimension numérique affichera le Mo par minute auquel le système est en train de fusionner. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Champ GigaBytes</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(bg) est utilisée pour cette dimension. La valeur est divisée par 1 000 et arrondie au nombre entier le plus proche. La valeur de cette dimension numérique affiche l’espace utilisé par les champs dans le jeu de données. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(b) est utilisée pour cette dimension. La valeur de la dimension Simple est la dernière ligne d’un bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernier ping</b> </td> 
   <td colname="col2">x-last-ping est divisé par 10 (pour tenir compte des contraintes de taille des dimensions numériques). Le dernier ping est la dernière ligne d'un bloc donné et représente la dernière fois que l'agent de surveillance a consigné l'intégrité du système. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de lecture du journal</b> </td> 
   <td colname="col2">la valeur cs-uri-query(be) est utilisée pour cette dimension numérique. Il s’agit de la dernière ligne d’un bloc donné. Cette dimension permet de calculer le pourcentage de journaux lus. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID du mode de traitement</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(bb) est utilisée pour cette dimension simple. Il s’agit de la dernière ligne d’un bloc donné. L’ID de mode de traitement permet de déterminer le mode de traitement du système (entrée rapide, fusion rapide, temps réel). <p>Remarque :  Cette dimension est masquée puis réexposée avec des valeurs conviviales dans le mode de traitement de la dimension côté client. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Traitement bloqué</b> </td> 
   <td colname="col2"> Le champ bloqué par le traitement X est créé dans diverses conditions pour indiquer si le profil est en cours d’exécution ou non. C'est une dimension simple. <p>Remarque :  Cette dimension fonctionne mieux lorsqu’il existe un grand nombre de journaux d’entrée à répartir équitablement entre les unités de traitement de données. S’il n’y a, par exemple, qu’un seul fichier volumineux chargé par jour, les outils de données peuvent apparaître comme "bloqués" pendant une heure ou plus, ce qui entraîne une lecture fausse et positive de cette dimension. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profil</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(ba) est utilisée pour cette dimension simple. Cette dimension affiche le ou les noms des profils actuellement contrôlés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Source la plus éloignée derrière</b> </td> 
   <td colname="col2"> La dernière ligne de cs-uri-query(bl) est copiée dans le champ x-source-le-derrière. La dimension simple utilise la dernière ligne pour un bloc donné. Cette dimension affiche la date du dernier contact avec une source de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de transformation</b> </td> 
   <td colname="col2"> la valeur cs-uri-query(bf) est utilisée pour cette dimension numérique. Il s’agit de la dernière ligne d’un bloc donné. Cette dimension permet de calculer le pourcentage de transformation complète des données. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensions Heure</b> </td> 
   <td colname="col2"> Heure, Jour, Semaine, Mois, Heure du jour et Jour de la semaine sont tous dérivés du champ d’horodatage X. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Groupe</b> </td> 
   <td colname="col2"> Regroupement de mots qui vous donne une autre façon de filtrer le jeu de données résultant. Défini dans le fichier insight_monitor_agent.cfg. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mesures</b> </td> 
   <td colname="col2"> Vous trouverez ci-dessous la liste des mesures incluses dans le profil de surveillance des profils de l’outil de données et la manière dont elles sont dérivées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>À Compter Du Délai</b> </td> 
   <td colname="col2"> Cette mesure correspond à la somme des minutes A partir du délai pour chaque bloc, puis divisée par la mesure Blocs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>En Secondes De Retard</b> </td> 
   <td colname="col2"> Cette mesure correspond à la somme des secondes de délai pour chaque bloc et divisée par le nombre total de blocs. (À compter du délai en secondes, la dimension n’est pas configurée en standard) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Blocs</b> </td> 
   <td colname="col2"> 1 pour chaque bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Entrée rapide Mo par minute</b> </td> 
   <td colname="col2"> Somme des méga-octets d’entrée rapide par minute pour chaque bloc divisée par le nombre de blocs lorsque la valeur Méga-octets d’entrée rapide par minute est supérieure à zéro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fusion rapide Mo par minute</b> </td> 
   <td colname="col2"> La somme des méga-octets de fusion rapide par minute pour chaque bloc divisé par le nombre de blocs lorsque la fusion rapide des méga-octets par minute est supérieure à zéro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Champ GigaBytes</b> </td> 
   <td colname="col2"> Somme en gigaoctets de champ pour chaque bloc divisée par la mesure Blocs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernier âge du passage</b> </td> 
   <td colname="col2"> À Partir Du Temps Moins L’Heure Du Dernier Ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Heure du dernier ping</b> </td> 
   <td colname="col2"> Somme du dernier ping pour chaque bloc divisé par des blocs, puis multipliée par 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lecture du journal</b> </td> 
   <td colname="col2"> Lorsque le pourcentage de lecture du journal est supérieur à zéro, le pourcentage de lecture du journal est la somme du pourcentage de lecture du journal pour chaque bloc, divisé par la mesure Blocs, qui est divisé par 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Traitement bloqué</b> </td> 
   <td colname="col2"> Somme de la dimension Traiter bloquée pour chaque bloc, divisée par la mesure Blocs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Transformation</b> </td> 
   <td colname="col2"> Somme du pourcentage de transformation pour chaque bloc divisé par la mesure Blocs, lorsque le pourcentage de transformation est supérieur à zéro, le tout divisé par 10. </td> 
  </tr> 
 </tbody> 
</table>

