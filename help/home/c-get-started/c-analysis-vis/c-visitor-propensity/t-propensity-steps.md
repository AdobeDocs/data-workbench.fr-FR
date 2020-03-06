---
description: Pour utiliser la visualisation du score de propension, procédez comme suit.
solution: Analytics
title: Configuration du score de propension
topic: Data workbench
uuid: afc9aada-3bf9-4ce6-8c43-a955771065b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration du score de propension{#setting-up-propensity-scoring}

Pour utiliser la visualisation du score de propension, procédez comme suit.

1. Ouvrez un nouvel espace de travail et cliquez sur **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

   ![](assets/propensity_visualization.png)

1. Définissez la **[!UICONTROL Target]** (variable dépendante).

   Définissez la variable dépendante en sélectionnant :

* **Eléments** de dimension : Cliquez avec le bouton droit de la souris dans l’espace de travail et sélectionnez **[!UICONTROL Table]**. Sélectionnez ensuite des éléments de dimension comme variable dépendante.

   OU

* **[!UICONTROL Filter Editor]**. Cliquez sur **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Filter Editor]** pour ouvrir la visualisation de l’éditeur de filtres.

   ![](assets/propensity_visualization_filter_editor.png)

   Après avoir sélectionné un élément de dimension ou un filtre comme variable dépendante, cliquez sur **[!UICONTROL Set Target]**, saisissez un nom pour décrire la variable dépendante. Cliquez ensuite sur **[!UICONTROL OK]** (et assurez-vous que la zone de filtre est en surbrillance) pour définir Target.

   ![](assets/propensity_visualization_setTarget.png)

   Le nom que vous donnez à la cible est la variable dépendante qui apparaîtra dans le volet de gauche.
1. Ajoutez des variables indépendantes.

   Ajoutez les variables indépendantes à l’aide des mesures ou des éléments de dimension.

   ![](assets/propensity_visualization_metrics.png)

* **Mesures**. Dans la barre d’outils Score de propension, sélectionnez une mesure dans le **[!UICONTROL Metrics]** menu.

* **Eléments** de dimension : Cliquez avec le bouton droit de la souris dans l’espace de travail et sélectionnez **[!UICONTROL Table]**. Sélectionnez un ou plusieurs éléments de dimension et faites-les glisser vers la colonne de gauche sous **[!UICONTROL Independent Variables]** ou vers la **[!UICONTROL Element]** zone à l’aide des touches `<Ctrl>` + `<Alt>` .

1. Définir **[!UICONTROL Training Filter]**. Vous pouvez définir l’ensemble de visiteurs que vous souhaitez marquer en cliquant sur **[!UICONTROL Options]** > **[!UICONTROL Set Training Filter]** dans la barre d’outils Score de propension. Vous obtiendrez ainsi un sous-ensemble de données créées à l’aide uniquement des visiteurs que vous souhaitez marquer. Par exemple, les visiteurs qui ont visité le mois dernier, les visiteurs qui résident en Australie ou les visiteurs qui ont consulté des produits spécifiques.

   Le filtre par défaut est **[!UICONTROL Train on Everyone]**, mais vous pouvez le modifier en l’activant **[!UICONTROL Dimension Elements]** dans un tableau ou en créant un filtre à l’aide du **[!UICONTROL Filter Editor]**.

   Après avoir sélectionné un élément de dimension ou créé un filtre et activé, cliquez sur **Options** > **Définir le filtre** de formation, attribuez un nom au filtre, puis cliquez sur **[!UICONTROL OK]** Options.
1. Une fois que vous avez identifié toutes vos entrées, appuyez sur **[!UICONTROL Go]**.

   ![](assets/propensity_visualization_GO.png)

   Le processus de notation commence par la transmission des données à plusieurs reprises. Les résultats s’afficheront alors sous forme de graphiques à barres sur une ligne de pourcentage.
1. Enregistrer le score de propension.

   À partir de la version 6.1, vous disposez désormais d’une option lors de l’utilisation de la fonction Enregistrer la score de propension :

* Dimension
* Dimension et mesure

   Vous pouvez obtenir deux fichiers enregistrés, une dimension et une mesure définies.

   >[!NOTE]
   >
   >Si vous envoyez le score de propension pour traitement, vous obtiendrez une dimension uniquement.

   La mesure dérivée est la mesure de score moyen associée.
1. Vérifiez la précision.

   Le système affiche **[!UICONTROL Model Complete]** et génère un modèle de notation une fois le processus terminé.

   Un clic droit sur **[!UICONTROL Model Complete]** permet d&#39;identifier la précision du modèle de notation tel que défini par le système. Les valeurs comprises entre 0 % et 100 % identifieront la probabilité que les visiteurs correspondent à la **[!UICONTROL Target]** variable.

   La matrice de confusion donne quatre valeurs en fonction de la combinaison des valeurs Positif réel (AP), Négatif réel (AN), Positif prédit (PP) et Négatif prédit (PN). Ces chiffres sont obtenus en appliquant le modèle de notation obtenu aux données de test de 20 % refusées dont nous connaissons la réponse exacte. Si le score est supérieur à 50 %, il est prédit comme un cas positif (correspondant à l’événement défini).

   ![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"><b> Précision</b> </td> 
   <td colname="col2"> Indique la précision du modèle en identifiant les prédictions correctes par rapport à toutes les prédictions. <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Rappel</b> </td> 
   <td colname="col2"> Identifie la capacité de réidentifier le modèle de notation. <p><b>TP / (TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Précision</b> </td> 
   <td colname="col2">Identifie le niveau d’incohérence. <p>TP / (TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Ouvrez un [effet élévateur ou un diagramme](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a)de gain ou la visionneuse de [modèles](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-9f2593a8218140b7bd132a4c74e159f9).

   Cliquez avec le bouton droit sur la visualisation **Modèle complet** et sélectionnez **[!UICONTROL Lift Chart]**, **[!UICONTROL Gain Chart]** ou **[!UICONTROL Model Viewer.]**
