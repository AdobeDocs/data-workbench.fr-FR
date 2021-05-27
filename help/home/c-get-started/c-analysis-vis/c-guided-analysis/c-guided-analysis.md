---
description: Une visualisation d’analyse guidée fournit des indices pour une analyse plus approfondie en fonction des sélections que vous effectuez dans un espace de travail.
title: Analyse guidée
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
exl-id: c19b52b6-52db-455e-adde-8b2400aae006
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---

# Analyse guidée{#guided-analysis}

Une visualisation d’analyse guidée fournit des indices pour une analyse plus approfondie en fonction des sélections que vous effectuez dans un espace de travail.

Cette visualisation vous aide à identifier les dimensions qui peuvent vous fournir plus d’informations, c’est-à-dire celles qui sont les plus fortement corrélées avec vos sélections. La visualisation d’analyse guidée dans votre application d’Adobe affiche les dimensions pertinentes pour votre jeu de données, comme dans la [!DNL Site] visualisation d’analyse guidée suivante.

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>Si un nom de dimension s’affiche en rouge, il n’est pas défini dans votre jeu de données.

Lorsque vous effectuez une sélection dans un espace de travail, la visualisation d’analyse guidée affiche des coches à gauche et des points à droite des dimensions pour indiquer lesquelles fournissent les informations les plus pertinentes :

* **Cochez** marksidentifier les dimensions dont les valeurs diffèrent de la référence d’une manière statistiquement significative (c’est-à-dire que la différence entre la sélection et la référence n’est pas due à une chance aléatoire).
* **** Les diagrammes indiquent le degré de différence entre la sélection et la référence. Le premier point représente la statistique U, le second la statistique V. Voir [Présentation des mesures statistiques](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708). Plus les points sont clairs et plus grands, plus la différence est grande et plus les informations relatives à la dimension selon votre sélection sont pertinentes (c’est-à-dire que les points plus clairs et plus grands représentent des informations plus utiles).
