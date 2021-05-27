---
description: Les graphiques de dispersion représentent les éléments d’une dimension de données (telle que Page ou Ville) sur une grille dans laquelle les axes x et y représentent différentes mesures.
title: Graphiques de dispersion 2D
uuid: 73c23d22-3c3a-4535-b66b-0e3508bd904c
exl-id: 340f8c18-ce47-4f3a-aba4-3d6124505313
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 1%

---

# Graphiques de dispersion 2D{#d-scatter-plots}

Les graphiques de dispersion représentent les éléments d’une dimension de données (telle que Page ou Ville) sur une grille dans laquelle les axes x et y représentent différentes mesures.

Les graphiques de dispersion peuvent s’avérer utiles lorsque vous essayez de comprendre la relation entre un grand nombre d’éléments disparates, selon deux mesures différentes. Dans l’exemple suivant, le graphique de dispersion montre chaque ville selon le nombre de visiteurs et le taux de rétention respectif.

![](assets/vis_ScatterPlot_City.png)

Le graphique de dispersion permet de voir rapidement les valeurs aberrantes. Par exemple, le taux de rétention par visiteur est supérieur à la moyenne.

Les graphiques de dispersion peuvent également être utilisés pour montrer la cohérence des données. Dans l’exemple suivant, le graphique de dispersion indique le nombre de visiteurs avec des sessions d’une durée particulière.

![](assets/vis_ScatterPlot_SessionDuration.png)

La taille de chaque point du graphique de dispersion est déterminée par la mesure de rayon. La mesure de rayon par défaut diffère pour chaque application d’Adobe. Par exemple, dans [!DNL Site], la mesure du rayon est basée sur les sessions par défaut. Vous pouvez modifier la mesure de rayon afin que les points de vos graphiques de dispersion représentent n’importe quelle mesure disponible. Pour connaître les étapes à suivre, voir [Modification des mesures de rayon](../../../home/c-get-started/c-analysis-vis/c-scat-plots.md#section-fd80576d583c430cb469daf12e39aa2a) La couleur des points est basée sur la légende de couleur qui est ouverte dans l’espace de travail. Pour plus d’informations sur les légendes de couleur, voir [Légendes de couleur](../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

## Sélectionner des points {#section-4b4d45f39b884d54bb7407b3b2f4ea50}

**Pour sélectionner un seul point**

* Cliquez sur le point.

**Pour ajouter un autre point ou groupe de points à votre sélection**

* Ctrl+clic sur un point ou Ctrl+glisser sur plusieurs points.

**Pour supprimer un point ou un groupe de points de votre sélection**

* Maintenez la touche Maj enfoncée et cliquez sur un point ou faites glisser le curseur sur plusieurs points.

## Modification des dimensions {#section-796cd962ef3f476caa89d99083782ed1}

* Cliquez avec le bouton droit sur le libellé de la dimension en haut du graphique, puis cliquez sur **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]***.

## Modification des mesures {#section-44b8be9215cd4039b1eeb98ae1b31445}

**Pour modifier la mesure affichée sur l’axe x ou y d’un graphique de dispersion**

* Cliquez avec le bouton droit sur le libellé de la mesure à modifier, puis cliquez sur **[!UICONTROL Change Metric]** > *&lt;**[!UICONTROL metric name]***.

## Modification des mesures de rayon {#section-fd80576d583c430cb469daf12e39aa2a}

**Pour modifier la mesure du rayon d’un graphique de dispersion**

Cliquez avec le bouton droit sur le libellé de la dimension en haut du graphique, puis cliquez sur **[!UICONTROL Change Radius Metric]** > *&lt;**[!UICONTROL metric name]***.

![](assets/mnu_ScatterPlot_Change.png)
