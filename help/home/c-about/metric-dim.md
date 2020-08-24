---
description: Créez des Dimensions définies par des attributs de mesure (Dimensions de mesure) à l’aide d’un assistant pas à pas. Ensuite, testez, prévisualisation et enregistrez le nouveau paramètre Limite de mesure dans votre liste de Dimensions.
title: Assistant dimension de mesure
uuid: 411b2e28-0958-43bb-a853-7de7b3063818
translation-type: tm+mt
source-git-commit: 35e6e9280ab36e8b39e89039b791199d1de54e03
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 2%

---


# Assistant dimension de mesure{#metric-dim-wizard}

Créez des Dimensions définies par des attributs de mesure (Dimensions de mesure) à l’aide d’un assistant pas à pas. Ensuite, testez, prévisualisation et enregistrez le nouveau paramètre Limite de mesure dans votre liste de Dimensions.

Un Dim de mesure convertit une mesure en une nouvelle dimension. Par exemple, un Dim de mesure basé sur une mesure de Vues de page et de niveau de Visiteur affiche les éléments de dimension en fonction du total des Vues de page pour chaque Visiteur. Il vous permet d’étendre une mesure actuellement définie en fonction d’éléments de dimension afin de créer et d’enregistrer en tant que nouvelle dimension.

## Step 1: Select Dimension and Metric {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. Ouvrez l’assistant Dim de mesure.

   Dans un espace de travail, cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Tools]** > **[!UICONTROL Create Metric Dim]**.

1. Nommez la mesure Dim.

   Par défaut, le champ Nom est renseigné automatiquement en fonction des sélections Niveau et Mesure.

1. Sélectionnez un niveau de Dimension.

   Le niveau de dimension est la dimension parente contenant toutes les valeurs d’élément constitutif pour filtrer l’entrée et définir un type de dimension.

   Les niveaux de Dimension sont les suivants :

   * Clics publicitaires
   * Accès
   * Product
   * Visite
   * Visiteur

1. Sélectionnez une mesure.

   Sélectionnez une mesure prédéfinie à étendre et enregistrer sous forme de mesure dim.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (Facultatif) Créez une formule de mesure.

   Cliquez sur la zone pour entrer une formule de mesure personnalisée. La valeur de Prévisualisation calculée s&#39;affiche pour valider l&#39;expression.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Vous pouvez ajouter votre propre expression [de](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) mesure ou couper-coller à partir d’un autre éditeur de mesures ou d’une autre visualisation. Des erreurs de syntaxe, des erreurs de formule, des filtres non définis et d’autres erreurs sont signalées dans l’assistant.

1. Cliquez sur **[!UICONTROL Next]**.

## Étape 2 : Mise en forme et définition des intervalles {#section-5bddf3cd306545d7806a501637f80f77}

1. Sélectionnez un format pour la nouvelle mesure dim.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   Le format définit comment la mesure sera présentée lorsqu’elle sera ouverte dans une visualisation. Ces formats sont des normes [](http://www.cplusplus.com/reference/cstdio/printf/)printf sélectionnées, définies ci-dessous :

   ```
   %[flags][width][.precision][length][specifier]
   % 0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   Dans le **[!UICONTROL Preview]** champ, une valeur s’affiche en fonction de la mesure et du format sélectionnés.

1. expression Ajouter le nombre d&#39;intervalles.

   Vous pouvez définir une mesure dim avec différentes plages ou intervalles. Cette opération renvoie des sous-ensembles d’éléments basés sur la taille, tels que [0-4], [5-10],...). Les éléments du niveau de Dimension se rapportent aux éléments dont la plage contient la valeur de la mesure. Consultez la description de l’expression du compartiment dans [Syntaxe pour les Expressions](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html)de Dimension.

1. Cliquez sur **[!UICONTROL Preview]** pour ouvrir la table des valeurs Dim de mesure avant d’enregistrer.

   ![](assets/6_4_workstation_metricdim_preview.png)

   Le tableau détaille les valeurs des mesures par dim de mesure.

1. Cliquez sur **[!UICONTROL Show in Dimension Menu]** pour ajouter la nouvelle dimension à l&#39;onglet **Dimension** dans le **Finder**.

1. Cliquez sur **[!UICONTROL Next]**.

## Étape 3 : Terminer et enregistrer {#section-d9043235b18a425f9de0db668d4b1683}

1. Sélectionnez cette option pour lancer l’éditeur de mesures, la visualisation graphique ou le tableau après l’enregistrement.

   | Champ | Description |
   |---|---|
   | **[!UICONTROL Launch Metric Dim Editor]** | Ouvrez l’éditeur de mesures. |
   | **[!UICONTROL Launch Graph]** | Lancez un graphique PNG du tableau. |
   | **[!UICONTROL Launch Table]** | Lancez un tableau dans l’espace de travail avec des valeurs dans des colonnes répertoriant les valeurs de la nouvelle mesure dim par rapport aux valeurs de la mesure sélectionnée. |

1. Cliquez sur **[!UICONTROL Finish]** et enregistrez.

   Une boîte de dialogue d&#39;enregistrement s&#39;ouvre et vous permet d&#39;enregistrer le fichier. Les options sélectionnées pour les valeurs de vue s&#39;ouvrent dans l&#39;espace de travail.

