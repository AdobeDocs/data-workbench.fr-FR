---
description: Les dimensions suivantes peuvent être utilisées dans le profil historique des outils de données.
title: Dimensions dans le profil historique de Data Workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
exl-id: 9df1f317-a985-4132-b32e-f2263e0c23b2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 1%

---

# Dimensions dans le profil historique de Data Workbench{#dimensions-in-the-data-workbench-historic-profile}

Les dimensions suivantes peuvent être utilisées dans le profil historique des outils de données.

## Dimensions dans le profil historique de Data Workbench {#section-96f1b64f5cb84411b630f97f227d888d}

Les dimensions suivantes peuvent être utilisées dans le profil historique des outils de données.

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloc</b> </td> 
   <td colname="col2">Il s’agit du seul décompte dans cette configuration, il s’agit de la racine pour toutes les dimensions. Un bloc peut être considéré comme un serveur. Il utilise le champ x-trackingid. <p>Remarque :  L'ID de bloc est un hachage du nom du serveur et du nom d'hôte, il y aura donc environ un bloc par serveur par profil. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> Il s'agit d'une dimension dénombrable construite à partir du dénombrable Bloc. Chaque ligne de données du profil est un ping de l'agent de surveillance. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Alerte critique</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-requête(ad). Il est construit au niveau Ping conditionné que cs-uri-requête(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Alerte vers le bas</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-requête(ac). Il est construit au niveau Ping, sous réserve que cs-uri-requête(a) corresponde à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Avertissement d'alerte</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-requête(ae). Il est construit au niveau Ping conditionné que cs-uri-requête(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tout retraitement de Profil</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-requête(aa). Il est construit au niveau Ping conditionné que cs-uri-requête(a) correspond à "1" et cs-uriquery(k) n'est pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>À compter du délai</b> </td> 
   <td colname="col2"> cs-uri-requête(bi) est placé dans le champ x-as-of-delay-minutes et arrondi à la minute la plus proche. Il est construit au niveau Ping conditionné que cs-uri-requête(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de lignes de capacité</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-requête(r). Il est construit au niveau Ping conditionné que cs-uri-requête(a) correspond à "1" et cs-uriquery(k) n'est pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de capacité</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-requête(n). Il est construit au niveau Ping conditionné que cs-uri-requête(a) correspond à "1" et cs-uriquery(k) n'est pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite de la vérification des composants</b> </td> 
   <td colname="col2"> Dimension simple créée à partir de la valeur cs-uri-requête(v). Il est construit au niveau Ping, et conditionné que cs-uri-requête(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Composants dans une erreur</b> </td> 
   <td colname="col2"> cs-uri-requête(ao) est fractionné par le délimiteur "|" et copié dans le champ x-components-in-error. Dimension plusieurs à plusieurs créée à partir du champ x-components-in-error. Construit au niveau Ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondes de vérification détaillées</b> </td> 
   <td colname="col2"> Dimension numérique créée à partir de la valeur cs-uri-requête(l). Il est construit au niveau Ping conditionné que cs-uri-requête(k) n'est pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite de la vérification détaillée</b> </td> 
   <td colname="col2"> Dimension simple créée à partir de la valeur cs-uri-requête(k). Il est construit au niveau Ping conditionné que cs-uri-requête(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimension GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-requête(bc) est copié dans le champ x-dimension-gigaoctets. Le champ x-dimension-gigabytes est utilisateur pour cette Dimension simple, conditionnée sur cs-uri-requête(a) correspondant à "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage utilisé sur le disque "x"</b> </td> 
   <td colname="col2"> Ces Dimensions numériques sont configurées à partir des valeurs cs-uri-requête(ah, ai, aj, ak, al). Ils sont construits au niveau Ping et conditionnés sur cs-uri-requête(a) correspond à "1" et cs-uri-requête(k) n'est pas vide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimation des dekasecondes de balayage</b> </td> 
   <td colname="col2"> Le champ x-estimation-sweep-dekaseconds est utilisé dans cette Dimension numérique. Il s'agit du temps de balayage estimé des serveurs divisé par dix (résolution réduite de la mesure de balayage pour rendre la dimension plus raisonnable). <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MégaBytes d’entrée rapide par minute</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(bj) est utilisée pour cette dimension. La dernière ligne d'un bloc est utilisée comme valeur de la dimension. Si le jeu de données est en entrée rapide, cette valeur de Dimension numérique affichera le Mo par minute auquel le système saisit les données. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fusion rapide MégaBytes par minute</b> </td> 
   <td colname="col2">La valeur cs-uri-requête(bk) est utilisée pour cette dimension. La dernière ligne d'un bloc est utilisée comme valeur de la dimension. Si le jeu de données est en fusion rapide Cette valeur de Dimension numérique affiche le Mo par minute auquel le système est en train de fusionner. <p><p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Champ GigaBytes</b> </td> 
   <td colname="col2">La valeur cs-uri-requête(bg) est utilisée pour cette dimension. La valeur est divisée par 1 000 et arrondie au nombre entier le plus proche. Cette valeur de Dimension numérique affiche l’espace utilisé par les champs dans le jeu de données. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Groupe</b> </td> 
   <td colname="col2"> Dimension simple créée au niveau Ping à partir de la valeur cs-uri-requête(x). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Hôte</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(b) est utilisée pour cette dimension. La valeur de la dimension Simple est la dernière ligne d’un bloc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dernier ping</b> </td> 
   <td colname="col2"> le champ x-unixtime est copié dans x-last-ping et divisé par 10 pour réduire la cardinalité. La Dimension numérique est créée au niveau Bloc et utilise le champ x-last-ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Charge moyenne</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la dernière ligne pour la valeur cs-uri-requête(i) d’un serveur donné. Il est conditionné sur cs-uri-requête(k) ne pas être vide. Cette dimension permet de calculer la charge moyenne sur les serveurs du système surveillé. <p><p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de lecture du journal</b> </td> 
   <td colname="col2">la valeur cs-uri-requête(be) est utilisée pour cette dimension numérique, générée au niveau Ping. Cette dimension est utilisée pour calculer le pourcentage de journaux lus. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de fichiers de la page mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la valeur cs-uri-requête(o), créée au niveau Ping. Il est conditionné sur cs-uri-requête(k) n'étant pas vide, et cs-uri-requête(a) correspondant à "1". Cette dimension est utilisée pour calculer le pourcentage d’utilisation de la mémoire de fichier de page. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Total MégaBytes physiques de mémoire</b> </td> 
   <td colname="col2">Il s’agit d’une dimension numérique utilisant la valeur cs-uri-requête(ag), créée au niveau du ping. Il est conditionné sur cs-uri-requête(k) n'étant pas vide, et cs-uri-requête(a) correspondant à "1. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de mémoire physique</b> </td> 
   <td colname="col2">Il s’agit d’une dimension numérique utilisant la valeur cs-uri-requête(ag), créée au niveau du ping. Il est conditionné sur cs-uri-requête(k) n'étant pas vide, et cs-uri-requête(a) correspondant à "1. Cette dimension est utilisée pour calculer le pourcentage d'utilisation de la mémoire physique de chaque serveur. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de Requête de mémoire</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la valeur cs-uri-requête(s) au niveau Ping. Il est conditionné sur cs-uri-requête(k) n'étant pas vide et cs-uri-requête(a) correspondant à "1. Cette dimension est utilisée pour calculer le pourcentage d'utilisation de la mémoire de requête de chaque serveur. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connexions réseau</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension numérique utilisant la valeur cs-uri-requête(q) générée au niveau Ping. Il est conditionné sur cs-uri-requête(k) n'étant pas vide et cs-uri-requête(a) correspondant à "1. Elle est utilisée pour indiquer le nombre de connexions réseau disponibles pour un serveur donné. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lignes de sortie</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(bh) est divisée par 100000 et copiée dans le champ x-output-rows afin de réduire la taille de la dimension. X-output-rows est utilisé dans une Dimension numérique créée au niveau Ping, à condition que cs-uri-requête(a) corresponde à "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de type Ping</b> </td> 
   <td colname="col2"> Dimension simple créée à l'aide de la valeur cs-uri-requête(a) au niveau Ping. Ceci montre quel type de Ping a été enregistré. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Centisecondes de latence du sondage</b> </td> 
   <td colname="col2">La valeur cs-uri-requête(m) est divisée par 10 pour réduire la taille de la dimension et copiée dans le champ x-poll-latency-centisecondes. Il s’agit d’une dimension numérique créée au niveau Ping, à condition que cs-uri-requête(k) ne soit pas vide et que cs-uri-requête(a) corresponde à "1"/ Cette dimension est utilisée pour calculer la latence du sondage. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de mode de traitement</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(bb) est utilisée pour cette Dimension simple, créée au niveau du ping. Il est conditionné que cs-uri-requête(bb) n'est pas vide, et que cs-uri-requête(a) correspond à "2" Le mode de traitement ID permet de voir dans quel mode de traitement le système se trouve (Entrée rapide, Fusion rapide, Temps réel). <p>Remarque :  Cette dimension est masquée puis réexposée avec des valeurs conviviales dans le mode de traitement de la dimension côté client. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profil</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(ba) est utilisée pour cette Dimension Simple, elle est créée au niveau Ping. Cette dimension affiche le ou les noms des profils actuellement surveillés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondes de vérification rapide</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(h) est utilisée pour cette Dimension numérique. Il est construit au niveau Ping conditionné que cs-uri-requête(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Réussite de la vérification rapide</b> </td> 
   <td colname="col2"> Il s’agit d’une dimension simple créée à partir de la valeur cs-uri-requête(g) générée au niveau Ping. Il est utilisé pour calculer la mesure de vérification rapide. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de traitement en temps réel</b> </td> 
   <td colname="col2"> Dimension numérique à l’aide de la valeur cs-uri-requête(t) générée au niveau Ping. Il est conditionné que cs-uri-requête(a) correspond à "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Source la plus éloignée derrière</b> </td> 
   <td colname="col2"> Dimension simple créée à partir de la valeur cs-uri-requête(bl) générée au niveau Ping. Cette dimension affiche la date du dernier contact avec une source de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage d'espace de base de données temporaire</b> </td> 
   <td colname="col2">Dimension numérique générée à l’aide de la valeur cs-uri-requête(an), générée au niveau Ping. Il est conditionné que cs-uri-requête(k) n'est pas vide, et cs-uri-requête(a) correspond à "1". Il est utilisé pour calculer le pourcentage d’espace de base de données temporaire utilisé sur un serveur donné. <p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pourcentage de transformation</b> </td> 
   <td colname="col2">la valeur cs-uri-requête(bf) est utilisée pour cette dimension numérique. Il est construit au niveau Ping. Cette dimension est utilisée pour calculer le pourcentage de transformation complète des données. <p><p>Remarque :  Cette dimension est masquée, car elle n’est utile que lorsqu’elle est convertie en mesure. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Version du Data Workbench</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(ab) est utilisée pour cette Dimension simple. Il est construit au niveau Ping et conditionné que cs-uri-requête(ab) n'est pas vide, et cs-uri-requête(a) correspond à "1". Cette option affiche la ou les versions du serveur de l’outil de données s’exécutant sur chaque serveur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Version majeure du Data Workbench</b> </td> 
   <td colname="col2"> La valeur cs-uri-requête(ab) est fractionnée et la valeur de version majeure est copiée dans le champ x-insight-version-major. Il s'agit d'une Dimension simple construite au niveau Ping et conditionnée que x-insight-version-major n'est pas vide, et cs-uri-requête(a) correspond à "1". </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->
