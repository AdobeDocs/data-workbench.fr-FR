---
description: Informations conceptuelles sur les espaces de travail et les visualisations.
solution: Analytics
title: Espaces de travail et visualisations
topic: Data workbench
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Espaces de travail et visualisations{#workspaces-and-visualizations}

Informations conceptuelles sur les espaces de travail et les visualisations.

La figure suivante présente un mappage de dépendances dont les noeuds représentent les espaces de travail, les rapports, les options de menu et les calques globe définis dans le profil. Cette option fonctionne uniquement si l’option [!DNL Query Model] d’affichage est activée.

>[!NOTE]
>
>Si l’option [!DNL Query Model] d’affichage n’est pas activée lorsque vous sélectionnez l’option [!DNL Workspaces and Visualizations] d’affichage, un message d’erreur s’affiche.

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* Un noeud gris représente un espace de travail ou un rapport.
* Un noeud jaune-vert représente une option de menu.
* Un noeud rouge représente un espace de travail, un rapport, une option de menu ou un calque globe avec une dépendance rompue ou circulaire ou une autre erreur.

>[!NOTE]
>
>Etant donné que la carte des dépendances est conçue pour s’adapter aux dépendances acycliques, les noeuds impliqués dans les dépendances circulaires peuvent ne pas s’afficher correctement sur la carte. Vous pouvez rechercher des dépendances circulaires en saisissant &quot;dépendance circulaire&quot; dans la zone de [!DNL Search] texte. Pour plus d’informations sur la [!DNL Search] fonctionnalité, voir [Recherche dans une carte](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

Pour obtenir la description des autres noeuds de la carte, voir Composants [de modèle de](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f)requête.
