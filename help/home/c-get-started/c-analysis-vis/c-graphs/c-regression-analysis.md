---
description: Le graphique à barres dans les outils de données inclut désormais une comparaison de régression pour plusieurs mesures sur plusieurs graphiques.
title: Graphique Analyse de régression
uuid: 8512890e-f42b-4dce-826a-2b4bf2a215f4
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Regression Analysis Graph{#regression-analysis-graph}

Le graphique à barres dans les outils de données inclut désormais une comparaison de régression pour plusieurs mesures sur plusieurs graphiques.

[Les graphiques](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/graphs/c-graphs.html) à barres dans les Outils de données vous permettent de faire passer les mesures d’un graphique à des mesures d’un autre graphique. Si vous disposez de plusieurs graphiques, vous pouvez comparer une mesure (en tant que variable indépendante) à un graphique évaluant d’autres mesures (en tant que variables dépendantes). Cela vous permet de déterminer l’intensité de la relation entre une variable dépendante (la mesure établie en premier) et une série d’autres mesures changeantes (régressions avec la mesure dépendante établie).

L’analyse de régression sur une visualisation graphique permet aux analystes d’exécuter des scénarios &quot;et si&quot;. Par exemple, si les visites augmentent à ce niveau, quel impact cette augmentation aura-t-elle sur les recettes ?

**Configuration de l’analyse de régression**

1. Sélectionnez le graphique comme mesure dépendante pour une comparaison de régression.

   Cliquez avec le bouton droit sur le graphique et sélectionnez **Définir comme mesure de base pour la régression**.

   ![](assets/c_graph_regression_1.png)

1. Définissez d’autres graphiques de mesures en tant que variables indépendantes.

   Cliquez avec le bouton droit de la souris sur la mesure et sélectionnez **[!UICONTROL Regress with `<base metric name>`]** d’autres mesures.

   ![](assets/c_graph_regression.png)

1. Affichez la régression en cliquant avec le bouton droit sur le graphique pour déplacer la barre vers le haut et vers le bas.

   Si vous cliquez avec le bouton droit de la souris sur le graphique pour une valeur spécifique, vous pouvez voir les ratios de régression pour chaque mesure en fonction des valeurs ascendantes ou descendantes.

   ![](assets/c_graph_regression_2.png)

   Par exemple, si mes Pages vues passent à 86 041, les autres mesures auront les valeurs suivantes : Visites à 12 183 et Visiteurs par Visite à 12 028.

   ![](assets/c_graph_regression_3.png)

   Si les valeurs Visiteurs par visite passent à 26 141, les autres mesures seront Visites à 26 560 et Pages vues à 189 091.

