---
description: Cette section explique comment créer des clés principales (ID de suivi) pour les jeux de données des outils de données pour la conception et l’implémentation de schémas.
title: Traitement des données - Création de la clé primaire
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Traitement des données - Création de la clé primaire{#data-processing-building-primary-key}

Cette section explique comment créer des clés principales (ID de suivi) pour les jeux de données des outils de données pour la conception et l’implémentation de schémas.

## Présentation de l&#39;ID de suivi {#section-24683031044a4af49988655ccb9a45fd}

Après avoir lu et décodé les données dans DWB (à l’aide de décodeurs), la première étape consiste à définir l’ID de suivi et l’horodatage. L’ID de suivi est un identifiant qui identifie de manière unique un enregistrement de client. Il peut s’agir de n’importe quel champ du flux, tel que l’ID d’adresse électronique, le numéro de sécurité sociale, l’ID de cookie, etc. Le champ à utiliser comme ID de suivi est décidé par le client au cours de la session de découverte. L’ID de suivi et l’horodatage sont des champs obligatoires et doivent être définis pour chaque enregistrement.

En règle générale, pour les données en ligne, l’ID de cookie (combinaison de *x-visid_high* et de* x-visid_low*) est utilisé comme mécanisme par défaut pour l’identification des clients uniques. Toutefois, il est possible de le modifier en fonction des besoins du client. La date et l’heure auxquelles la requête (ou l’événement) se produit est l’horodatage *x*. Tous les enregistrements dans DWB sont regroupés par *trackingid* et triés selon l’horodatage. Le [!DNL Definitions.cfg] fichier Champ obligatoire est un fichier Jeu de données de traitement du journal Inclure qui définit les champs obligatoires : *x-trackingid* et *x-timestamp*.

Remarque : *x-trackingid *dans DWB est un champ incorporé et ce nom ne doit être utilisé pour aucun autre champ.

**Exemple 1**: Création de *x-trackingid* à l’aide de l’ID de cookie (lorsque seules les données en ligne sont utilisées)

Pour créer le *x-trackingid *dans DWB à l’aide de l’ID de cookie, utilisez la fonction de hachage pour créer le *x-trackingid* dans le [!DNL foundation.cfg] fichier (il est recommandé de définir l’ID de suivi dans [!DNL foundation.cfg] mais il peut être défini dans n’importe quel autre fichier de configuration situé sous [!DNL Dataset > log processing] le dossier) comme indiqué ci-dessous :

![](assets/dwb_impl_primary_key1.png)

**Exemple 2**: Création de *x-trackingid* à l’aide de l’ID de courrier électronique (lorsque des données en ligne et hors ligne sont disponibles)

En supposant que les données hors ligne et en ligne soient disponibles (par exemple), et que l’ID de courrier électronique soit disponible dans les deux sources de données. Puisque l’ID de courrier électronique identifie de manière unique un client, il sera utilisé pour créer le *x-trackingid*.

Utilisez la fonction de hachage pour créer le *trackingId* , comme illustré ci-dessous :

![](assets/dwb_impl_primary_key2.png)

