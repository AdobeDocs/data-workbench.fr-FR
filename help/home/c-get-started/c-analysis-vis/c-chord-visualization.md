---
description: La visualisation des accords vous permet d’afficher la proportion et la corrélation entre les mesures, en affichant des accords plus grands comme indication d’une corrélation plus forte.
title: Visualisation des accords
uuid: 3f322f58-f8f5-4d91-bdf8-4b5f9d7fb072
exl-id: d712f7b3-de2f-4ca4-a1bf-a2e4d42a084e
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# Visualisation des accords{#chord-visualization}

La visualisation des accords vous permet d’afficher la proportion et la corrélation entre les mesures, en affichant des accords plus grands comme indication d’une corrélation plus forte.

La visualisation des accords vous permet d’identifier les corrélations entre les mesures, ce qui vous permet d’ajouter et d’évaluer facilement les corrélations possibles. Il fournit également une autre vue dans toute [Matrice de corrélation](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html) créée précédemment. À l’aide de la visualisation des accords, vous ne pouvez pas identifier de corrélation positive ou négative entre les mesures, mais seulement si une corrélation existe. Dans certains cas, il est possible d’identifier une relation directe ou inverse en appliquant des mesures de compteur.

1. **Ouvrez la **[!UICONTROL Chord]**visualisation**.

   Dans l’espace de travail, cliquez avec le bouton droit de la souris sur [!DNL Visualization > Predictive Analytics > Chord].

1. **Sélectionnez une Dimension dans le menu**.

   Une visualisation vierge s’ouvre pour vous permettre de sélectionner une dimension. Le nom de la dimension s’affiche en haut de la visualisation des accords vierges.

   >[!NOTE]
   >
   >Si une matrice de corrélation est déjà ouverte dans l’espace de travail, vous pouvez également la rendre sous la forme d’une visualisation des accords.

1. **Choisissez les mesures à corréler**.

   Faites glisser des mesures à partir de **[!UICONTROL Finder]** en cliquant sur **[!UICONTROL Ctrl-Alt]** pour les faire glisser du tableau vers le graphique. Une fois deux mesures ou plus sélectionnées, le graphique s’actualise automatiquement et commence à afficher les données de corrélation. Continuez à ajouter des mesures si nécessaire pour mettre en corrélation des points de données.

   ![](assets/chord_drag_metric.png)

   La visualisation des accords affiche la proportion de l’ensemble représenté par la zone de chaque segment. Continuez à ajouter des mesures en fonction des besoins pour identifier et étudier les relations significatives.

   ![](assets/chord_selected.png)

1. **Visualisez la visualisation des accords**.

   Passez la souris sur chaque mesure de la visualisation pour afficher les relations. Dans cet exemple, vous pouvez voir une corrélation entre les unités et la plupart des autres mesures (à l’exception de la mesure **Durée de visite** ).

   ![](assets/chord_visualization_1.png)

   Lorsque vous passez le curseur sur la mesure **Durée de visite** de la visualisation des accords, vous pouvez constater qu’il existe très peu ou très peu de corrélation entre toutes les autres mesures.

   ![](assets/chord_visualization_2.png)

1. **Modifier les paramètres.** Cliquez avec le bouton droit de la souris sur la visualisation Cordes pour ouvrir un menu afin de modifier la dimension, d’afficher les dimensions sous forme de nombres absolus ou de pourcentages, de supprimer la mesure sélectionnée ou toutes les mesures, de modifier les couleurs et les détails et d’exporter les valeurs vers une Matrice de corrélation.

   ![](assets/chord_menu.png)
