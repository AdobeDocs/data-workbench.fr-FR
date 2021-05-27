---
description: Les filtres de profil limitent la portée des données disponibles à partir d’un jeu de données.
title: Filtres de profil intégrés
uuid: d6854d2c-4643-476e-8a44-f188e18cb115
exl-id: bb167487-415d-44a8-9a0a-9a76d90ba5c0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 1%

---

# Filtres de profil intégrés{#built-in-profile-filters}

Les filtres de profil limitent la portée des données disponibles à partir d’un jeu de données.

Outre les filtres de traitement et de transformation des journaux qui peuvent être appliqués avant ou pendant la création d’un jeu de données, d’autres filtres de profil sont disponibles, ce qui a un impact sur la portée des données disponibles pour la sélection à partir d’un jeu de données. Cette section décrit uniquement le dernier type de filtres spéciaux.

Les filtres de profil suivants sont disponibles pour l’utilisateur après la création d’un jeu de données :

* Filtre de sous-ensembles de données
* Filtre de session rompu

>[!NOTE]
>
>D’autres filtres peuvent être créés et appliqués par leur présence dans le répertoire Filtres d’un profil.

## Sous-paramétrage des données {#section-0defb44315d94254ab6e629ec3d6f420}

Un sous-ensemble de données agit comme un filtre de données en vous permettant de sélectionner uniquement les éléments de dimension des données qui vous intéressent.

La création de sous-ensembles de données réduit le temps nécessaire au calcul des réponses exactes à vos requêtes. Si le sous-ensemble de données que vous spécifiez est suffisamment petit, Data Workbench peut récupérer toutes les données nécessaires à partir d’Insight Server et répondre rapidement et précisément aux questions sur le sous-ensemble. Cela s’avère particulièrement utile si vous savez, par exemple, que l’analyse d’un jour de données ou de sessions à partir d’un référent particulier prendra plusieurs heures.

Les utilisateurs peuvent créer eux-mêmes des sous-ensembles de données ou accéder à des sous-ensembles de données définis dans un profil hérité ou opérationnel. Lorsqu’un utilisateur crée un sous-ensemble du jeu de données (en sélectionnant les données souhaitées dans Insight, puis en cliquant avec le bouton droit de la souris dans l’espace de travail, puis en cliquant sur Données > Sous-ensemble), un fichier Data Subset.filter est créé dans le dossier Filtres du répertoire du profil utilisateur. Ce filtre définit le sous-ensemble de données que vous avez sélectionné et enregistre le sous-ensemble en vue d’une utilisation ultérieure.

>[!NOTE]
>
>Vous pouvez créer plusieurs sous-ensembles de données et les faire basculer pour afficher différentes parties des données. N’oubliez pas de désactiver le sous-paramétrage des données lorsque vous souhaitez afficher toutes les données. Sinon, vos valeurs de mesure ne seront pas représentatives de toutes les données du jeu de données.

## Filtre de session rompu {#section-1608e97da6464b11aea27cbb7f3160e4}

Le filtre de session interrompue est une formule de mesure qui peut être facilement modifiée pour répondre à toutes les exigences de filtrage. Dans les profils de site par défaut, le filtre de session rompu est configuré pour inclure tous les visiteurs dont l’indicateur Visitorisé est défini sur 1. La valeur 1 indique la présence d’un cookie de suivi pour ce visiteur.

Voici le texte du fichier Broken Session Filter.filter par défaut fourni par Adobe dans le package de version pour les profils du site.

```
entity = derived_filter:
   formula = string: Visitorized_Flag="1"
   model = ref: wdata/model
```

Par défaut, le filtre Session interrompue est appliqué aux espaces de travail pour leur sélection et leurs références. Il peut être activé en cliquant avec le bouton droit de la souris dans l’espace de travail et en cliquant sur Données > Filtre de session endommagé.

Le filtre de session rompu peut être référencé dans les expressions de filtre sous la forme Broken_Session_Filter, même s’il n’est pas activé pour l’espace de travail actuel. Voir [expressions de filtre](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Identifiers) pour plus d’informations.
