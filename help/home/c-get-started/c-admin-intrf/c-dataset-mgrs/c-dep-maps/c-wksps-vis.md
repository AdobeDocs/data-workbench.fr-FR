---
description: Informations conceptuelles sur les espaces de travail et les visualisations.
title: Espaces de travail et visualisations
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
exl-id: a70748dd-8190-4d1b-9ee1-1011b73a1a86
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 3%

---

# Espaces de travail et visualisations{#workspaces-and-visualizations}

Informations conceptuelles sur les espaces de travail et les visualisations.

La figure suivante présente un mappage de dépendance dont les noeuds représentent les espaces de travail, les rapports, les options de menu et les calques de globe définis dans le profil. Cette option ne fonctionne que si l’option d’affichage [!DNL Query Model] est activée.

>[!NOTE]
>
>Si l’option d’affichage [!DNL Query Model] n’est pas activée lorsque vous choisissez l’option d’affichage [!DNL Workspaces and Visualizations], un message d’erreur s’affiche.

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* Un noeud gris représente un espace de travail ou un rapport.
* Un noeud jaune-vert représente une option de menu.
* Un noeud rouge représente un espace de travail, un rapport, une option de menu ou une couche globe avec une dépendance brisée ou circulaire ou une autre erreur.

>[!NOTE]
>
>Étant donné que la carte des dépendances est conçue pour s’adapter aux dépendances acycliques, les noeuds impliqués dans les dépendances circulaires peuvent ne pas s’afficher correctement sur la carte. Vous pouvez rechercher des dépendances circulaires en saisissant &quot;dépendance circulaire&quot; dans la zone de texte [!DNL Search]. Pour plus d’informations sur la fonction [!DNL Search], voir [Recherche dans une carte](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

Pour obtenir des descriptions des autres noeuds sur la carte, voir [Composants de modèle de requête](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).
