---
description: Les filtres de profil limitent la portée des données disponibles à partir d’un jeu de données.
solution: Analytics
title: Filtres de profil intégrés
topic: Data workbench
uuid: d6854d2c-4643-476e-8a44-f188e18cb115
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Filtres de profil intégrés{#built-in-profile-filters}

Les filtres de profil limitent la portée des données disponibles à partir d’un jeu de données.

Outre les filtres de traitement et de transformation du journal qui peuvent être appliqués avant ou pendant la création d’un jeu de données, d’autres filtres de profil sont disponibles, ce qui a un impact sur la portée des données disponibles pour la sélection à partir d’un jeu de données. Cette section décrit uniquement le dernier type de filtres spéciaux.

Les filtres de profil suivants sont disponibles pour l’utilisateur après la création d’un jeu de données :

* Filtre de sous-ensembles de données
* Filtre de session rompu

>[!NOTE]
>
>D’autres filtres peuvent être créés et appliqués par leur présence dans le répertoire Filtres d’un profil.

## Sous-ensembles de données {#section-0defb44315d94254ab6e629ec3d6f420}

Un sous-ensemble de données agit comme un filtre de données en vous permettant de sélectionner uniquement les éléments de dimension des données qui vous intéressent.

La création de sous-ensembles de données réduit le temps nécessaire pour calculer les réponses exactes à vos requêtes. Si le sous-ensemble de données que vous spécifiez est suffisamment petit, les outils de données peuvent récupérer toutes les données nécessaires à partir d’Insight Server et répondre rapidement et précisément aux questions sur le sous-ensemble. Cela s’avère particulièrement utile si vous savez, par exemple, que l’analyse d’une journée de données ou de sessions à partir d’un référent particulier prendra plusieurs heures.

Les utilisateurs peuvent créer eux-mêmes des sous-ensembles de données ou accéder à des sous-ensembles de données définis dans un profil hérité ou un profil de travail. Lorsqu’un utilisateur crée un sous-ensemble du jeu de données (en sélectionnant les données de votre choix dans Insight, puis en cliquant avec le bouton droit de la souris dans l’espace de travail et en cliquant sur Données > Sous-ensemble), un fichier Data Subset.filter est créé dans le dossier Filtres du répertoire du profil utilisateur. Ce filtre définit le sous-ensemble de données que vous avez sélectionné et enregistre le sous-ensemble pour une utilisation ultérieure.

>[!NOTE]
>
>Vous pouvez créer plusieurs sous-ensembles de données et les activer/désactiver pour afficher différentes parties des données. N’oubliez pas de désactiver le sous-paramétrage des données lorsque vous souhaitez afficher toutes les données. Sinon, les valeurs de vos mesures ne seront pas représentatives de toutes les données du jeu de données.

## Filtre de session rompu {#section-1608e97da6464b11aea27cbb7f3160e4}

Le filtre de session rompue est une formule de mesure qui peut être facilement modifiée pour répondre aux exigences de filtrage. Dans les profils de site par défaut, le filtre de session rompue est configuré pour inclure tous les visiteurs qui ont un indicateur Visitorisé défini sur 1. La valeur 1 indique la présence d’un cookie de suivi pour ce visiteur.

Vous trouverez ci-dessous le texte du fichier Broken Session Filter.filter par défaut fourni par Adobe dans le package de version pour les profils de site.

```
entity = derived_filter:
   formula = string: Visitorized_Flag="1"
   model = ref: wdata/model
```

Par défaut, le filtre Session rompue est appliqué aux espaces de travail pour leur sélection et leurs repères. Il peut être basculé en cliquant avec le bouton droit dans l’espace de travail et en cliquant sur Données > Filtre Session rompue.

Le filtre de session rompue peut être référencé dans les expressions de filtre sous la forme Broken_Session_Filter, même s’il n’est pas activé pour l’espace de travail actif. Voir Expressions [de](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Identifiers) filtre pour plus d’informations.
