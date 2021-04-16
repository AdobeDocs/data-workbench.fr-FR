---
description: Informations sur les codes et formats de fuseau horaire.
title: Codes du fuseau horaire
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 5%

---

# Codes du fuseau horaire{#time-zone-codes}

Informations sur les codes et formats de fuseau horaire.

La plupart des paramètres temporels du serveur de l’outil de données sont spécifiés au format suivant :

* Mois JJ, AAAA HH : MM : SS TZone
* Exemple : 13 août 2013 22:30:00 (HNE)

Les fuseaux horaires sont exprimés dans un format de fuseau horaire indépendant du système (temps universel coordonné) au format suivant :

* UTC +hmm dstrules

Le signe (+) peut être un signe plus (+) ou un signe moins (-) et hhmm est le décalage par rapport à l&#39;heure UTC en heures et minutes. Les règles facultatives de la variable spécifient un ensemble de règles pour mettre en oeuvre l’heure d’été ou une stratégie de changement d’heure similaire.

Si vous spécifiez des règles, un fichier délimité par des tabulations nommé [!DNL dstrules.dst] doit être présent dans le répertoire Dataset\TimeZone du profil [!DNL Base] (pour les fichiers de configuration qui ne sont associés à aucun jeu de données particulier) ou du profil de jeux de données (pour les fichiers de configuration qui sont spécifiques à un jeu de données). Le fichier spécifie un ensemble de règles indépendant du fuseau horaire pour l’heure d’été. Vous pouvez avoir différents ensembles de règles pour différentes années. Le fichier [!DNL DST.dst] fourni par l&#39;Adobe dans le profil [!DNL Base] précise les règles américaines standard établies par la Energy Policy Act de 2005 (en vigueur depuis 2007) et les règles américaines pour les années précédentes.

Les exemples d’entrées de fuseau horaire sont répertoriés ci-dessous :

* Heure avancée de l&#39;Est des États-Unis : Fuseau horaire = chaîne : UTC -0500 DST
* Heure UTC sans décalage et sans distrules (correspondant à GMT) : Fuseau horaire = chaîne : UTC -0000

Lorsque ce format est utilisé, le fuseau horaire système du serveur de l’outil de données, des outils de données et des ordinateurs des rapports ne doit pas nécessairement être identique au fuseau horaire spécifié. En outre, tous les profils de jeux de données principaux sur un ordinateur serveur de l’outil de données ne doivent pas avoir le même paramètre de fuseau horaire.

Le tableau suivant contient la liste des codes que vous pouvez utiliser pour spécifier les fuseaux horaires dans les paramètres temporels.

## Table du code du fuseau horaire {#section-b4f965b872c543e2ac52a3c94410d076}

Si vous implémentez l’heure d’été ou une autre stratégie similaire de changement d’horloge, vous devez enregistrer le fichier [!DNL .dst] contenant les règles appropriées dans le répertoire du nom de profil [!DNL \Dataset\Timezone] sur l’ordinateur serveur de l’outil de données.

| Code | Fuseau horaire | Décalage à partir de GMT |
|---|---|---|
| gmt | Greenwich Mean | 0 |
| est | Eastern Standard | 5 |
| edt | East Daylight | 5 |
| cst | Central Standard | 6 |
| cdt | Central Daylight | 6 |
| mst | Mountain Standard | 7 |
| mdt | Mountain Daylight | 7 |
| post | Pacifique | 8 |
| pdt | Pacifique (Daylight) | 8 |
