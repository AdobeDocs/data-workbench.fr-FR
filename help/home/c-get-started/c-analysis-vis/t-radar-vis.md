---
description: Les graphiques radar permettent de se concentrer rapidement sur les domaines qui nécessitent le plus d’attention, en fournissant une vue visuelle d’un ensemble de mesures et de la manière dont elles sont liées ou diffèrent.
solution: Analytics
title: Visualisation radar
topic: Data workbench
uuid: 39d67743-b6c1-46f1-99fd-7c71dfe07932
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualisation radar{#radar-visualization}

Les graphiques radar permettent de se concentrer rapidement sur les domaines qui nécessitent le plus d’attention, en fournissant une vue visuelle d’un ensemble de mesures et de la manière dont elles sont liées ou diffèrent.

Vous avez souvent besoin de plusieurs mesures pour comprendre et évaluer des observations sélectionnées dans un espace de travail.

Cette visualisation se révèle particulièrement utile pour les comparaisons ou les repères entre les sélections de tableau. Par exemple, vous pouvez ajouter un tableau de l’espace de travail qui répertorie les magasins, puis ajouter une visualisation radar avec des mesures telles que Recettes, Visiteurs et Pages vues. (Comme illustré à l’écran dans la procédure suivante.) Lorsque vous effectuez des sélections de magasin dans le tableau, l’empreinte du graphique radar se déplace, identifiant les faiblesses ou les forces des mesures du magasin sélectionné.

Chaque radiale d’un graphique radar est une mesure et au moins trois mesures sont requises. Les données de mesure sont tracées par rapport à une mesure ancrée. La mesure ancrée et le paramètre Ajuster à l’ancre de chaque mesure déterminent la mise à l’échelle des mesures par rapport aux repères.

**Pour créer une visualisation radar**

1. Cliquez avec le bouton droit de la souris dans Workspace, puis cliquez sur **[!UICONTROL Visualization]** > **[!UICONTROL Radar]**.

   ![](assets/client-rad.png)

1. Pour ajouter des mesures, cliquez avec le bouton droit de la souris dans la visualisation et sélectionnez **[!UICONTROL Add Metric]**.
1. Pour ancrer une mesure au graphique, cliquez avec le bouton droit sur une mesure et choisissez l’option suivante :

   **Ancre à cette mesure :** Utilise cette mesure comme point de repère auquel d’autres mesures sont tracées. Vous pouvez ancrer une mesure à la fois. Chaque mesure du graphique est filtrée par la sélection de l’espace de travail actif ou par aucun filtre. Le rapport de référence entre ces deux valeurs est tracé sur l’axe entre le centre du graphique et le nom de la mesure sur le radar. Zéro est tracé au centre.

1. Pour mettre à l’échelle une mesure avec la mesure ancrée, cliquez dessus avec le bouton droit de la souris et choisissez l’option suivante :

   **Echelle avec ancre :** Lorsqu’elle est activée, l’axe de cette mesure est mis à l’échelle de sorte que le ratio de référence de la mesure d’ancrage sélectionnée soit tracé dans le cercle, avec zéro au centre. Lorsqu’il n’est pas sélectionné, le cercle représente un ratio de référence de 1. En règle générale, vous activez l’option Echelle avec ancrage pour les mesures dénombrables, telles que Visiteurs ou Pages vues, et vous la désactivez pour les mesures de ratio, telles que Conversion, Durée moyenne de la session ou Pages vues par session.

