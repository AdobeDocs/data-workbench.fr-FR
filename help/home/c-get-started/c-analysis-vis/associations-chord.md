---
description: La visualisation du corde d’association vous permet d’afficher la proportion et l’association entre les mesures, les dimensions et les éléments, en affichant des accords plus grands comme une indication d’une association plus forte.
title: Visualisation du corde d’association
uuid: c656ffc8-e45a-44c0-a29b-cdc10dcbd1f2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualisation du corde d’association{#association-chord-visualization}

La visualisation du corde d’association vous permet d’afficher la proportion et l’association entre les mesures, les dimensions et les éléments, en affichant des accords plus grands comme une indication d’une association plus forte.

Le tableau Associations compare les valeurs avec le calcul V de Cramer au lieu d&#39;utiliser le coefficient de corrélation de Pearson, tel qu&#39;il est utilisé dans les visualisations Matrice [de](/help/home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md) corrélation et Correspondance [](/help/home/c-get-started/c-analysis-vis/associations-visualization.md) (il ne peut comparer que les mesures, tandis que le tableau d&#39;association et le corde peuvent comparer les mesures, les dimensions et les éléments). Le Chord Associations fournit également une autre vue dans un tableau [d’](../../../home/c-get-started/c-analysis-vis/associations-visualization.md#concept-9d937dda38174875b32095c6eaf22f2f)associations créé précédemment.

**Pour créer un accord d’association**

1. Dans un espace de travail, cliquez avec le bouton droit de la souris sur **Visualisation > Analyses prédictives > Correspondance** d’association.

   Un menu s&#39;ouvre et vous permet de sélectionner une dimension étendue dans la liste.

   ![](assets/association_chord1.png)

   Une fois sélectionné, le tableau d’association vide s’ouvre avec la dimension sélectionnée identifiée dans le titre. ![](assets/association_chord2.png)

1. **Sélectionnez une mesure, une dimension ou un élément** de dimension.

   Cliquez avec le bouton droit de la souris sur la visualisation des accords et sélectionnez **Ajouter une mesure** ou **Ajouter une dimension**. Sélectionnez les éléments du menu à ajouter à l&#39;accord.

   Vous pouvez également faire glisser des mesures et des dimensions depuis la page **[!UICONTROL Finder]** en cliquant **[!UICONTROL Ctrl-Alt]** sur les mesures et dimensions et en les faisant glisser vers l’accord. Ou faites glisser les éléments de dimension directement d’un tableau ouvert vers la visualisation en corde.

1. **Choisissez d’autres mesures, dimensions et éléments à associer**.

   Une fois que plusieurs valeurs sont sélectionnées, le graphique est automatiquement actualisé et commence à afficher les données d’association. Continuez à ajouter des mesures si nécessaire pour associer des points de données.

   ![](assets/association_chord.png)

   La visualisation en corde affiche la proportion de l’ensemble représenté par la zone de chaque segment. Continuer à ajouter des mesures/dimensions/éléments en fonction des besoins pour identifier et étudier les relations importantes.

1. **Affichez la visualisation** de Cordes.

   Passez la souris sur chaque valeur de la visualisation pour afficher les relations.

1. **Modifier les paramètres.** Cliquez avec le bouton droit de la souris sur la visualisation des accords pour ouvrir un menu permettant de modifier la mesure, la dimension ou les éléments et d’afficher les dimensions sous forme de nombres absolus ou de pourcentages, de supprimer la mesure sélectionnée ou toutes les mesures, de modifier les couleurs et les détails et d’exporter les valeurs vers un tableau d’associations.

**Pour créer un accord d&#39;association à partir d&#39;une table d&#39;association :**

1. Ouvrez une visualisation Tableau **d’** association.
1. Cliquez avec le bouton droit de la souris et sélectionnez **Exporter la visualisation** des accords. Un diagramme de corde d’association s’ouvre avec les valeurs sélectionnées dans le tableau d’association. ![](assets/association_table_to_chord.png)

>[!IMPORTANT]
>
>L’exportation d’un tableau d’association à partir d’un diagramme d’accords d’association qui contient au moins une mesure entraîne la duplication des éléments dans les lignes/colonnes du tableau d’association. Pour éviter les éléments dupliqués, créez un tableau d’association et ajoutez les éléments souhaités au lieu d’exporter les éléments d’un diagramme d’association.

