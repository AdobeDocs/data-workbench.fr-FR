---
description: Informations sur les codes et les formats de fuseau horaire.
title: Codes du fuseau horaire
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 5%

---

# Codes du fuseau horaire{#time-zone-codes}

Informations sur les codes et les formats de fuseau horaire.

La plupart des paramètres temporels du serveur Data Workbench sont spécifiés au format suivant :

* JJ du mois, HH AAAA : MM : SS TZone
* Exemple : 13 août 2013 22:30:00 EST

Les fuseaux horaires sont exprimés dans un format de fuseau horaire indépendant du système (temps universel coordonné) au format suivant :

* Règles UTC +hmm

Le signe (+) peut être un signe plus (+) ou un signe moins (-) et hhmm est le décalage par rapport à UTC en heures et minutes. Les règles facultatives de variable spécifient un ensemble de règles pour mettre en oeuvre l’heure d’été ou une stratégie de changement d’heure similaire.

Si vous spécifiez des règles, un fichier délimité par des tabulations nommé [!DNL dstrules.dst] doit être présent dans le répertoire Dataset\TimeZone du profil [!DNL Base] (pour les fichiers de configuration qui ne sont pas associés à un jeu de données particulier) ou du profil du jeu de données (pour les fichiers de configuration qui sont spécifiques à un jeu de données). Le fichier spécifie un jeu de règles indépendant des fuseaux horaires pour l’heure d’été. Vous pouvez avoir différents ensembles de règles pour différentes années. Le fichier [!DNL DST.dst] fourni par Adobe dans le profil [!DNL Base] spécifie les règles américaines standard établies par le Energy Policy Act de 2005 (en vigueur à partir de 2007) et les règles américaines pour les années précédentes.

Les exemples d’entrées de fuseau horaire sont répertoriés ci-dessous :

* Heure d’été de l’Est des États-Unis : Fuseau horaire = chaîne : UTC -0500 DST
* Heure UTC sans décalage et sans règle (correspondant à GMT) : Fuseau horaire = chaîne : UTC-0000

Lorsque ce format est utilisé, le fuseau horaire système du serveur Data Workbench, des outils de données et des Report machines ne doit pas être identique au fuseau horaire spécifié. En outre, tous les profils de jeu de données principaux sur un serveur Data Workbench n’ont pas besoin de définir le même fuseau horaire.

Le tableau suivant contient la liste des codes que vous pouvez utiliser pour spécifier les fuseaux horaires dans les paramètres temporels.

## Tableau de code de fuseau horaire {#section-b4f965b872c543e2ac52a3c94410d076}

Si vous mettez en oeuvre une stratégie d’enregistrement de l’heure d’été ou une stratégie similaire de changement d’horloge, vous devez enregistrer le fichier [!DNL .dst] contenant les règles appropriées dans le répertoire du nom de profil [!DNL \Dataset\Timezone] sur l’ordinateur du serveur Data Workbench.

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
