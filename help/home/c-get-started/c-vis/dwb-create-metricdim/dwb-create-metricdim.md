---
description: Utilisez l’assistant Dimension de mesure pour créer une Dimension de mesure.
title: Assistant dimension de mesure
uuid: 77b9bc8e-7625-4fef-9de4-f113f9b2debd
exl-id: 109fbefc-5608-493d-aec9-8337f21eaa70
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# Assistant dimension de mesure{#metric-dim-wizard}

{{eol}}

Utilisez l’assistant Dimension de mesure pour créer une Dimension de mesure.

Une dimension de mesure convertit une mesure en une nouvelle dimension. Par exemple, une dimension de mesure basée sur une mesure Pages vues et le niveau du visiteur affiche des éléments de dimension en fonction du nombre total de pages vues pour chaque visiteur. Il vous permet d’étendre une mesure actuellement définie en fonction d’éléments de dimension afin de créer et d’enregistrer en tant que nouvelle dimension.

## Étape 1 : sélectionner une dimension et une mesure ; {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. **Ouvrez l’assistant de dimension de mesure .**.

   Dans un espace de travail, cliquez avec le bouton droit de la souris et sélectionnez **Outils** > **Créer une dimension de mesure**.

1. **Nommer la dimension de mesure**.

   Par défaut, le champ Nom est automatiquement renseigné en fonction des sélections Niveau et Mesure .

1. **Sélectionnez un niveau de Dimension.** Le niveau de dimension est la dimension parente contenant toutes les valeurs d’élément constitutif pour filtrer l’entrée et définir un type de dimension.

   Les niveaux de Dimension incluent :

   * Clic publicitaire
   * Accès
   * Product
   * Visite
   * Visiteur

1. **Sélection d’une mesure**.

   Sélectionnez une mesure prédéfinie à étendre et à enregistrer en tant que mesure dim.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (facultatif) **Créer une formule de mesure**.

   Cliquez sur la case pour saisir une formule de mesure personnalisée. La valeur d’ aperçu calculée apparaîtra en validant l’expression.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Vous pouvez ajouter les vôtres [expression de mesure](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) ou couper et coller à partir d’un autre éditeur de mesures ou visualisation. Les erreurs de syntaxe, de formule, les filtres non définis et autres erreurs sont signalés dans l’assistant.

1. Cliquez sur **Suivant**.

## Étape 2 : format et définition de compartiments {#section-5bddf3cd306545d7806a501637f80f77}

Vous pouvez sélectionner le format de mesure et définir les valeurs de compartiment d’une expression de dimension.

1. Sélectionnez une **Format** pour la nouvelle mesure dim.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   Le format définit la manière dont la mesure sera présentée lorsqu’elle sera ouverte dans une visualisation. Ces formats sont sélectionnés [normes printf](https://www.cplusplus.com/reference/cstdio/printf/), défini ci-dessous :

   ```
   %[flags][width][.precision][length][specifier]
   %
   0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   Dans le **Aperçu** , une valeur s’affiche en fonction de la mesure et du format sélectionnés.

1. Ajouter **Comptage des compartiments** expression.

   Vous pouvez définir un diagramme de mesure avec différentes plages ou intervalles. Cette opération renvoie des sous-ensembles d’éléments en fonction de leur taille, tels que [0-4], [5-10],...). Les éléments du niveau de Dimension sont associés aux éléments dont la plage contient la valeur de la mesure. Voir la description de l’expression du compartiment à l’adresse [Syntaxe des expressions de Dimension](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html).

1. Cliquez sur **Aperçu** pour ouvrir le tableau des valeurs de dimension de mesure avant l’enregistrement.

   ![](assets/6_4_workstation_metricdim_preview.png)

   Le tableau présente les valeurs des mesures par dim de mesure.

1. Cliquez sur **Afficher dans le menu Dimension** pour ajouter la dimension nouvellement créée à l’événement **Dimension** dans le **Finder**.
1. Cliquez sur **Suivant**.

## Étape 3 : terminer et enregistrer {#section-d9043235b18a425f9de0db668d4b1683}

1. Sélectionnez cette option pour lancer l’éditeur de dimension de mesure, la visualisation graphique ou le tableau après l’enregistrement.

   | Champ | Description |
   |---|---|
   | Lancement de l’éditeur de dimension de mesure | Ouvrez l’éditeur de dimension de mesure. |
   | Graphique de lancement | Lancez un graphique PNG du tableau. |
   | Tableau de lancement | Lancez un tableau dans l’espace de travail avec des valeurs dans des colonnes répertoriant les valeurs de la nouvelle mesure dim par rapport aux valeurs de la mesure sélectionnée. |

1. Cliquez sur **Terminer** et enregistrez.

   Une boîte de dialogue d’enregistrement s’ouvre, vous permettant d’enregistrer le fichier. Les options sélectionnées pour afficher les valeurs s’ouvrent dans l’espace de travail.
