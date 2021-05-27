---
description: Les dimensions suivantes peuvent être utilisées dans le profil historique de Data Workbench.
title: Dimensions dans le profil historique de Data Workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
exl-id: 9df1f317-a985-4132-b32e-f2263e0c23b2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 1%

---

# Dimensions dans le profil historique de Data Workbench{#dimensions-in-the-data-workbench-historic-profile}

Les dimensions suivantes peuvent être utilisées dans le profil historique de Data Workbench.

## Dimensions dans le profil historique de Data Workbench {#section-96f1b64f5cb84411b630f97f227d888d}

Les dimensions suivantes peuvent être utilisées dans le profil historique de Data Workbench.

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloc</b> </td> 
   <td colname="col2">Il s’agit du seul décompte dans cette configuration. Il s’agit de la racine de toutes les dimensions. Un bloc peut être considéré comme un serveur. Il utilise le champ x-trackingid . <p>Remarque :  L’ID de bloc est un hachage du nom du serveur plus le nom d’hôte, il y aura donc environ un bloc par serveur et par profil. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension dénombrable construite à partir du dénombrable Bloc . Chaque ligne de données du profil est un ping de l’agent de surveillance. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Critique d’alerte</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-query(ad) . Il est créé au niveau du ping conditionné que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Alerte descendante</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-query(ac). Il est créé au niveau du ping, sous réserve que cs-uri-query(a) corresponde à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Avertissement d’alerte</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-query(ae) . Il est créé au niveau du ping conditionné que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tout retraitement de profil</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-query(aa). Il est créé au niveau du ping, sous réserve que cs-uri-query(a) corresponde à "1" et que cs-uriquery(k) ne soit pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>À partir du délai</b> </td> 
   <td colname="col2"> cs-uri-query(bi) est placé dans le champ x-as-of-delay-minutes et arrondi à la minute la plus proche. Il est créé au niveau du ping conditionné que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de la ligne de capacité</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-query(r) . Il est créé au niveau du ping, sous réserve que cs-uri-query(a) corresponde à "1" et que cs-uriquery(k) ne soit pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Taille de la capacité, pourcentage</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-query(n) . Il est créé au niveau du ping, sous réserve que cs-uri-query(a) corresponde à "1" et que cs-uriquery(k) ne soit pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite du contrôle des composants</b> </td> 
   <td colname="col2"> Dimension simple créée à partir de la valeur cs-uri-query(v) . Il est créé au niveau du ping et conditionné que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Composants en erreur</b> </td> 
   <td colname="col2"> cs-uri-query(ao) est divisé par le délimiteur "|" et copié dans le champ x-components-in-error . Dimension "plusieurs à plusieurs" créée à partir du champ x-components-in-error . Construit au niveau du ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondes de vérification détaillées</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-query(l) . Il est créé au niveau du ping, sous réserve que cs-uri-query(k) ne soit pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite de la vérification détaillée</b> </td> 
   <td colname="col2"> Dimension simple créée à partir de la valeur cs-uri-query(k) . Il est créé au niveau du ping conditionné que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimension giga-octets</b> </td> 
   <td colname="col2"> cs-uri-query(bc) est copié dans le champ x-dimension-gigaoctets . Le champ x-dimension-gigaoctets est utilisateur pour cette Dimension Simple, conditionné sur cs-uri-query(a) correspondant à "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Disque "x" (pourcentage) utilisé</b> </td> 
   <td colname="col2"> Ces Dimensions numériques sont configurées à partir des valeurs cs-uri-query(ah, ai, aj, ak, al). Ils sont créés au niveau du ping et conditionnés sur cs-uri-query(a) correspond à "1" et cs-uri-query(k) n’est pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimation des secondes de balayage</b> </td> 
   <td colname="col2"> Le champ x-estimated-sweep-dekaseconds est utilisé dans cette Dimension numérique. Il s’agit de la durée estimée du balayage des serveurs divisée par dix (résolution réduite de la mesure du balayage pour rendre la dimension plus raisonnable). <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MégaOctets d’entrée rapide par minute</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(bj) est utilisée pour cette dimension. La dernière ligne d’un bloc est utilisée comme valeur de la dimension. Si le jeu de données est en entrée rapide, cette valeur de la Dimension numérique affichera le Mo par minute auquel le système saisit des données. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fusion rapide : méga octets par minute</b> </td> 
   <td colname="col2">La valeur cs-uri-query(bk) est utilisée pour cette dimension. La dernière ligne d’un bloc est utilisée comme valeur de la dimension. Si le jeu de données est en fusion rapide Cette valeur de la Dimension numérique affiche le Mo par minute auquel le système est en train de fusionner. <p><p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Champ GigaBytes</b> </td> 
   <td colname="col2">La valeur cs-uri-query(bg) est utilisée pour cette dimension. La valeur est divisée par 1 000 et arrondie au nombre entier le plus proche. La valeur de cette Dimension numérique affiche l’espace utilisé par les champs du jeu de données. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Groupe</b> </td> 
   <td colname="col2"> Dimension simple créée au niveau du ping à partir de la valeur cs-uri-query(x) . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Hôte</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(b) est utilisée pour cette dimension. La valeur de la dimension Simple est la Dernière ligne d’un bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernier ping</b> </td> 
   <td colname="col2"> le champ x-unixtime est copié dans x-last-ping et divisé par 10 pour réduire la cardinalité. La Dimension numérique est créée au niveau Bloc et utilise le champ x-last-ping . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Load Average</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique qui utilise la Dernière ligne pour la valeur cs-uri-query(i) d’un serveur donné. Elle est conditionnée sur le fait que cs-uri-query(k) ne soit pas vide. Cette dimension permet de calculer la charge moyenne sur les serveurs du système surveillé. <p><p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de lecture du journal</b> </td> 
   <td colname="col2">la valeur cs-uri-query(be) est utilisée pour cette dimension numérique, créée au niveau du ping. Cette dimension est utilisée pour calculer le pourcentage de journaux en cours de lecture. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de fichier de page mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique à l’aide de la valeur cs-uri-query(o), créée au niveau du ping. Il est conditionné sur cs-uri-query(k) n’étant pas vide, et cs-uri-query(a) correspondant à "1". Cette dimension est utilisée pour calculer le pourcentage d’utilisation de la mémoire de fichier de page. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nombre total de méga-octets physiques de la mémoire</b> </td> 
   <td colname="col2">Il s’agit d’une dimension numérique à l’aide de la valeur cs-uri-query(ag), créée au niveau du ping. Il est conditionné sur cs-uri-query(k) n’étant pas vide, et cs-uri-query(a) correspondant à "1. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de mémoire physique</b> </td> 
   <td colname="col2">Il s’agit d’une dimension numérique à l’aide de la valeur cs-uri-query(ag), créée au niveau du ping. Il est conditionné sur cs-uri-query(k) n’étant pas vide, et cs-uri-query(a) correspondant à "1. Cette dimension est utilisée pour calculer le pourcentage d’utilisation de la mémoire physique de chaque serveur. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de requête mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la valeur cs-uri-query(s) au niveau du ping. Il est conditionné sur cs-uri-query(k) n’étant pas vide et cs-uri-query(a) correspondant à "1. Cette dimension est utilisée pour calculer le pourcentage de l’utilisation de la mémoire de requête de chaque serveur. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connexions réseau</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique à l’aide de la valeur cs-uri-query(q) créée au niveau du ping. Il est conditionné sur cs-uri-query(k) n’étant pas vide et cs-uri-query(a) correspondant à "1. Elle permet d’afficher le nombre de connexions réseau disponibles pour un serveur donné. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lignes de sortie</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(bh) est divisée par 100000 et copiée dans le champ x-output-rows pour réduire la taille de la dimension. X-output-rows est utilisé dans une Dimension numérique créée au niveau du ping, sous réserve que cs-uri-query(a) corresponde à "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de type Ping</b> </td> 
   <td colname="col2"> Dimension simple créée à l’aide de la valeur cs-uri-query(a) au niveau du ping. Cela montre quel genre de Ping a été enregistré. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Centisecondes de latence du sondage</b> </td> 
   <td colname="col2">La valeur cs-uri-query(m) est divisée par 10 pour réduire la taille de dimension et copiée dans le champ x-poll-latency-centiseconds . Il s’agit d’une dimension numérique créée au niveau du ping, à condition que cs-uri-query(k) ne soit pas vide et que cs-uri-query(a) corresponde à "1"/ Cette dimension est utilisée pour calculer la latence du sondage. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Identifiant du mode de traitement</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(bb) est utilisée pour cette Dimension Simple, créée au niveau du ping. Il est conditionné que cs-uri-query(bb) ne soit pas vide et que cs-uri-query(a) correspond à "2" L’identifiant du mode de traitement permet de voir dans quel mode de traitement le système se trouve (entrée rapide, fusion rapide, temps réel). <p>Remarque :  Cette dimension est masquée puis réexposée avec des valeurs conviviales en mode de traitement de dimension côté client. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profil</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(ba) est utilisée pour cette Dimension Simple, elle est créée au niveau du ping. Cette dimension affiche le ou les noms du ou des profils actuellement surveillés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondes de vérification rapide</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(h) est utilisée pour cette Dimension numérique. Il est créé au niveau du ping conditionné que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite du contrôle rapide</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension simple créée à partir de la valeur cs-uri-query(g) créée au niveau du ping. Il est utilisé pour calculer la mesure de vérification rapide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de traitement en temps réel</b> </td> 
   <td colname="col2"> Dimension numérique à l’aide de la valeur cs-uri-query(t) créée au niveau du ping. Il est conditionné que cs-uri-query(a) corresponde à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>La source la plus éloignée derrière</b> </td> 
   <td colname="col2"> Dimension simple créée à partir de la valeur cs-uri-query(bl) créée au niveau du ping. Cette dimension affiche la date du dernier contact avec une source de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage d’espace de base de données temporaire</b> </td> 
   <td colname="col2">Dimension numérique créée à l’aide de la valeur cs-uri-query(an), créée au niveau du ping. Il est conditionné que cs-uri-query(k) ne soit pas vide et que cs-uri-query(a) corresponde à "1". Il est utilisé pour calculer le pourcentage de l’espace Temp DB utilisé sur un serveur donné. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de transformation</b> </td> 
   <td colname="col2">la valeur cs-uri-query(bf) est utilisée pour cette dimension numérique. Il est construit au niveau du ping. Cette dimension est utilisée pour calculer le pourcentage de transformation complète des données. <p><p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Version du Data Workbench</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(ab) est utilisée pour cette Dimension simple. Il est créé au niveau du ping et conditionné que cs-uri-query(ab) n’est pas vide, et que cs-uri-query(a) correspond à "1". Cette option affiche la ou les versions du serveur Data Workbench exécuté sur chaque serveur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Version majeure du Data Workbench</b> </td> 
   <td colname="col2"> La valeur cs-uri-query(ab) est fractionnée et la valeur de version majeure est copiée dans le champ x-insight-version-major . Il s’agit d’une Dimension simple créée au niveau du ping et conditionnée que x-insight-version-major n’est pas vide et que cs-uri-query(a) correspond à "1". </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->
