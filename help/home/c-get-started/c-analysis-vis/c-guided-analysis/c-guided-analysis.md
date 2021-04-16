---
description: Une visualisation d’analyses guidées fournit des indices pour une analyse plus poussée en fonction des sélections que vous effectuez dans un espace de travail.
title: Analyse guidée
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
exl-id: c19b52b6-52db-455e-adde-8b2400aae006
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---

# Analyse guidée{#guided-analysis}

Une visualisation d’analyses guidées fournit des indices pour une analyse plus poussée en fonction des sélections que vous effectuez dans un espace de travail.

Cette visualisation vous aide à identifier les dimensions qui peuvent vous fournir davantage d’informations, c’est-à-dire celles qui sont les plus fortement corrélées à vos sélections. La visualisation des analyses guidées dans votre application d’Adobe affiche les dimensions pertinentes pour votre jeu de données, comme dans la [!DNL Site] visualisation d’analyse guidée suivante.

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>Si un nom de dimension s’affiche en rouge, il n’est pas défini dans votre jeu de données.

Lorsque vous effectuez une sélection dans un espace de travail, la visualisation des analyses guidées affiche des coches à gauche et des points à droite des dimensions pour indiquer lesquelles fournissent les informations les plus pertinentes :

* **Cochez la** coche marketing pour identifier les dimensions dont les valeurs diffèrent de l’indice de référence d’une manière statistiquement significative (c’est-à-dire que la différence entre la sélection et l’indice de référence n’est pas due à une chance aléatoire).
* **Les** chiffres indiquent le degré de différence entre la sélection et l&#39;indice de référence. Le premier point représente la statistique U et le second point la statistique V. Voir [Comprendre les mesures statistiques](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708). Plus les points sont lumineux et grands, plus la différence est grande et plus les informations relatives à la dimension en fonction de votre sélection sont pertinentes (c’est-à-dire que les points plus clairs et plus grands représentent des informations plus utiles).
