---
description: Les graphiques radar permettent de se concentrer rapidement sur les domaines qui ont le plus besoin d'attention, en fournissant une vue visuelle d'un ensemble de mesures, et en indiquant comment elles se rapportent ou diffèrent.
title: Visualisation du radar
uuid: 39d67743-b6c1-46f1-99fd-7c71dfe07932
exl-id: 5385d903-422b-4936-bbb3-0d5ee4d286de
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---

# Visualisation du radar{#radar-visualization}

Les graphiques radar permettent de se concentrer rapidement sur les domaines qui ont le plus besoin d&#39;attention, en fournissant une vue visuelle d&#39;un ensemble de mesures, et en indiquant comment elles se rapportent ou diffèrent.

Vous avez souvent besoin de plusieurs mesures pour comprendre et évaluer les observations sélectionnées dans un espace de travail.

Cette visualisation est utile pour les comparaisons ou les repères entre les sélections de tableau. Par exemple, vous pouvez ajouter un tableau d’espace de travail qui stocke des listes, puis ajouter une visualisation radar avec des mesures telles que Recettes, Visiteurs et Vues de page. (Comme indiqué à l’écran dans la procédure suivante.) Au fur et à mesure que vous effectuez les sélections dans le tableau, l&#39;empreinte du graphique radar se déplace, en identifiant les faiblesses ou les forces dans les mesures pour le magasin sélectionné.

Chaque rayon d&#39;un graphique radar est une mesure et au moins trois mesures sont requises. Les données de mesure sont tracées par rapport à une mesure ancrée. La mesure ancrée et le paramètre Ajuster à l’ancre de chaque mesure déterminent la mise à l’échelle des mesures par rapport aux repères.

**Pour créer une visualisation radar**

1. Cliquez avec le bouton droit de la souris dans Workspace, puis cliquez sur **[!UICONTROL Visualization]** > **[!UICONTROL Radar]**.

   ![](assets/client-rad.png)

1. Pour ajouter des mesures, cliquez avec le bouton droit de la souris dans la visualisation et sélectionnez **[!UICONTROL Add Metric]**.
1. Pour ancrer une mesure au graphique, cliquez avec le bouton droit de la souris sur une mesure et choisissez l’option suivante :

   **Ancrage à cette mesure :** Utilise cette mesure comme référence à laquelle d’autres mesures sont tracées. Vous pouvez ancrer une mesure à la fois. Chaque mesure du graphique est filtrée par la principale sélection d’espace de travail ou par l’absence de filtre. Le rapport de référence entre ces deux valeurs est tracé sur l&#39;axe entre le centre du graphique et le nom de la mesure sur le radar. Zéro est tracé au centre.

1. Pour mettre à l’échelle une mesure avec la mesure ancrée, cliquez avec le bouton droit de la souris sur la mesure et choisissez l’option suivante :

   **Ajuster à l’échelle avec ancrage :** lorsque cette option est activée, l’axe de cette mesure est mis à l’échelle de sorte que le rapport de référence de la mesure d’ancrage sélectionnée soit tracé en cercle, avec zéro au centre. Lorsqu’il n’est pas sélectionné, le cercle représente un ratio de référence de 1. En règle générale, vous activez l’option Ajuster à l’aide de l’ancre pour les mesures dénombrables, telles que les Visiteurs ou les Vues de page, et vous la désactivez pour les mesures de ratio, telles que Conversion, Durée moyenne de la session ou Vues de page par session.
