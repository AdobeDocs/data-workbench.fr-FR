---
description: Informations conceptuelles sur les composants du modèle de requête.
solution: Analytics
title: Composants du modèle de requête
topic: Data workbench
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Composants du modèle de requête{#query-model-components}

Informations conceptuelles sur les composants du modèle de requête.

La figure suivante présente un mappage de dépendances dont les noeuds représentent les mesures, dimensions dérivées et filtres d’un modèle de requête définis dans les dossiers Dimensions, Mesures et Filtres du profil, ainsi que les dimensions étendues définies dans le jeu de données qui y sont liées d’une certaine manière.

![](assets/vis_DependencyMap_QueryModel.png)

* Un noeud jaune-vert représente un filtre.
* Un noeud violet représente une mesure.
* Un noeud bleu-vert représente une dimension dérivée.
* Un noeud vert représente une dimension étendue (définie dans le jeu de données).
* Un noeud rouge représente une mesure, une dimension dérivée ou un filtre avec une dépendance brisée ou circulaire ou une autre erreur.

>[!NOTE]
>
>Etant donné que la carte des dépendances est conçue pour s’adapter aux dépendances acycliques, les noeuds impliqués dans les dépendances circulaires peuvent ne pas s’afficher correctement sur la carte. Vous pouvez rechercher des dépendances circulaires en saisissant &quot;dépendance circulaire&quot; dans la zone de [!DNL Search] texte. Pour plus d’informations sur la [!DNL Search] fonctionnalité, voir [Recherche dans une carte](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

