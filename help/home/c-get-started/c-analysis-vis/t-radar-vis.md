---
description: Les graphiques radars permettent de se concentrer rapidement sur les domaines qui ont le plus besoin d’attention, en fournissant un aperçu visuel d’un ensemble de mesures et de leur relation ou différence.
title: Visualisation du radar
uuid: 39d67743-b6c1-46f1-99fd-7c71dfe07932
exl-id: 5385d903-422b-4936-bbb3-0d5ee4d286de
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---

# Visualisation du radar{#radar-visualization}

{{eol}}

Les graphiques radars permettent de se concentrer rapidement sur les domaines qui ont le plus besoin d’attention, en fournissant un aperçu visuel d’un ensemble de mesures et de leur relation ou différence.

Plusieurs fois, vous avez besoin de plusieurs mesures pour comprendre et évaluer les observations sélectionnées dans un espace de travail.

Cette visualisation est utile pour les comparaisons ou les références entre les sélections de tableau. Par exemple, vous pouvez ajouter un tableau de l’espace de travail qui répertorie les magasins, puis ajouter une visualisation radar avec des mesures telles que Recettes, Visiteurs et Pages vues. (Comme illustré dans l’écran de la procédure suivante.) Lorsque vous effectuez des sélections de magasin dans le tableau, l’encombrement du graphique radar change, en identifiant les faiblesses ou les forces des mesures pour le magasin sélectionné.

Chaque radiale d’un graphique radar est une mesure et au moins trois mesures sont requises. Les données de mesure sont tracées par rapport à une mesure ancrée. La mesure ancrée et le paramètre Échelle à l’ancre pour chaque mesure déterminent la mise à l’échelle des mesures par rapport aux références.

**Pour créer une visualisation radar**

1. Cliquez avec le bouton droit de la souris dans Workspace, puis cliquez sur **[!UICONTROL Visualization]** > **[!UICONTROL Radar]**.

   ![](assets/client-rad.png)

1. Pour ajouter des mesures, cliquez avec le bouton droit de la souris dans la visualisation, puis sélectionnez **[!UICONTROL Add Metric]**.
1. Pour ancrer une mesure dans le graphique, cliquez avec le bouton droit de la souris sur une mesure et choisissez l’option suivante :

   **Ancre à cette mesure :** Utilise cette mesure comme référence à laquelle d’autres mesures sont tracées. Vous pouvez ancrer une mesure à la fois. Chaque mesure du graphique est filtrée par la principale sélection de l’espace de travail ou par aucun filtre. Le rapport de référence entre ces deux valeurs est tracé sur l’axe entre le centre du graphique et le nom de la mesure sur le radar. Zéro est tracé au centre.

1. Pour mettre à l’échelle une mesure avec la mesure ancrée, cliquez avec le bouton droit de la souris sur la mesure et choisissez l’option suivante :

   **Échelle avec ancre :** Lorsqu’elle est activée, l’axe de cette mesure est mis à l’échelle de sorte que le rapport d’évaluation de la mesure d’ancrage sélectionnée soit tracé en cercle, avec zéro au centre. Lorsqu’il n’est pas sélectionné, le cercle représente un ratio de référence de 1. En règle générale, vous activez l’option Échelle avec ancre pour les mesures dénombrables, telles que Visiteurs ou Pages vues, et la désactivez pour les mesures de rapport, telles que Conversion, Durée moyenne de la session ou Pages vues par session.
