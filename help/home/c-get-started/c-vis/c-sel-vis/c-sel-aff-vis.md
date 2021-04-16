---
description: Dans un espace de travail, une visualisation représente un ensemble de résultats de requête.
title: Compréhension de l’impact d’une sélection sur d’autres visualisations
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
exl-id: 7756646b-9309-41aa-a098-8988f6c065c8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 3%

---

# Compréhension de l’impact d’une sélection sur d’autres visualisations{#understanding-how-a-selection-affects-other-visualizations}

Dans un espace de travail, une visualisation représente un ensemble de résultats de requête.

Lorsque vous effectuez une sélection, le Data Workbench filtres les résultats des requêtes qu’il utilise pour produire les visualisations dans l’espace de travail. Le filtre spécifique varie selon la visualisation.

Les exemples suivants illustrent comment le Data Workbench applique une sélection à trois types différents de visualisations. La consultation de ces exemples vous permet de comprendre l’effet de filtrage des sélections sur les visualisations. Ils vous aident également à comprendre comment interpréter les résultats que vous voyez dans une visualisation filtrée.

* [Filtrage d’une visualisation avec une mesure Sessions](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Filtrage d’une visualisation avec une mesure Visiteuse](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Filtrage d’une visualisation avec une mesure Visiteuse par session](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Filtrage d’une visualisation avec une mesure de sessions {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

Dans cet exemple, l’URI [!DNL /direct.asp/?ldPage=hme] de la visualisation à gauche filtre la mesure pour les sessions affichées dans la visualisation à droite.

![](assets/client-vis1.png)

* **Effet de la sélection sur la Requête:** Data Workbench filtres les sessions pour l’URI sélectionné. Dans cet exemple, la requête qui génère la valeur de l’élément [!DNL /pops/disclosure_pop.asp] est filtrée comme suit :

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **Interprétation de la visualisation :** la visualisation filtrée représente le nombre de sessions qui incluent les URI répertoriés dans la visualisation et  [!DNL /direct.asp/?ldPage=hme]la visualisation. Cet exemple montre qu&#39;il y a eu 1 113 sessions au cours desquelles les visiteurs ont consulté à la fois la page [!DNL /pops/disclosure_pop.asp] et [!DNL /direct.asp/?ldPage=hme] au cours de la même session.

## Filtrage d’une visualisation avec une mesure Visiteuse {#section-97d38c7f03e8457189a9c72d69514ed2}

Dans cet exemple, l’URI [!DNL /direct.asp/?ldPage=home] de la visualisation sur la gauche filtre la mesure pour les Visiteurs dans la visualisation sur la droite.

![](assets/client-vis2.png)

* **Effet de la sélection sur la Requête : le** Data Workbench filtres les Visiteurs pour l’URI sélectionné. Dans cet exemple, la requête qui génère la valeur de l&#39;URI [!DNL /pops/disclosure_pop.asp] est filtrée comme suit :

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **Interprétation de la visualisation :** la visualisation filtrée représente les Visiteurs qui ont consulté les URI répertoriés dans la visualisation et  [!DNL /direct.asp/?ldPage=hme] (mais pas nécessairement au cours de la même session). L&#39;exemple ci-dessus montre que 2 041 visiteurs ont consulté [!DNL /pops/disclosure_pop.asp] et [!DNL /direct.asp/?ldPage=hme].

## Filtrage d’une visualisation avec une mesure Visiteuse par session {#section-f746182311d648dcb98716b0fe846e25}

Dans cet exemple, l’URI [!DNL /direct.asp/?ldPage=hme] de la visualisation sur la gauche filtre la mesure visiteur par session dans la visualisation sur la droite.

![](assets/client-vis3.png)

* **Effet de la sélection sur la Requête : le** Data Workbench filtres les Visiteurs par session pour l’URI sélectionné. Par exemple, la requête qui génère la valeur de l&#39;URI [!DNL /pops/disclosure_pop.asp] est filtrée comme suit :

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **Interprétation de la visualisation :** la visualisation filtrée représente les Visiteurs qui ont consulté les deux URI répertoriés dans la visualisation et  [!DNL /direct.asp/?ldPage=hme] au cours de la même session. Cet exemple montre que 1 069 visiteurs ont vu à la fois [!DNL /pops/disclosure_pop.asp] et [!DNL /direct.asp/?ldPage=hme] au cours d&#39;une seule session.
