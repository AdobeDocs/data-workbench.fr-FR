---
description: Suivez ces étapes pour utiliser la visualisation du score de propension .
title: Configuration d’un score de propension
uuid: afc9aada-3bf9-4ce6-8c43-a955771065b4
exl-id: e16a7062-636e-44a9-a07d-343d48bf1b4c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# Configuration d’un score de propension{#setting-up-propensity-scoring}

{{eol}}

Suivez ces étapes pour utiliser la visualisation du score de propension .

1. Ouvrez un nouvel espace de travail et cliquez sur **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

   ![](assets/propensity_visualization.png)

1. Définissez la variable **[!UICONTROL Target]** (la variable dépendante).

   Définissez la variable dépendante en sélectionnant :

* **Eléments de Dimension**: Cliquez avec le bouton droit dans l’espace de travail et sélectionnez **[!UICONTROL Table]**. Sélectionnez ensuite un élément de Dimension comme variable dépendante.

   OR

* **[!UICONTROL Filter Editor]**. Cliquez sur **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Filter Editor]** pour ouvrir la visualisation de l’éditeur de filtres.

   ![](assets/propensity_visualization_filter_editor.png)

   Après avoir sélectionné un élément de Dimension ou Filtrer comme variable dépendante, cliquez sur **[!UICONTROL Set Target]**, saisissez un nom pour décrire la variable dépendante. Cliquez ensuite sur **[!UICONTROL OK]** (et assurez-vous que la zone de filtre est mise en surbrillance) pour définir Target.

   ![](assets/propensity_visualization_setTarget.png)

   Le nom donné à la cible est la variable dépendante qui apparaîtra dans le volet de gauche.
1. Ajoutez des variables indépendantes.

   Ajoutez les variables indépendantes à l’aide des mesures ou des éléments de Dimension.

   ![](assets/propensity_visualization_metrics.png)

* **Mesures**. Dans la barre d’outils Score de propension , sélectionnez une mesure dans le **[!UICONTROL Metrics]** .

* **Eléments de Dimension**: Cliquez avec le bouton droit dans l’espace de travail et sélectionnez **[!UICONTROL Table]**. Sélectionnez un ou plusieurs éléments de Dimension et faites-les glisser sur la colonne de gauche sous **[!UICONTROL Independent Variables]** ou au **[!UICONTROL Element]** à l’aide de la `<Ctrl>` + `<Alt>` clés.

1. Définir **[!UICONTROL Training Filter]**. Vous pouvez définir l’ensemble des visiteurs que vous souhaitez noter en cliquant sur **[!UICONTROL Options]** > **[!UICONTROL Set Training Filter]** dans la barre d’outils Score de propension . Vous obtiendrez ainsi un sous-ensemble de données créé à l’aide uniquement des visiteurs que vous souhaitez noter. Par exemple, qui a consulté le mois dernier, les visiteurs qui résident en Australie ou ceux qui ont consulté des produits spécifiques.

   Le filtre par défaut est **[!UICONTROL Train on Everyone]**, mais vous pouvez la modifier en activant **[!UICONTROL Dimension Elements]** dans un tableau ou en créant un filtre à l’aide de la fonction **[!UICONTROL Filter Editor]**.

   Après avoir sélectionné un élément de Dimension ou créé un filtre, cliquez sur **Options** > **Définir le filtre d’entraînement**, saisissez un nom pour décrire le filtre, puis cliquez sur **[!UICONTROL OK]**.
1. Une fois que vous avez identifié toutes vos entrées, appuyez sur **[!UICONTROL Go]**.

   ![](assets/propensity_visualization_GO.png)

   Le processus de notation commencera par transmettre les données plusieurs fois. Les résultats s’affichent alors sous forme de graphique à barres sur une ligne de pourcentage.
1. Enregistrez le score de propension.

   À partir de la version 6.1, vous disposez désormais d’une option lors de l’utilisation de l’option Enregistrer le score de propension :

* Dimension
* Dimension et mesure

   Vous pouvez obtenir deux fichiers enregistrés, à la fois une dimension et une mesure définie.

   >[!NOTE]
   >
   >Si vous envoyez le score de propension pour le traitement, vous obtiendrez une dimension uniquement.

   La mesure dérivée est la mesure de score moyen associée.
1. Vérifiez la précision.

   Le système affiche **[!UICONTROL Model Complete]** et générer un modèle de notation une fois le processus terminé.

   Clic droit sur **[!UICONTROL Model Complete]** identifie la précision du modèle de notation tel que défini par le système. Les valeurs comprises entre 0 % et 100 % identifieront la probabilité que les visiteurs correspondent à la variable **[!UICONTROL Target]** .

   La matrice de confusion donne quatre chiffres en fonction de la combinaison de l’option Réel positif (AP), Négatif réel (AN), Positif prédit (PP) et Négatif prédit (PN). Ces chiffres sont obtenus en appliquant le modèle de notation obtenu aux données de test ignorées de 20 % dont nous connaissons la vraie réponse. Si le score est supérieur à 50 %, il est prédit en tant que cas positif (correspondance à l’événement défini).

   ![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"><b> Précision</b> </td> 
   <td colname="col2"> Indique la précision du modèle en identifiant les prédictions correctes par rapport à toutes les prédictions. <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Rappeler</b> </td> 
   <td colname="col2"> Identifie la possibilité de réidentifier le modèle de notation. <p><b>TP / (TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Précision</b> </td> 
   <td colname="col2">Identifie le niveau d’incohérence. <p>TP / (TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Ouvrez une [Graphique de l’effet élévateur ou du gain](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a), ou la variable [Visionneuse de modèles](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-9f2593a8218140b7bd132a4c74e159f9).

   Cliquez avec le bouton droit de la souris sur le **Fin du modèle** visualisation et sélection **[!UICONTROL Lift Chart]**, **[!UICONTROL Gain Chart]** ou **[!UICONTROL Model Viewer.]**
