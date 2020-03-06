---
description: La visualisation Tableau d’association vous permet d’associer des mesures à des mesures, des dimensions et des éléments de dimension à l’aide de l’algorithme V de Cramer.
title: Visualisation du tableau d’association
uuid: 4563c336-3377-4929-8694-8c0d00866825
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Visualisation du tableau d’association{#association-table-visualization}

La visualisation Tableau d’association vous permet d’associer des mesures à des mesures, des dimensions et des éléments de dimension à l’aide de l’algorithme V de Cramer.

Le tableau Association compare les valeurs avec le calcul V de Cramer au lieu d&#39;utiliser le coefficient de corrélation de Pearson, tel qu&#39;utilisé dans les visualisations Matrice [de](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html) corrélation et Correspondance Chord [(il ne peut comparer que les mesures, tandis que le tableau Association et le Corail](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html) [](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445) Association peuvent comparer les mesures, les dimensions et les éléments).

## Création d’une table d’association {#section-87ed12ccc1af4196a1b6534e621c4cbb}

Le tableau Association compare les mesures sur une dimension dénombrable ou non dénombrable. Le tableau peut être modifié pour mettre en surbrillance les associations au sein de la visualisation par sélection de couleurs ou pour le rendre sous forme de zone textuelle, de carte thermique ou les deux.

1. Ouvrez une table d’association.

   Cliquez avec le bouton droit [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table].

   ![](assets/association_table.png)

1. Sélectionnez une dimension étendue (une dimension Clics publicitaires, Accès, Produit, Visite ou Visiteur). Une table d’association s’ouvre avec la dimension étendue identifiée dans le coin et la mesure associée placée à la fois dans la ligne et la colonne.

   ![](assets/association_table1.png)

   Le tableau Associations utilise le V de Cramer comme corrélation symétrique, ce qui entraîne la sélection de mesures, de dimensions et de valeurs d’éléments reflétées dans les colonnes et les lignes d’un tableau d’association. Par exemple, la sélection de la dimension étendue **Produit** utilise la **[!UICONTROL Visits]** mesure en tant que mesure associée dans la ligne et la colonne du tableau, ce qui entraîne une comparaison parfaite mais inutile (1,00) car les valeurs comparées sont identiques.

1. Ajoutez d’autres valeurs au tableau Association.

   Cliquez avec le bouton droit dans une colonne ou une ligne et sélectionnez **Ajouter une mesure** ou **Ajouter une dimension**. Vous pouvez également faire glisser des mesures et des dimensions depuis un panneau **Finder** . Vous pouvez également faire glisser des éléments de dimension d’un tableau ouvert vers la visualisation du tableau.

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >Le tableau Association ne peut pas contenir plus de dix lignes et colonnes.

