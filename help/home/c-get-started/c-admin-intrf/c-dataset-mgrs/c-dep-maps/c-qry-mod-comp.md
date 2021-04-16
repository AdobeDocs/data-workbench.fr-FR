---
description: Informations conceptuelles sur les composants du modèle de requête.
title: Composants du modèle de requête
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
exl-id: 1f5d0a3a-6647-4762-ab20-9d80e467d48f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 3%

---

# Composants du modèle de requête{#query-model-components}

Informations conceptuelles sur les composants du modèle de requête.

La figure suivante présente un mappage de dépendances dont les noeuds représentent les mesures, les dimensions dérivées et les filtres d’un modèle de requête définis dans les dossiers Dimensions, Mesures et Filtres du profil, ainsi que les dimensions étendues définies dans le jeu de données qui y sont liées d’une manière ou d’une autre.

![](assets/vis_DependencyMap_QueryModel.png)

* Un noeud jaune-vert représente un filtre.
* Un noeud violet représente une mesure.
* Un noeud bleu-vert représente une dimension dérivée.
* Un noeud vert représente une dimension étendue (définie dans le jeu de données).
* Un noeud rouge représente une mesure, une dimension dérivée ou un filtre avec une dépendance brisée ou circulaire ou une autre erreur.

>[!NOTE]
>
>Comme la carte des dépendances est conçue pour s&#39;adapter aux dépendances acycliques, les noeuds impliqués dans les dépendances circulaires peuvent ne pas s&#39;afficher correctement sur la carte. Vous pouvez rechercher des dépendances circulaires en saisissant &quot;dépendance circulaire&quot; dans la zone de texte [!DNL Search]. Pour plus d&#39;informations sur la fonction [!DNL Search], consultez la section [Recherche dans une carte](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).
