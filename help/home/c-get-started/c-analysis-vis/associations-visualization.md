---
description: La visualisation du tableau d’association vous permet d’associer des mesures à des mesures, des dimensions et des éléments de dimension à l’aide de l’algorithme V de Cramer.
title: Visualisation du tableau d’association
uuid: 4563c336-3377-4929-8694-8c0d00866825
exl-id: 3fc2c025-d369-45ed-8c9e-eb4a0ac412b7
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# Visualisation du tableau d’association{#association-table-visualization}

La visualisation du tableau d’association vous permet d’associer des mesures à des mesures, des dimensions et des éléments de dimension à l’aide de l’algorithme V de Cramer.

Le tableau d’association compare les valeurs avec le calcul V de Cramer plutôt qu’en utilisant le coefficient de corrélation de Pearson, comme utilisé dans les visualisations [Matrice de corrélation](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html) et [Corrélation des accords](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html) (elles peuvent uniquement comparer des mesures, tandis que le tableau d’association et le [accord d’association](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445) peuvent comparer des mesures, des dimensions et des éléments).

## Créer un tableau d’association {#section-87ed12ccc1af4196a1b6534e621c4cbb}

Le tableau Association compare les mesures sur une dimension dénombrable ou non dénombrable. Le tableau peut être modifié pour mettre en surbrillance les associations au sein de la visualisation par sélection de couleur ou pour le rendre sous forme de carte textuelle, de carte thermique, ou les deux.

1. Ouvrez un tableau d’association.

   Cliquez avec le bouton droit de la souris [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table].

   ![](assets/association_table.png)

1. Sélectionnez une dimension étendue : un clic publicitaire, un accès, un produit, une visite ou une dimension Visiteur. Un tableau d’association s’ouvre avec la dimension étendue identifiée dans le coin et la mesure associée placée à la fois dans la ligne et la colonne.

   ![](assets/association_table1.png)

   Le tableau Associations utilise le V de Cramer comme corrélation symétrique, ce qui entraîne la sélection de mesures, de dimensions et de valeurs d’éléments dans les colonnes et les lignes d’un tableau d’association. Par exemple, la sélection de la dimension étendue **Produit** utilise la mesure **[!UICONTROL Visits]** comme mesure associée à la fois à la ligne et à la colonne du tableau, ce qui se traduit par une comparaison parfaite mais inutile (1,00), car les valeurs comparées sont identiques.

1. Ajoutez d’autres valeurs au tableau Association.

   Cliquez avec le bouton droit dans une colonne ou une ligne et sélectionnez **Ajouter une mesure** ou **Ajouter une Dimension**. Vous pouvez également faire glisser des mesures et des dimensions à partir d’un panneau **Finder**. Il est également possible de faire glisser des éléments de Dimension d’un tableau ouvert vers la visualisation de tableau.

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >La table d&#39;association est limitée à dix lignes et colonnes.
