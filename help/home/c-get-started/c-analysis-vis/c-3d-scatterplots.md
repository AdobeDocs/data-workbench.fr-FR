---
description: Un graphique de dispersion 3D représente les éléments d’une dimension de données (tels que Jours ou Site référent) sur une grille tridimensionnelle où les axes x, y et z représentent différentes mesures.
title: Graphiques de dispersion 3D
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
exl-id: 18f18cab-a31b-4ffe-89c5-412a5645af2e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 1%

---

# Graphiques de dispersion 3D{#d-scatter-plots}

Un graphique de dispersion 3D représente les éléments d’une dimension de données (tels que Jours ou Site référent) sur une grille tridimensionnelle où les axes x, y et z représentent différentes mesures.

Comme le graphique de dispersion [2D](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Scatter_Plots), cette visualisation est utile pour essayer de comprendre la relation entre un grand nombre d’éléments disparates utilisant différentes mesures.

**Pour utiliser la visualisation en graphique de dispersion 3D :**

1. Ouvrez un nouvel espace de travail.

   Après avoir ouvert un nouvel espace de travail, vous devrez peut-être cliquer sur **Ajouter** > **Déverrouiller temporairement**.
1. Cliquez avec le bouton droit et sélectionnez **Visualisation** > **Graphique de dispersion 3D**.

   Un menu répertoriant **[!UICONTROL Dimensions]** s&#39;ouvre.

1. Sélectionnez une dimension pour la requête.

   Le graphique de dispersion 3D ouvre les mesures par défaut pour cette dimension.

   ![](assets/3D_main.png)

   La sélection du menu **[!UICONTROL Days]** affiche le graphique de dispersion 3D suivant avec ces mesures par défaut sur les axes suivants : **[!UICONTROL x=Visits]**, **[!UICONTROL y=Retention]** et **[!UICONTROL z=Visits]**.

1. Modifier les mesures. Cliquez avec le bouton droit de la souris sur l&#39;étiquette de la mesure dans les axes x, y ou z et sélectionnez **[!UICONTROL Change Metric]**. Sélectionnez ensuite une autre mesure pour l’axe sélectionné.

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * Faites glisser une mesure vers l’un des libellés des trois axes et déposez-la pour transformer l’axe sélectionné en mesure perdue.
   >    * Faites glisser une mesure n’importe où sur la visualisation et déposez-la pour modifier la mesure de rayon de cet axe.
   >    * Faites glisser une dimension n’importe où sur la visualisation et déposez-la pour la modifier.


1. Modifiez la mesure Rayon. Cliquez avec le bouton droit sur le titre en haut de la page (intitulé après la dimension sélectionnée) et sélectionnez **[!UICONTROL Change Radius Metric]**.

   La mesure de rayon définit la taille du point tracé en fonction de la sélection de mesures. La position relative des points ne change pas dans le graphique de dispersion, mais les tailles des points tracés dans la visualisation augmentent en fonction de la valeur de la mesure.

   ![](assets/3D_change_radius.png)

1. Utilisez le **[!UICONTROL Orthographic Camera]**. Cette option vous permet d’identifier les points tracés par rapport à leur perspective réelle en fonction de la mesure de rayon afin d’éviter une distorsion tridimensionnelle.

   Lorsque le graphique de dispersion 3D apparaît pour la première fois, il s’affiche dans une projection tournante tridimensionnelle, ce qui entraîne une certaine distorsion pour les points tracés plus près de la perspective, ou &quot;caméra&quot; virtuelle. (Les emplacements les plus proches de la caméra apparaissent beaucoup plus grands que les points tournant plus loin de la caméra.)

   Pour éviter cette distorsion de perspective, vous pouvez sélectionner l&#39;option **[!UICONTROL Orthographic Camera]** en cliquant avec le bouton droit sur le titre et en le sélectionnant dans le menu. Vous pouvez ainsi représenter les objets à trois dimensions en deux dimensions. Cette option rend les points tracés comme plats et les affiche comme points par rapport à la mesure de rayon, ce qui réduit les décalages tridimensionnels.

1. Sélectionnez des points dans le graphique de dispersion.

   * **Pour supprimer un point ou un groupe de points** : Cliquez sur le point.
   * **Pour ajouter un autre point ou un autre groupe de points à votre sélection** :  **Ctrl** +  **** clic sur un point ou  **Ctrl** +  **** glisse sur plusieurs points.

   * **Pour supprimer un point ou un groupe de points de votre sélection** :  **Maj** + **** clic sur un point ou  **Maj** **+** **** glisser sur plusieurs points.

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->
