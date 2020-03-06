---
description: Utilisez l’assistant d’ajustement de mesure pour créer une nouvelle dimension de mesure.
title: Assistant Limite de mesure
uuid: 77b9bc8e-7625-4fef-9de4-f113f9b2debd
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Assistant Limite de mesure{#metric-dim-wizard}

Utilisez l’assistant d’ajustement de mesure pour créer une nouvelle dimension de mesure.

Un point de mesure convertit une mesure en une nouvelle dimension. Par exemple, un rapport de mesure basé sur une mesure Pages vues et le niveau du visiteur affiche des éléments de dimension en fonction du nombre total de pages vues pour chaque visiteur. Il vous permet d’étendre une mesure actuellement définie en fonction des éléments de dimension afin de créer et d’enregistrer une nouvelle dimension.

## Étape 1 : sélectionner une dimension et une mesure {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. **Ouvrez l’assistant** d’ajustement des mesures.

   Dans un espace de travail, cliquez avec le bouton droit de la souris et sélectionnez **Outils** > **Créer un paramètre de mesure**.

1. **Attribuez un nom au paramètre** de mesure.

   Par défaut, le champ Nom est renseigné automatiquement en fonction des sélections Niveau et Mesure.

1. **Sélectionnez un niveau de dimension.** Le niveau de dimension est la dimension parente contenant toutes les valeurs d’élément constitutif pour filtrer l’entrée et définir un type de dimension.

   Les niveaux de dimension incluent :

   * Clics publicitaires
   * Accès
   * Product
   * Visite
   * Visiteur

1. **Sélectionnez une mesure**.

   Sélectionnez une mesure prédéfinie à étendre et à enregistrer en tant que mesure dim.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (Facultatif) **Créez une formule** de mesure.

   Cliquez sur la zone pour entrer une formule de mesure personnalisée. La valeur d’aperçu calculée s’affiche pour valider l’expression.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Vous pouvez ajouter votre propre expression [de](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) mesure ou couper-coller à partir d’un autre éditeur de mesure ou d’une autre visualisation. Des erreurs de syntaxe, des erreurs de formule, des filtres non définis et d’autres erreurs sont signalées dans l’assistant.

1. Cliquez sur **Suivant**.

## Étape 2 : format et définir des intervalles {#section-5bddf3cd306545d7806a501637f80f77}

Vous pouvez sélectionner le format de mesure et définir les valeurs du compartiment pour une expression de dimension.

1. Sélectionnez un **format** pour la nouvelle mesure dim.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   Le format définit le mode de présentation de la mesure lorsqu’elle est ouverte dans une visualisation. Ces formats sont sélectionnés selon des normes [](http://www.cplusplus.com/reference/cstdio/printf/)d’impression, définies ci-dessous :

   ```
   %[flags][width][.precision][length][specifier]
   %
   0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   Dans le champ **Aperçu** , une valeur s’affiche en fonction de la mesure et du format sélectionnés.

1. Ajouter une expression **Bucket Count** .

   Vous pouvez définir une mesure dim avec différentes plages ou intervalles. Cette opération renvoie des sous-ensembles d’éléments en fonction de la taille ( [0-4], [5-10], etc.). Les éléments du niveau de dimension se rapportent aux éléments dont la plage contient la valeur de mesure. Voir la description de l’expression de compartiment dans [Syntaxe pour les expressions](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html)de dimension.

1. Cliquez sur **Prévisualiser** pour ouvrir la table des valeurs de l’intervalle de mesures avant d’enregistrer.

   ![](assets/6_4_workstation_metricdim_preview.png)

   Le tableau détaille les valeurs de mesure par dim de mesure.

1. Cliquez sur **Afficher dans le menu** Dimension pour ajouter la nouvelle dimension à l’onglet **Dimension** dans le **Finder**.
1. Cliquez sur **Suivant**.

## Étape 3 : terminer et enregistrer {#section-d9043235b18a425f9de0db668d4b1683}

1. Sélectionnez cette option pour lancer l’éditeur de date de mesure, la visualisation graphique ou le tableau après l’enregistrement.

   | Champ | Description |
   |---|---|
   | Lancement de l’éditeur de date des mesures | Ouvrez l’éditeur de date des mesures. |
   | Lancer graphique | Lancez un graphique PNG du tableau. |
   | Lancer le tableau | Lancez un tableau dans l’espace de travail avec des valeurs dans des colonnes répertoriant les valeurs de la nouvelle mesure dim par rapport aux valeurs de la mesure sélectionnée. |

1. Cliquez sur **Terminer** et enregistrez.

   Une boîte de dialogue d&#39;enregistrement s&#39;ouvre et vous permet d&#39;enregistrer le fichier. Les options sélectionnées pour afficher les valeurs s’ouvrent dans l’espace de travail.

