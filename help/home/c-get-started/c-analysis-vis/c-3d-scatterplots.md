---
description: Un graphique de dispersion 3D montre les éléments d’une dimension de données (tels que Jours ou Site de référence) sur une grille tridimensionnelle où les axes x, y et z représentent différentes mesures.
solution: Analytics
title: Graphiques de dispersion 3D
topic: Data workbench
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Graphiques de dispersion 3D{#d-scatter-plots}

Un graphique de dispersion 3D montre les éléments d’une dimension de données (tels que Jours ou Site de référence) sur une grille tridimensionnelle où les axes x, y et z représentent différentes mesures.

À l’instar du graphique de [dispersion 2D](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Scatter_Plots), cette visualisation est utile pour comprendre la relation entre un grand nombre d’éléments disparates utilisant différentes mesures.

**Pour utiliser la visualisation en graphique de dispersion 3D :**

1. Ouvrez un nouvel espace de travail.

   Après avoir ouvert un nouvel espace de travail, vous devrez peut-être cliquer sur **Ajouter** > Déverrouiller **** temporairement.
1. Cliquez avec le bouton droit de la souris et sélectionnez **Visualisation** > Graphique de dispersion **3D**.

   Une liste de menus **[!UICONTROL Dimensions]** s&#39;ouvre.

1. Sélectionnez une dimension pour la requête.

   Le graphique de dispersion 3D ouvre les mesures par défaut pour cette dimension.

   ![](assets/3D_main.png)

   La sélection du **[!UICONTROL Days]** menu affiche le graphique de dispersion 3D suivant avec ces mesures par défaut sur les axes suivants : **[!UICONTROL x=Visits]**, **[!UICONTROL y=Retention]** et **[!UICONTROL z=Visits]**.

1. Modifier les mesures. Cliquez avec le bouton droit de la souris sur l’étiquette de la mesure dans les axes x, y ou z et sélectionnez **[!UICONTROL Change Metric]**. Sélectionnez ensuite une autre mesure pour l’axe sélectionné.

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * Faites glisser une mesure sur l’une des étiquettes des trois axes et déposez-la pour changer l’axe sélectionné en mesure de dépôt.
   >    * Faites glisser une mesure n’importe où sur la visualisation et déposez-la pour modifier la mesure de rayon de cet axe.
   >    * Faites glisser une dimension n’importe où sur la visualisation et déposez-la pour la modifier.


1. Modifiez la mesure du rayon. Cliquez avec le bouton droit sur le titre en haut de la page (intitulé après la dimension sélectionnée) et sélectionnez **[!UICONTROL Change Radius Metric]**.

   La mesure de rayon définit la taille du point tracé en fonction de la sélection de mesures. La position relative des points ne change pas dans le graphique de dispersion, mais les tailles de points tracés dans la visualisation augmentent en fonction de la valeur de la mesure.

   ![](assets/3D_change_radius.png)

1. Employez le **[!UICONTROL Orthographic Camera]**. Cette option vous permet d’identifier les points tracés par rapport à leur perspective réelle en fonction de la mesure de rayon afin d’éviter une distorsion tridimensionnelle.

   Lorsque le graphique de dispersion 3D apparaît pour la première fois, il s’affiche dans une projection tournante tridimensionnelle, ce qui entraîne une certaine distorsion pour les points tracés plus près de la perspective, ou &quot;caméra&quot; virtuelle. (Les tracés plus proches de la caméra sont beaucoup plus grands que les points tournant plus loin de la caméra.)

   Pour éviter cette distorsion de perspective, vous pouvez sélectionner l’ **[!UICONTROL Orthographic Camera]** option en cliquant avec le bouton droit sur le titre et en le sélectionnant dans le menu. Vous pouvez ainsi représenter les objets tridimensionnels en deux dimensions. Les points mappés sont alors affichés sur un plan plat et les points sont affichés par rapport à la mesure de rayon, ce qui réduit les décalages tridimensionnels.

1. Sélectionnez des points dans le graphique de dispersion.

   * **Pour supprimer un point ou un groupe de points**: Cliquez sur le point.
   * **Pour ajouter un autre point ou groupe de points à votre sélection**: **Ctrl** + **clic sur** un point ou **Ctrl** + **glisser sur plusieurs points.**

   * **Pour supprimer un point ou un groupe de points de votre sélection**: **Maj** + **clic sur** un point ou **Maj** **+  faire glisser sur plusieurs points.******

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->

