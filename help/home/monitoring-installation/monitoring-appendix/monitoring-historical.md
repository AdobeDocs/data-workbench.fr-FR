---
description: Les dimensions suivantes peuvent être utilisées dans le profil historique des outils de données.
solution: Analytics
title: Dimensions dans le profil historique des outils de données
topic: Data workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensions dans le profil historique des outils de données{#dimensions-in-the-data-workbench-historic-profile}

Les dimensions suivantes peuvent être utilisées dans le profil historique des outils de données.

## Dimensions dans le profil historique des outils de données {#section-96f1b64f5cb84411b630f97f227d888d}

Les dimensions suivantes peuvent être utilisées dans le profil historique des outils de données.

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloc</b> </td> 
   <td colname="col2">Il s’agit du seul décompte dans cette configuration, c’est la racine pour toutes les dimensions. Un bloc peut être considéré comme un serveur. Il utilise le champ x-trackingid. <p>Remarque :  L’ID de bloc est un hachage du nom du serveur et du nom d’hôte. Il y aura donc environ un bloc par serveur et par profil. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension dénombrable construite à partir du compte à rebours. Chaque ligne de données du profil est un ping de l’agent de surveillance. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Critique d'alerte</b> </td> 
   <td colname="col2"> Dimension numérique générée à partir de la valeur cs-uri-query(ad). Il est construit au niveau Ping conditionné que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Alerte vers le bas</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-query(ac). Il est construit au niveau Ping, sous réserve que cs-uri-query(a) corresponde à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Avertissement d'alerte</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-query(ae). Il est construit au niveau Ping conditionné que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tout retraitement de profil</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-query(aa). Il est construit au niveau Ping, sous réserve que cs-uri-query(a) corresponde à "1" et cs-uriquery(k) ne soit pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>À compter du délai</b> </td> 
   <td colname="col2"> cs-uri-query(bi) est placé dans le champ x-as-of-delay-minutes et arrondi à la minute la plus proche. Il est construit au niveau Ping conditionné que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de lignes de capacité</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-query(r). Il est construit au niveau Ping, sous réserve que cs-uri-query(a) corresponde à "1" et cs-uriquery(k) ne soit pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de la taille de la capacité</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-query(n). Il est construit au niveau Ping, sous réserve que cs-uri-query(a) corresponde à "1" et cs-uriquery(k) ne soit pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite du contrôle des composants</b> </td> 
   <td colname="col2"> Dimension simple créée à partir de la valeur cs-uri-query(v). Il est construit au niveau Ping, et conditionné que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Composants en erreur</b> </td> 
   <td colname="col2"> cs-uri-query(ao) est divisé par le délimiteur "|" et copié dans le champ x-components-in-error. Plusieurs à plusieurs dimensions créées à partir du champ x-components-in-error. Construit au niveau du Ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondes de vérification détaillées</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-query(l). Il est construit au niveau Ping conditionné que cs-uri-query(k) n'est pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite de la vérification détaillée</b> </td> 
   <td colname="col2"> Dimension simple créée à partir de la valeur cs-uri-query(k). Il est construit au niveau Ping conditionné que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimension gigaoctets</b> </td> 
   <td colname="col2"> cs-uri-query(bc) est copié dans le champ x-dimension-gigaoctets. Le champ x-dimension-gigaoctets est utilisateur pour cette dimension simple, conditionné sur cs-uri-query(a) correspondant à "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage utilisé du disque "x"</b> </td> 
   <td colname="col2"> Ces dimensions numériques sont configurées à partir des valeurs cs-uri-query(ah, ai, aj, ak, al). Ils sont construits au niveau Ping et conditionnés sur cs-uri-query(a) correspond à "1" et cs-uri-query(k) n'est pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimation des dekasecondes de balayage</b> </td> 
   <td colname="col2"> Le champ x-estimation-sweep-dekaseconds est utilisé dans cette dimension numérique. Il s’agit du temps de balayage estimé des serveurs divisé par dix (résolution réduite de la mesure de balayage pour rendre la dimension plus raisonnable). <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MégaOctets d’entrée rapide par minute</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(bj) est utilisée pour cette dimension. La dernière ligne d’un bloc est utilisée comme valeur de la dimension. Si le jeu de données est en entrée rapide, cette valeur de dimension numérique affichera le Mo par minute auquel le système saisit les données. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fusion rapide MégaOctets par minute</b> </td> 
   <td colname="col2">La valeur cs-uri-query(bk) est utilisée pour cette dimension. La dernière ligne d’un bloc est utilisée comme valeur pour la dimension. Si le jeu de données est en fusion rapide, la valeur de cette dimension numérique affichera le Mo par minute auquel le système est en train de fusionner. <p><p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Champ GigaBytes</b> </td> 
   <td colname="col2">La valeur cs-uri-query(bg) est utilisée pour cette dimension. La valeur est divisée par 1 000 et arrondie au nombre entier le plus proche. La valeur de cette dimension numérique affiche l’espace utilisé par les champs dans le jeu de données. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Groupe</b> </td> 
   <td colname="col2"> Dimension simple créée au niveau Ping à partir de la valeur cs-uri-query(x). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(b) est utilisée pour cette dimension. La valeur de la dimension Simple est la dernière ligne d’un bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernier ping</b> </td> 
   <td colname="col2"> le champ x-unixtime est copié dans x-last-ping et divisé par 10 pour réduire la cardinalité. La dimension numérique est créée au niveau du bloc et utilise le champ x-last-ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Moyenne de charge</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la dernière ligne pour la valeur cs-uri-query(i) d’un serveur donné. Il est conditionné sur cs-uri-query(k) ne pas être vide. Cette dimension permet de calculer la charge moyenne sur les serveurs du système surveillé. <p><p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de lecture du journal</b> </td> 
   <td colname="col2">la valeur cs-uri-query(be) est utilisée pour cette dimension numérique, générée au niveau Ping. Cette dimension permet de calculer le pourcentage de journaux lus. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage du fichier de la page Mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique à l’aide de la valeur cs-uri-query(o), créée au niveau du ping. Il est conditionné sur cs-uri-query(k) n'étant pas vide, et cs-uri-query(a) correspondant à "1". Cette dimension permet de calculer le pourcentage d’utilisation de la mémoire des fichiers de page. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Total MégaBytes physiques de mémoire</b> </td> 
   <td colname="col2">Il s’agit d’une dimension numérique à l’aide de la valeur cs-uri-query(ag), créée au niveau du ping. Il est conditionné sur cs-uri-query(k) n'étant pas vide, et cs-uri-query(a) correspondant à "1. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage physique de mémoire</b> </td> 
   <td colname="col2">Il s’agit d’une dimension numérique à l’aide de la valeur cs-uri-query(ag), créée au niveau du ping. Il est conditionné sur cs-uri-query(k) n'étant pas vide, et cs-uri-query(a) correspondant à "1. Cette dimension permet de calculer le pourcentage d’utilisation de la mémoire physique de chaque serveur. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de requête mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la valeur cs-uri-query(s) au niveau du ping. Il est conditionné sur cs-uri-query(k) ne pas être vide et cs-uri-query(a) correspond à "1. Cette dimension permet de calculer le pourcentage d’utilisation de la mémoire de requête de chaque serveur. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connexions réseau</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique à l’aide de la valeur cs-uri-query(q) générée au niveau Ping. Il est conditionné sur cs-uri-query(k) ne pas être vide et cs-uri-query(a) correspond à "1. Elle est utilisée pour indiquer le nombre de connexions réseau disponibles pour un serveur donné. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lignes de sortie</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(bh) est divisée par 100000 et copiée dans le champ x-output-rows afin de réduire la taille de la dimension. X-output-rows est utilisé dans une dimension numérique créée au niveau du ping, à condition que cs-uri-query(a) corresponde à "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de type Ping</b> </td> 
   <td colname="col2"> Dimension simple créée à l’aide de la valeur cs-uri-query(a) au niveau du ping. Ceci montre quel type de Ping a été enregistré. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Centisecondes de latence du sondage</b> </td> 
   <td colname="col2">La valeur cs-uri-query(m) est divisée par 10 pour réduire la taille de la dimension et copiée dans le champ x-poll-latency-centiseconds. Il s’agit d’une dimension numérique générée au niveau Ping, sous réserve que cs-uri-query(k) ne soit pas vide et que cs-uri-query(a) corresponde à "1"/ Cette dimension est utilisée pour calculer la latence du sondage. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID du mode de traitement</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(bb) est utilisée pour cette dimension simple, créée au niveau du ping. Il est conditionné que cs-uri-query(bb) n'est pas vide, et que cs-uri-query(a) correspond à "2" Le mode de traitement ID permet de voir dans quel mode de traitement le système se trouve (Entrée rapide, Fusion rapide, Temps réel). <p>Remarque :  Cette dimension est masquée puis réexposée avec des valeurs conviviales dans le mode de traitement de la dimension côté client. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profil</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(ba) est utilisée pour cette dimension simple, elle est créée au niveau du ping. Cette dimension affiche le ou les nom(s) du ou des profil(s) actuellement surveillé(s). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondes de vérification rapide</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(h) est utilisée pour cette dimension numérique. Il est construit au niveau Ping conditionné que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite de la vérification rapide</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension simple créée à partir de la valeur cs-uri-query(g) générée au niveau Ping. Il est utilisé pour calculer la mesure de vérification rapide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de traitement en temps réel</b> </td> 
   <td colname="col2"> Dimension numérique à l’aide de la valeur cs-uri-query(t) créée au niveau du ping. Il est conditionné que cs-uri-query(a) corresponde à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Source la plus éloignée derrière</b> </td> 
   <td colname="col2"> Dimension simple créée à partir de la valeur cs-uri-query(bl) générée au niveau du ping. Cette dimension affiche la date du dernier contact avec une source de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage d’espace de base de données temporaire</b> </td> 
   <td colname="col2">Dimension numérique générée à l’aide de la valeur cs-uri-query(an), générée au niveau Ping. Il est conditionné que cs-uri-query(k) n'est pas vide, et cs-uri-query(a) correspond à "1". Il est utilisé pour calculer le pourcentage d’espace de base de données temporaire utilisé sur un serveur donné. <p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de transformation</b> </td> 
   <td colname="col2">la valeur cs-uri-query(bf) est utilisée pour cette dimension numérique. Il est construit au niveau du Ping. Cette dimension permet de calculer le pourcentage de transformation complète des données. <p><p>Remarque :  Cette dimension est masquée car elle n’est utile que lorsqu’elle est convertie en mesure. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Version des outils de données</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(ab) est utilisée pour cette dimension simple. Il est construit au niveau Ping et conditionné que cs-uri-query(ab) n'est pas vide, et cs-uri-query(a) correspond à "1". Cette option affiche la ou les versions du serveur de l’outil de données s’exécutant sur chaque serveur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Version majeure des outils de données</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(ab) est fractionnée et la valeur de la version principale est copiée dans le champ x-insight-version-major. Il s’agit d’une dimension simple créée au niveau Ping et conditionnée que x-insight-version-major n’est pas vide et que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->

