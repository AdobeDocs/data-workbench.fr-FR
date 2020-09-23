---
description: Instructions de mise en forme des paramètres temporels dans Insight Server.
solution: Analytics
title: Codes du fuseau horaire
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 5%

---


# Codes du fuseau horaire{#time-zone-codes}

Instructions de mise en forme des paramètres temporels dans Insight Server.

La plupart des paramètres temporels dans [!DNL Insight Server] sont spécifiés au format suivant :

*Mois JJ, AAAA HH:MM:SS TimeZone*

Exemple : 13 août 2013 22:30:00 (HNE)

Les fuseaux horaires sont exprimés dans un format de fuseau horaire indépendant du système (temps universel coordonné) au format suivant :

UTC +hhmm *dstrules*

Le signe (+) peut être un signe plus (+) ou un signe moins (-) et *hmm* est le décalage par rapport à l&#39;heure UTC en heures et minutes. La variable facultative *dstrules* spécifie un ensemble de règles pour mettre en oeuvre l’heure d’été ou une stratégie de changement d’heure similaire.

Si vous spécifiez *des règles*, un fichier délimité par des tabulations nommé *&lt;[!DNL dstrules]>* [!DNL .dst] doit être présent dans le répertoire Dataset\TimeZone du profil de base (pour les fichiers de configuration qui ne sont associés à aucun jeu de données particulier) ou du profil de jeux de données (pour les fichiers de configuration qui sont spécifiques à un jeu de données). Le fichier spécifie un ensemble de règles indépendant du fuseau horaire pour l’heure d’été. Vous pouvez avoir différents ensembles de règles pour différentes années. Le [!DNL DST.dst] dossier fourni par l&#39;Adobe dans le profil de base précise les règles américaines standard établies par le Energy Policy Act de 2005 (en vigueur à partir de 2007) et les règles américaines pour les années précédentes.

Les exemples d’entrées de fuseau horaire sont répertoriés ci-dessous :

* Heure avancée de l&#39;Est des États-Unis : Fuseau horaire = chaîne : UTC -0500 DST
* Heure UTC sans décalage et sans *déformation* (correspondant à GMT) : Fuseau horaire = chaîne : UTC -0000

Lorsque ce format est utilisé, le fuseau horaire système des [!DNL Insight Server], [!DNL Insight]et [!DNL Report] des machines ne doit pas nécessairement être identique au fuseau horaire spécifié. En outre, tous les profils de jeux de données principaux sur un [!DNL Insight Server] ordinateur ne doivent pas avoir le même paramètre de fuseau horaire.

Le tableau suivant contient la liste des codes que vous pouvez utiliser pour spécifier les fuseaux horaires dans les paramètres temporels.

## Tableau du code de fuseau horaire {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Si vous implémentez l’heure d’été ou une autre stratégie similaire de changement d’horloge, vous devez enregistrer le [!DNL .dst] fichier contenant les règles appropriées dans l’ *ordinateur du nom* du [!DNL Insight Server] profil \Dataset\Timezone directory on the .

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

