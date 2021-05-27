---
description: Informations conceptuelles sur les composants du modèle de requête.
title: Composants du modèle de requête
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
exl-id: 1f5d0a3a-6647-4762-ab20-9d80e467d48f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 3%

---

# Composants du modèle de requête{#query-model-components}

Informations conceptuelles sur les composants du modèle de requête.

La figure suivante présente une carte de dépendance dont les noeuds représentent les mesures, dimensions dérivées et filtres d’un modèle de requête définis dans les dossiers Dimensions, Mesures et Filtres du profil, ainsi que les dimensions étendues définies dans le jeu de données qui y sont liées d’une manière ou d’une autre.

![](assets/vis_DependencyMap_QueryModel.png)

* Un noeud jaune-vert représente un filtre.
* Un noeud violet représente une mesure.
* Un noeud bleu-vert représente une dimension dérivée.
* Un noeud vert représente une dimension étendue (définie dans le jeu de données).
* Un noeud rouge représente une mesure, une dimension dérivée ou un filtre avec une dépendance brisée ou circulaire ou une autre erreur.

>[!NOTE]
>
>Étant donné que la carte des dépendances est conçue pour s’adapter aux dépendances acycliques, les noeuds impliqués dans les dépendances circulaires peuvent ne pas s’afficher correctement sur la carte. Vous pouvez rechercher des dépendances circulaires en saisissant &quot;dépendance circulaire&quot; dans la zone de texte [!DNL Search]. Pour plus d’informations sur la fonction [!DNL Search], voir [Recherche dans une carte](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).
