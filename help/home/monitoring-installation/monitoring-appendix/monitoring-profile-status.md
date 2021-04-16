---
description: Les dimensions suivantes peuvent être utilisées dans le profil d’état du Profil de l’outil de données.
title: Dimensions dans le profil du statut du profil de Data Workbench
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Dimensions dans le profil du statut du profil de Data Workbench{#dimensions-in-the-data-workbench-profile-status-profile}

Les dimensions suivantes peuvent être utilisées dans le profil d’état du Profil de l’outil de données.

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloc</b> </td> 
   <td colname="col2"> Il s’agit du seul décompte dans cette configuration et il existe comme racine pour toutes les dimensions. Un bloc peut être considéré comme un serveur. Il utilise le champ x-trackingid. L'ID de bloc est un hachage du nom du serveur et du nom d'hôte, il y aura donc environ un bloc par serveur par profil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>À compter du délai</b> </td> 
   <td colname="col2"> cs-uri-requête(bi) est placé dans le champ x-as-of-delay-minutes et arrondi à la minute la plus proche. En ce qui concerne les minutes de délai, il s’agit d’une dimension numérique qui prend la dernière ligne de x-as-of-delay-minutes pour un bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Environnement</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(c) est utilisée pour l'ID d'Environnement. La dernière ligne d'un bloc est utilisée comme valeur de la dimension. Cette Dimension simple affiche l'Environnement d'exécution de vos serveurs (à condition qu'il soit correctement configuré). <p>Cette variable peut être définie dans le fichier insight_monitor_agent.cfg. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MégaBytes d’entrée rapide par minute</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(bj) est utilisée pour cette dimension. La dernière ligne d'un bloc est utilisée comme valeur de la dimension. Si le jeu de données est en entrée rapide, cette valeur de Dimension numérique affichera le Mo par minute auquel le système saisit les données. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fusion rapide MégaBytes par minute</b> </td> 
   <td colname="col2">La valeur cs-uri-requête(bk) est utilisée pour cette dimension. La dernière ligne d'un bloc est utilisée comme valeur de la dimension. Si le jeu de données est en fusion rapide Cette valeur de Dimension numérique affiche le Mo par minute auquel le système est en train de fusionner. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Champ GigaBytes</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(bg) est utilisée pour cette dimension. La valeur est divisée par 1 000 et arrondie au nombre entier le plus proche. Cette valeur de Dimension numérique affiche l’espace utilisé par les champs dans le jeu de données. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Hôte</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(b) est utilisée pour cette dimension. La valeur de la dimension Simple est la dernière ligne d’un bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernier ping</b> </td> 
   <td colname="col2">x-last-ping est divisé par 10 (pour tenir compte des dimensions numériques). Le dernier ping est la dernière ligne d'un bloc donné et représente la dernière fois que l'agent de surveillance a consigné l'état du système. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de lecture du journal</b> </td> 
   <td colname="col2">la valeur cs-uri-requête(be) est utilisée pour cette dimension numérique. Il s’agit de la dernière ligne d’un bloc donné. Cette dimension est utilisée pour calculer le pourcentage de journaux lus. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de mode de traitement</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(bb) est utilisée pour cette Dimension simple. Il s’agit de la dernière ligne d’un bloc donné. Le mode de traitement ID permet de déterminer le mode de traitement du système (Entrée rapide, Fusion rapide, Temps réel). <p>Remarque :  Cette dimension est masquée puis réexposée avec des valeurs conviviales dans le mode de traitement de la dimension côté client. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Traitement bloqué</b> </td> 
   <td colname="col2"> Le champ bloqué par le traitement X est créé dans différentes conditions pour indiquer si le profil est en cours d’exécution ou non. C'est une dimension simple. <p>Remarque :  Cette dimension fonctionne mieux lorsqu’il existe un grand nombre de journaux d’entrée à répartir équitablement entre les unités de traitement de données. S’il n’existe, par exemple, qu’un seul fichier volumineux chargé par jour, les outils de données peuvent apparaître comme "bloqués" pendant une heure ou plus, ce qui entraîne une lecture fausse positive de cette dimension. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profil</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(ba) est utilisée pour cette Dimension simple. Cette dimension affiche le ou les noms des profils actuellement surveillés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Source la plus éloignée derrière</b> </td> 
   <td colname="col2"> La dernière ligne de cs-uri-requête(bl) est copiée dans le champ x-source-le-plus-arrière. La Dimension simple utilise la dernière ligne pour un bloc donné. Cette dimension affiche la date du dernier contact avec une source de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de transformation</b> </td> 
   <td colname="col2"> la valeur cs-uri-requête(bf) est utilisée pour cette dimension numérique. Il s’agit de la dernière ligne d’un bloc donné. Cette dimension est utilisée pour calculer le pourcentage de transformation complète des données. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensions Heure</b> </td> 
   <td colname="col2"> L’heure, le jour, la semaine, le mois, l’heure du jour et le jour de la semaine sont tous dérivés du champ d’horodatage. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Groupe</b> </td> 
   <td colname="col2"> Regroupement de mots qui vous donne une autre façon de filtrer le jeu de données résultant. Défini dans le fichier insight_monitor_agent.cfg. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mesures</b> </td> 
   <td colname="col2"> Les listes suivantes concernent les mesures incluses dans le Profil de surveillance des Profils de l’outil de données et la manière dont elles sont dérivées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>À Compter Du Délai</b> </td> 
   <td colname="col2"> Cette mesure correspond à la somme des minutes de délai A partir de chaque bloc, puis divisée par la mesure Blocs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>En Secondes De Retard</b> </td> 
   <td colname="col2"> Cette mesure correspond à la somme des secondes de délai pour chaque bloc, divisée par le nombre total de blocs. (À partir de la Dimension des secondes de délai non configurée en standard) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Blocs</b> </td> 
   <td colname="col2"> Somme d'un pour chaque bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Entrée rapide Mo par minute</b> </td> 
   <td colname="col2"> La somme des méga-octets d'entrée rapide par minute pour chaque bloc divisée par le nombre de blocs lorsque la valeur MégaBytes d'entrée rapide par minute est supérieure à zéro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fusion rapide Mo par minute</b> </td> 
   <td colname="col2"> La somme des méga-octets de fusion rapide par minute pour chaque bloc divisée par le nombre de blocs lorsque la fusion rapide des méga-octets par minute est supérieure à zéro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Champ GigaBytes</b> </td> 
   <td colname="col2"> Somme en gigaoctets de champ pour chaque bloc divisée par la mesure Blocs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernier âge du passage</b> </td> 
   <td colname="col2"> À Partir De L’Heure Moins L’Heure Du Dernier Ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Heure du dernier ping</b> </td> 
   <td colname="col2"> Somme du dernier ping pour chaque bloc divisée par des blocs, puis multipliée par 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lecture du journal</b> </td> 
   <td colname="col2"> Lorsque le pourcentage de lecture du journal est supérieur à zéro, la lecture du journal est la somme du pourcentage de lecture du journal pour chaque bloc, divisée par la mesure Blocs, qui est divisée par 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Traitement bloqué</b> </td> 
   <td colname="col2"> Somme de la Dimension de blocage de traitement pour chaque bloc, divisée par la mesure Blocs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Transformation</b> </td> 
   <td colname="col2"> Somme du pourcentage de transformation pour chaque bloc divisée par la mesure Blocs, lorsque le pourcentage de transformation est supérieur à zéro, le tout divisé par 10. </td> 
  </tr> 
 </tbody> 
</table>
