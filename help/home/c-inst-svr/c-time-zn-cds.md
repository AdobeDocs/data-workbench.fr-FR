---
description: Instructions de mise en forme des paramètres temporels dans Insight Server.
title: Codes du fuseau horaire
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 5%

---

# Codes du fuseau horaire{#time-zone-codes}

Instructions de mise en forme des paramètres temporels dans Insight Server.

La plupart des paramètres temporels de [!DNL Insight Server] sont spécifiés au format suivant :

*Mois JJ, AAAA HH:MM:SS TimeZone*

Exemple : 13 août 2013 22:30:00 (HNE)

Les fuseaux horaires sont exprimés dans un format de fuseau horaire indépendant du système (temps universel coordonné) au format suivant :

UTC +hhmm *dstrules*

Le signe (+) peut être un signe plus (+) ou un signe moins (-) et *hhmm* est le décalage par rapport à l&#39;heure UTC en heures et minutes. La variable facultative *dstrules* spécifie un ensemble de règles pour implémenter l&#39;heure d&#39;été ou une stratégie similaire de changement d&#39;horloge.

Si vous spécifiez *dstrules*, un fichier délimité par des tabulations nommé *&lt; [!DNL dstrules]* [!DNL .dst] doit être présent dans le répertoire Dataset\TimeZone du profil de base (pour les fichiers de configuration qui ne sont pas associés à un jeu de données particulier) ou du profil de jeux de données (pour les fichiers de configuration qui sont spécifiques à un jeu de données). Le fichier spécifie un ensemble de règles indépendant du fuseau horaire pour l’heure d’été. Vous pouvez avoir différents ensembles de règles pour différentes années. Le fichier [!DNL DST.dst] fourni par l&#39;Adobe dans le profil de base précise les règles américaines standard établies par le Energy Policy Act de 2005 (en vigueur depuis 2007) et les règles américaines pour les années précédentes.

Les exemples d’entrées de fuseau horaire sont répertoriés ci-dessous :

* Heure avancée de l&#39;Est des États-Unis : Fuseau horaire = chaîne : UTC -0500 DST
* Heure UTC sans décalage et sans *dstrules* (correspondant à GMT) : Fuseau horaire = chaîne : UTC -0000

Lorsque ce format est utilisé, le fuseau horaire système des machines [!DNL Insight Server], [!DNL Insight] et [!DNL Report] ne doit pas être identique au fuseau horaire spécifié. En outre, tous les profils de jeux de données principaux sur un ordinateur [!DNL Insight Server] ne doivent pas avoir le même paramètre de fuseau horaire.

Le tableau suivant contient la liste des codes que vous pouvez utiliser pour spécifier les fuseaux horaires dans les paramètres temporels.

## Table du code du fuseau horaire {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Si vous implémentez l’heure d’été ou une stratégie de changement d’horloge similaire, vous devez enregistrer le fichier [!DNL .dst] contenant les règles appropriées dans l’ordinateur *nom du profil*\Dataset\Timezone directory on the [!DNL Insight Server].

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
