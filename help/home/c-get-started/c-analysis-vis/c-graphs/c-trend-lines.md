---
description: Les lignes de tendances vous permettent de superposer des graphiques pour comparer et interpréter les données.
title: Lignes de tendance
uuid: b1d81973-2181-4507-a0a5-adf5eeb9f926
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Lignes de tendance{#trend-lines}

Les lignes de tendances vous permettent de superposer des graphiques pour comparer et interpréter les données.

À l’instar de la visualisation en graphique de [dispersion](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/c-scat-plots.html) , vous pouvez désormais définir des lignes de tendances sur une visualisation graphique afin d’afficher le taux de changement en fonction de lignes linéaires, exponentielles, de puissance ou polynomiales. La fonction Ligne de tendance permet d’incruster des lignes de tendance sur un graphique, le plus souvent sur une dimension de temps.

Par exemple, dans cette comparaison graphique, nous voyons que les visites sont en tendance à la hausse, mais que les commandes sont en tendance à la baisse.

![](assets/trend_line.png)

Pour ajouter une ligne de tendance

1. Ouvrez un graphique et cliquez avec le bouton droit sur le nom de la mesure dans le coin supérieur gauche.
1. Cliquez sur **[!UICONTROL Trend Lines]** puis sélectionnez une option.

   ![](assets/trend_line_graph.png)

   Vous pouvez sélectionner la ligne de tendance à afficher sur le graphique sous la forme **Linéaire** simple, **Exponentiel**, **Puissance** ou **Polynomial.** Polynomial crée une ligne de tendance de régression polynomiale. Linéaire simple crée une ligne de tendance comme taux de changement le long de la ligne de régression. Exponential calcule une ligne de tendance sous la forme y = b*exp( a*x ) et Power sous la forme y = b*x`<sup>a</sup>`.

   La tendance sera calculée et rendue sur le graphique, et une légende s’ouvrira, affichant des informations détaillées sur l’équation de tendance.

   ![](assets/trend_line_detail.png)

