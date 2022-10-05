---
description: Dans un espace de travail, une visualisation représente un ensemble de résultats de requête.
title: Compréhension de l’impact d’une sélection sur d’autres visualisations
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
exl-id: 7756646b-9309-41aa-a098-8988f6c065c8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 3%

---

# Compréhension de l’impact d’une sélection sur d’autres visualisations{#understanding-how-a-selection-affects-other-visualizations}

{{eol}}

Dans un espace de travail, une visualisation représente un ensemble de résultats de requête.

Lorsque vous effectuez une sélection, Data Workbench filtre les résultats des requêtes qu’il utilise pour produire les visualisations dans l’espace de travail. Le filtre spécifique varie selon la visualisation.

Les exemples suivants illustrent la manière dont Data Workbench applique une sélection à trois types différents de visualisations. La consultation de ces exemples vous aide à comprendre l’effet de filtrage des sélections sur les visualisations. Ils vous aident également à comprendre comment interpréter les résultats que vous voyez dans une visualisation filtrée.

* [Filtrage d’une visualisation avec une mesure Sessions](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Filtrage d’une visualisation avec une mesure Visiteurs](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Filtrage d’une visualisation avec une mesure Visiteurs par session](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Filtrage d’une visualisation avec une mesure Sessions {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

Dans cet exemple, la variable [!DNL /direct.asp/?ldPage=hme] L’URI dans la visualisation à gauche filtre la mesure pour les sessions affichées dans la visualisation à droite.

![](assets/client-vis1.png)

* **Effet de la sélection sur la requête :** Data Workbench filtre les sessions pour l’URI sélectionné. Dans cet exemple, la requête qui génère la valeur de la propriété [!DNL /pops/disclosure_pop.asp] est filtré comme suit :

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **Interprétation de la visualisation :** La visualisation filtrée représente le nombre de sessions qui incluent les URI répertoriés dans la visualisation et [!DNL /direct.asp/?ldPage=hme]. Cet exemple montre qu’il y avait 1 113 sessions au cours desquelles les visiteurs ont consulté les deux [!DNL /pops/disclosure_pop.asp] et [!DNL /direct.asp/?ldPage=hme] au cours de la même session.

## Filtrage d’une visualisation avec une mesure Visiteurs {#section-97d38c7f03e8457189a9c72d69514ed2}

Dans cet exemple, la variable [!DNL /direct.asp/?ldPage=home] L’URI dans la visualisation à gauche filtre la mesure Visiteurs dans la visualisation à droite.

![](assets/client-vis2.png)

* **Effet de la sélection sur la requête :** Data Workbench filtre les visiteurs pour l’URI sélectionné. Dans cet exemple, la requête qui génère la valeur de la propriété [!DNL /pops/disclosure_pop.asp] L’URI est filtré comme suit :

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **Interprétation de la visualisation :** La visualisation filtrée représente les visiteurs qui ont consulté les URI répertoriés dans la visualisation et [!DNL /direct.asp/?ldPage=hme] (mais pas nécessairement au cours de la même session). L’exemple ci-dessus montre que 2 041 visiteurs ont consulté les deux [!DNL /pops/disclosure_pop.asp] et [!DNL /direct.asp/?ldPage=hme].

## Filtrage d’une visualisation avec une mesure Visiteurs par session {#section-f746182311d648dcb98716b0fe846e25}

Dans cet exemple, la variable [!DNL /direct.asp/?ldPage=hme] L’URI dans la visualisation à gauche filtre la mesure pour visiteur par session dans la visualisation à droite.

![](assets/client-vis3.png)

* **Effet de la sélection sur la requête :** Data Workbench filtre les visiteurs par session pour l’URI sélectionné. Par exemple, la requête qui génère la valeur de la variable [!DNL /pops/disclosure_pop.asp] L’URI est filtré comme suit :

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **Interprétation de la visualisation :** La visualisation filtrée représente les visiteurs qui ont consulté les deux URI répertoriés dans la visualisation et [!DNL /direct.asp/?ldPage=hme] au cours de la même session. Cet exemple montre que 1 069 visiteurs ont vu les deux [!DNL /pops/disclosure_pop.asp] et [!DNL /direct.asp/?ldPage=hme] au cours d’une seule session.
