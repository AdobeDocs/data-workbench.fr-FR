---
description: Une visualisation d’analyse guidée fournit des indices pour une analyse plus approfondie en fonction des sélections que vous effectuez dans un espace de travail.
solution: Analytics
title: Analyse guidée
topic: Data workbench
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Analyse guidée{#guided-analysis}

Une visualisation d’analyse guidée fournit des indices pour une analyse plus approfondie en fonction des sélections que vous effectuez dans un espace de travail.

Cette visualisation vous aide à identifier les dimensions qui peuvent vous fournir plus d’informations, c’est-à-dire celles qui sont les plus étroitement corrélées avec vos sélections. La visualisation de l’analyse guidée dans votre application Adobe affiche les dimensions pertinentes pour votre jeu de données, comme dans la visualisation de l’analyse [!DNL Site] guidée suivante.

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>Si un nom de dimension s’affiche en rouge, il n’est pas défini dans votre jeu de données.

Lorsque vous effectuez une sélection dans un espace de travail, la visualisation de l’analyse guidée affiche des coches à gauche et des points à droite des dimensions pour indiquer ceux qui fournissent les informations les plus pertinentes :

* **Les coches** identifient les dimensions dont les valeurs diffèrent de la référence d’une manière statistiquement significative (c’est-à-dire que la différence entre la sélection et la référence n’est pas due à une chance aléatoire).
* **Les points** indiquent le degré de différence entre la sélection et la référence. Le premier point représente la statistique U et le second, la statistique V. Voir [Compréhension des mesures](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708)statistiques. Plus les points sont lumineux et grands, plus la différence est grande et plus les informations relatives à la dimension en fonction de votre sélection sont pertinentes (c’est-à-dire, plus les points sont lumineux, plus les points sont grands, plus les informations sont utiles).

