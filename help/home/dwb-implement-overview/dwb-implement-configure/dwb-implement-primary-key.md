---
description: Cette section explique comment créer des clés Principal (ID de suivi) pour les jeux de données de Data Workbench pour la conception et la mise en oeuvre de schémas.
title: Traitement des données - Création de la clé primaire
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
exl-id: 9937038f-d011-4946-8a5b-cc724b611ae5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# Traitement des données - Création de la clé primaire{#data-processing-building-primary-key}

{{eol}}

Cette section explique comment créer des clés Principal (ID de suivi) pour les jeux de données de Data Workbench pour la conception et la mise en oeuvre de schémas.

## Compréhension de l’ID de suivi {#section-24683031044a4af49988655ccb9a45fd}

Après avoir lu et décodé les données dans DWB (à l’aide de décodeurs), la première étape consiste à définir l’ID de suivi et l’horodatage. L’ID de suivi est un identifiant qui identifie de manière unique un enregistrement de client. Il peut s’agir de n’importe quel champ du flux, comme l’ID d’email, le numéro de sécurité sociale, l’ID de cookie, etc. Le champ à utiliser comme ID de suivi est décidé par le client au cours de la session de découverte. L’identifiant de suivi et l’horodatage sont des champs obligatoires qui doivent être définis pour chaque enregistrement.

En règle générale, pour les données en ligne, ID de cookie (combinaison de *x-visid_high* et* x-visid_low*) est utilisé comme mécanisme par défaut pour l’identification unique du client. Cependant, il peut être modifié selon les besoins du client. La date et l’heure auxquelles la requête (ou l’événement) se produit sont les suivantes : *x-timestamp*. Tous les enregistrements dans DWB sont regroupés par *trackingid* et triés selon l’horodatage. Champ obligatoire [!DNL Definitions.cfg] est un fichier d’inclusion de jeux de données de traitement de journal qui définit les champs requis : *x-trackingid* et *x-timestamp*.

Remarque : *x-trackingid *dans DWB est un champ inné et ce nom ne doit être utilisé pour aucun autre champ.

**Exemple 1**: Création *x-trackingid* utilisation de l’ID de cookie (lorsque seules les données en ligne sont utilisées)

Pour créer la *x-trackingid* dans DWB à l’aide de l’ID de cookie, utilisez la fonction de hachage pour créer la variable *x-trackingid* dans le [!DNL foundation.cfg] (il est recommandé de définir l’ID de suivi dans [!DNL foundation.cfg] mais il peut être défini dans n’importe quel autre fichier de configuration sous [!DNL Dataset > log processing] ), comme illustré :

![](assets/dwb_impl_primary_key1.png)

**Exemple 2**: Création *x-trackingid* utilisation de l’ID de message électronique (lorsque des données en ligne et hors ligne sont disponibles)

En supposant que les données hors ligne et en ligne soient disponibles (dans cet exemple) et que l’ID de message électronique soit disponible dans les deux sources de données. Puisque l’ID de message électronique identifie de manière unique un client, il sera utilisé pour créer la variable *x-trackingid*.

Utilisez la fonction de hachage pour créer la variable *trackingId* comme illustré :

![](assets/dwb_impl_primary_key2.png)
