---
description: Les dimensions suivantes peuvent être utilisées dans le profil d’état du profil de Data Workbench.
title: Dimensions dans le profil du statut du profil de Data Workbench
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Dimensions dans le profil du statut du profil de Data Workbench{#dimensions-in-the-data-workbench-profile-status-profile}

{{eol}}

Les dimensions suivantes peuvent être utilisées dans le profil d’état du profil de Data Workbench.

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloc</b> </td> 
   <td colname="col2"> Il s’agit du seul décompte dans cette configuration et de la racine pour toutes les dimensions. Un bloc peut être considéré comme un serveur. Il utilise le champ x-trackingid . L’ID de bloc est un hachage du nom du serveur plus le nom d’hôte, il y aura donc environ un bloc par serveur et par profil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>À partir du délai</b> </td> 
   <td colname="col2"> cs-uri-query(bi) est placé dans le champ x-as-of-delay-minutes et arrondi à la minute la plus proche. À partir du délai des minutes est une dimension numérique qui prend la dernière ligne de x-as-of-delay-minutes pour un bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Environnement</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(c) est utilisée pour l’ID d’environnement. La dernière ligne d’un bloc est utilisée comme valeur de la dimension. Cette Dimension simple affiche l’environnement dans lequel s’exécutent vos serveurs (à condition qu’il soit correctement configuré). <p>Cela peut être défini dans le fichier insight_monitor_agent.cfg . </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MégaOctets d’entrée rapide par minute</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(bj) est utilisée pour cette dimension. La dernière ligne d’un bloc est utilisée comme valeur de la dimension. Si le jeu de données est en entrée rapide, cette valeur de la Dimension numérique affichera le Mo par minute auquel le système saisit des données. <p>Remarque : Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fusion rapide : méga octets par minute</b> </td> 
   <td colname="col2">La valeur cs-uri-query(bk) est utilisée pour cette dimension. La dernière ligne d’un bloc est utilisée comme valeur de la dimension. Si le jeu de données est en fusion rapide Cette valeur de la Dimension numérique affiche le Mo par minute auquel le système est en train de fusionner. <p>Remarque : Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Champ GigaBytes</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(bg) est utilisée pour cette dimension. La valeur est divisée par 1 000 et arrondie au nombre entier le plus proche. La valeur de cette Dimension numérique affiche l’espace utilisé par les champs du jeu de données. <p>Remarque : Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Hôte</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(b) est utilisée pour cette dimension. La valeur de la dimension Simple est la Dernière ligne d’un bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernier ping</b> </td> 
   <td colname="col2">x-last-ping est divisé par 10 (pour tenir compte des contraintes de taille des dimensions numériques). Le dernier ping est la dernière ligne d’un bloc donné et il représente la dernière fois que l’agent de surveillance a consigné l’intégrité du système. <p>Remarque : Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de lecture du journal</b> </td> 
   <td colname="col2">la valeur cs-uri-query(be) est utilisée pour cette dimension numérique. Il s’agit de la dernière ligne d’un bloc donné. Cette dimension est utilisée pour calculer le pourcentage de journaux en cours de lecture. <p>Remarque : Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Identifiant du mode de traitement</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(bb) est utilisée pour cette Dimension simple. Il s’agit de la Dernière ligne d’un bloc donné. L’identifiant du mode de traitement permet de voir dans quel mode de traitement le système se trouve (entrée rapide, fusion rapide, temps réel). <p>Remarque : Cette dimension est masquée puis réexposée avec des valeurs conviviales en mode de traitement de dimension côté client. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Traitement bloqué</b> </td> 
   <td colname="col2"> Le champ x-processing-stalled est créé à l’aide de différentes conditions pour indiquer si le profil est en cours d’exécution ou non. C'est une dimension simple. <p>Remarque : Cette dimension fonctionne mieux lorsqu’il existe un grand nombre de journaux d’entrée à répartir équitablement entre les DPU. Si, par exemple, un seul fichier volumineux est chargé par jour, Data Workbench peut sembler "bloquer" pendant une heure ou plus, ce qui entraîne une lecture fausse positive de cette dimension. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profil</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(ba) est utilisée pour cette Dimension simple. Cette dimension affiche le ou les noms des profils actuellement surveillés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>La source la plus éloignée derrière</b> </td> 
   <td colname="col2"> La dernière ligne de cs-uri-query(bl) est copiée dans le champ x-source-le-plus-arrière. La Dimension simple utilise la Dernière ligne pour un bloc donné. Cette dimension affiche la date du dernier contact avec une source de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de transformation</b> </td> 
   <td colname="col2"> la valeur cs-uri-query(bf) est utilisée pour cette dimension numérique. Il s’agit de la dernière ligne d’un bloc donné. Cette dimension est utilisée pour calculer le pourcentage de transformation complète des données. <p>Remarque : Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensions Heure</b> </td> 
   <td colname="col2"> Heure, Jour, Semaine, Mois, Heure du jour et Jour de la semaine sont tous dérivés du champ d’horodatage. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Groupe</b> </td> 
   <td colname="col2"> Mot de groupement qui vous donne une autre manière de filtrer le jeu de données obtenu. Défini dans le fichier insight_monitor_agent.cfg . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mesures</b> </td> 
   <td colname="col2"> Vous trouverez ci-dessous la liste des mesures incluses dans le profil de surveillance de profil de Data Workbench et la manière dont elles sont dérivées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>À Compter Du Délai</b> </td> 
   <td colname="col2"> Cette mesure correspond à la somme des minutes "À partir du délai" pour chaque bloc, puis divisée par la mesure Blocs . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Délai En Secondes</b> </td> 
   <td colname="col2"> Cette mesure correspond à la somme des secondes de délai pour chaque bloc et divisée par le nombre total de blocs. (À partir du délai de Dimension en secondes non configuré prêt à l’emploi) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Blocs</b> </td> 
   <td colname="col2"> Additionnez un pour chaque bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MB d’entrée rapide par minute</b> </td> 
   <td colname="col2"> La somme des méga-octets d’entrée rapide par minute pour chaque bloc, divisée par le nombre de blocs lorsque la valeur MegaBytes par minute d’entrée rapide est supérieure à zéro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fusion rapide Mo par minute</b> </td> 
   <td colname="col2"> La somme des méga-octets de fusion rapide par minute pour chaque bloc divisé par le nombre de blocs lorsque la fusion rapide des méga-octets par minute est supérieure à zéro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Champ GigaBytes</b> </td> 
   <td colname="col2"> Somme des gigaoctets de champ pour chaque bloc divisé par la mesure Blocs . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernier âge du ping</b> </td> 
   <td colname="col2"> À Partir De L’Heure Moins L’Heure Du Dernier Ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernière heure de ping</b> </td> 
   <td colname="col2"> Somme du dernier ping pour chaque bloc divisé par des blocs, puis multipliée par 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lecture du journal</b> </td> 
   <td colname="col2"> Lorsque le pourcentage de lecture du journal est supérieur à zéro, la lecture du journal est la somme du pourcentage de lecture du journal pour chaque bloc, divisé par la mesure Blocs, qui est divisée par 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Traitement bloqué</b> </td> 
   <td colname="col2"> Somme de la Dimension Traitement bloqué pour chaque bloc, divisée par la mesure Blocs . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Transformation</b> </td> 
   <td colname="col2"> Somme du pourcentage de transformation pour chaque bloc divisé par la mesure Blocs lorsque le pourcentage de transformation est supérieur à zéro, le tout divisé par 10. </td> 
  </tr> 
 </tbody> 
</table>
