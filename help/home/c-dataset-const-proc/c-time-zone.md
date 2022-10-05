---
description: Informations sur les codes et les formats de fuseau horaire.
title: Codes et formats du fuseau horaire
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 4%

---

# Codes du fuseau horaire{#time-zone-codes}

{{eol}}

Informations sur les codes et les formats de fuseau horaire.

La plupart des paramètres temporels du serveur Data Workbench sont spécifiés au format suivant :

* JJ du mois, HH AAAA : MM : SS TZone
* Exemple : 13 août 2013 22:30:00 EST

Les fuseaux horaires sont exprimés dans un format de fuseau horaire indépendant du système (temps universel coordonné) au format suivant :

* Règles UTC +hmm

Le signe (+) peut être un signe plus (+) ou un signe moins (-) et hhmm est le décalage par rapport à UTC en heures et minutes. Les règles facultatives de variable spécifient un ensemble de règles pour mettre en oeuvre l’heure d’été ou une stratégie de changement d’heure similaire.

Si vous spécifiez des règles, un fichier délimité par des tabulations nommé [!DNL dstrules.dst] doit être présent dans le répertoire Dataset\TimeZone de l’une des [!DNL Base] profile (pour les fichiers de configuration qui ne sont pas associés à un jeu de données spécifique) ou le profil du jeu de données (pour les fichiers de configuration qui sont spécifiques au jeu de données). Le fichier spécifie un jeu de règles indépendant des fuseaux horaires pour l’heure d’été. Vous pouvez avoir différents ensembles de règles pour différentes années. Le [!DNL DST.dst] fourni par Adobe dans la variable [!DNL Base] profile spécifie les règles américaines standard établies par le Energy Policy Act de 2005 (en vigueur à partir de 2007) et les règles américaines pour les années précédentes.

Les exemples d’entrées de fuseau horaire sont répertoriés ci-dessous :

* Heure d’été de l’Est des États-Unis : Fuseau horaire = chaîne : UTC -0500 DST
* Heure UTC sans décalage et sans règle (correspondant à GMT) : Fuseau horaire = chaîne : UTC-0000

Lorsque ce format est utilisé, le fuseau horaire système du serveur Data Workbench, des outils de données et des Report machines ne doit pas être identique au fuseau horaire spécifié. En outre, tous les profils de jeu de données principaux sur un serveur Data Workbench n’ont pas besoin de définir le même fuseau horaire.

Le tableau suivant contient la liste des codes que vous pouvez utiliser pour spécifier les fuseaux horaires dans les paramètres temporels.

## Tableau de code de fuseau horaire {#section-b4f965b872c543e2ac52a3c94410d076}

Si vous implémentez l’heure d’été ou une stratégie similaire de changement d’heure, vous devez enregistrer la variable [!DNL .dst] fichier contenant les règles appropriées dans le nom du profil [!DNL \Dataset\Timezone] sur l’ordinateur du serveur data workbench.

| Code | Fuseau horaire | Décalage à partir de GMT |
|---|---|---|
| gmt | Greenwich Mean | 0 |
| est | Oriest Standard | 5 |
| edt | Heure d’été de l’Est | 5 |
| cst | Central Standard | 6 |
| cdt | Central Daylight | 6 |
| mst | Mountain Standard | 7 |
| mdt | Rocheuse | 7 |
| pst | Pacifique | 8 |
| pdt | Jour Pacifique | 8 |
