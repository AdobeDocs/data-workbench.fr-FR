---
description: Instructions de format sur les paramètres temporels dans Insight Server.
title: Codes de fuseau horaire (serveur Insight)
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 4%

---

# Codes du fuseau horaire{#time-zone-codes}

{{eol}}

Instructions de format sur les paramètres temporels dans Insight Server.

La plupart des paramètres temporels dans [!DNL Insight Server] sont spécifiés au format suivant :

*Mois JJ, AAAA HH:MM:SSTimeZone*

Exemple : 13 août 2013 22:30:00 EST

Les fuseaux horaires sont exprimés dans un format de fuseau horaire indépendant du système (temps universel coordonné) au format suivant :

UTC +hhmm *dstrules*

Le signe (+) peut être un signe plus (+) ou un signe moins (-), et *hhmm* est le décalage par rapport au temps universel (UTC) en heures et en minutes. Variable facultative *dstrules* spécifie un ensemble de règles pour mettre en oeuvre l’heure d’été ou une stratégie de changement d’heure similaire.

Si vous spécifiez *dstrules*, un fichier délimité par des tabulations nommé *&lt; [!DNL dstrules]>* [!DNL .dst] doit être présent dans le répertoire Dataset\TimeZone du profil de base (pour les fichiers de configuration qui ne sont pas associés à un jeu de données particulier) ou du profil du jeu de données (pour les fichiers de configuration qui sont spécifiques au jeu de données). Le fichier spécifie un jeu de règles indépendant des fuseaux horaires pour l’heure d’été. Vous pouvez avoir différents ensembles de règles pour différentes années. Le [!DNL DST.dst] Le fichier fourni par Adobe dans le profil de base spécifie les règles américaines standard établies par le Energy Policy Act de 2005 (en vigueur à compter de 2007) et les règles américaines pour les années précédentes.

Les exemples d’entrées de fuseau horaire sont répertoriés ci-dessous :

* Heure d’été de l’Est des États-Unis : Fuseau horaire = chaîne : UTC -0500 DST
* Heure UTC sans décalage et sans aucune *dstrules* (correspondant à GMT) : Fuseau horaire = chaîne : UTC-0000

Lorsque ce format est utilisé, le fuseau horaire système de [!DNL Insight Server], [!DNL Insight], et [!DNL Report] Les machines ne doivent pas être identiques au fuseau horaire spécifié. En outre, tous les profils de jeux de données principaux sur un [!DNL Insight Server] La machine ne doit pas avoir le même paramètre de fuseau horaire.

Le tableau suivant contient la liste des codes que vous pouvez utiliser pour spécifier les fuseaux horaires dans les paramètres temporels.

## Tableau de code de fuseau horaire {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Si vous implémentez l’heure d’été ou une stratégie similaire de changement d’heure, vous devez enregistrer la variable [!DNL .dst] contenant les règles appropriées dans le fichier *nom du profil*\Dataset\Timezone dans le répertoire [!DNL Insight Server] machine.

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
