---
description: Instructions de mise en forme des paramètres temporels dans Insight Server.
solution: Insight
title: Codes fuseau horaire
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Codes fuseau horaire{#time-zone-codes}

Instructions de mise en forme des paramètres temporels dans Insight Server.

La plupart des paramètres temporels [!DNL Insight Server] sont spécifiés au format suivant :

*Mois JJ, AAAA HH:MM:SS TimeZone*

Exemple : 13 août 2013 22:30:00 EST

Les fuseaux horaires sont exprimés dans un format de fuseau horaire indépendant du système (temps universel coordonné) au format suivant :

UTC +hhhmm *dstrules*

Le signe (+) peut être un signe plus (+) ou un signe moins (-), et *hhmm* est le décalage par rapport à UTC en heures et minutes. La variable facultative *décrit* un ensemble de règles pour mettre en oeuvre l’heure d’été ou une stratégie similaire de changement d’horloge.

Si vous spécifiez des *règles*, un fichier délimité par des tabulations nommé *&lt;[!DNL dstrules]>* [!DNL .dst] doit être présent dans le répertoire Dataset\TimeZone du profil Base (pour les fichiers de configuration qui ne sont associés à aucun jeu de données particulier) ou du profil du jeu de données (pour les fichiers de configuration qui sont spécifiques à un jeu de données). Le fichier spécifie un jeu de règles indépendant du fuseau horaire pour l’heure d’été. Vous pouvez avoir différents ensembles de règles pour différentes années. Le [!DNL DST.dst] fichier fourni par Adobe dans le profil de base spécifie les règles américaines standard établies par la loi de 2005 sur la politique énergétique (en vigueur depuis 2007) et les règles américaines pour les années précédentes.

Les exemples d’entrées de fuseau horaire sont répertoriés ci-dessous :

* Heure avancée de l&#39;Est des États-Unis : Fuseau horaire = chaîne : UTC -0500 DST
* Heure UTC sans décalage et sans *distorsion* (correspondant à GMT): Fuseau horaire = chaîne : UTC -0000

Lorsque ce format est utilisé, le fuseau horaire système des machines [!DNL Insight Server], [!DNL Insight]et [!DNL Report] ne doit pas nécessairement être identique au fuseau horaire spécifié. En outre, tous les profils de jeux de données actifs sur une [!DNL Insight Server] machine ne doivent pas avoir le même paramètre de fuseau horaire.

Le tableau suivant contient la liste des codes que vous pouvez utiliser pour spécifier les fuseaux horaires dans les paramètres temporels.

## Tableau Code de fuseau horaire {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Si vous implémentez l’heure d’été ou une stratégie similaire de changement d’horloge, vous devez enregistrer le [!DNL .dst] fichier contenant les règles appropriées dans le nom *de* profil \Dataset\Timezone directory on the [!DNL Insight Server] machine.

| Code | Fuseau horaire | Décalage à partir de GMT |
|---|---|---|
| gmt | Greenwich Mean | 0 |
| est | Standard oriental | 5 |
| edt | East Daylight | 5 |
| cst | Central Standard | 6 |
| cdt | Central Daylight | 6 |
| mst | Mountain Standard | 7 |
| mdt | Mountain Daylight | 7 |
| pst | Norme du Pacifique | 8 |
| pdt | Pacific Daylight | 8 |

