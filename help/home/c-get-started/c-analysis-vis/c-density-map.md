---
description: La visualisation de la carte de densité affiche les éléments sous forme de rectangles ombragés dans une carte carrée.
solution: Analytics
title: Carte de densité
topic: Data workbench
uuid: c13cecee-f322-4757-aa90-12039173ff9f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Carte de densité{#density-map}

La visualisation de la carte de densité affiche les éléments sous forme de rectangles ombragés dans une carte carrée.

Les dimensions des rectangles dépendent des valeurs d’élément, où les valeurs les plus élevées sont représentées par des rectangles de plus grande taille. Tout comme un graphique circulaire, cette visualisation vous permet de voir rapidement quels éléments constituent le pourcentage le plus élevé de la dimension sélectionnée.

![](assets/density_map_day_visits.png)

Pour créer une carte de densité :

1. Ouvrez un nouvel espace de travail.

   Après avoir ouvert un nouvel espace de travail, vous devrez peut-être cliquer sur **Ajouter** > Déverrouiller **** temporairement.
1. Cliquez sur **[!UICONTROL Visualization]** > **[!UICONTROL Density Map]**.

1. Select a **[!UICONTROL Dimension]** from the menu.

   For example, select **[!UICONTROL Time]** > **[!UICONTROL Days]**.

   En revanche, si vous sélectionnez **[!UICONTROL Time]** > **[!UICONTROL Hours]** , vous obtiendrez davantage d’éléments avec des valeurs plus petites qui s’affichent sous la forme de rectangles plus petits.

   >[!NOTE]
   >
   >Vous souhaiterez sélectionner une dimension avec plusieurs éléments en fonction de vos besoins. La limite actuelle est de 200 des plus grands éléments pour chaque dimension.

1. Vous pouvez modifier les vues des dimensions en ouvrant **[!UICONTROL Visualization]** > **[!UICONTROL Table]** et en sélectionnant plusieurs éléments du tableau à afficher dans la carte.

   ![](assets/density_map_day_selections.png)

   La carte répond aux sélections du tableau.

1. Placez le pointeur de la souris sur de petits éléments pour afficher leur nom et leur valeur dans le texte qui s’affiche près du curseur de la souris.
1. Masquez les éléments en cliquant avec le bouton droit de la souris et en sélectionnant **[!UICONTROL Mask]**, puis choisissez une option.

   ![](assets/density_map_day_mask.png)

   Pour afficher tous les noeuds masqués, sélectionnez **[!UICONTROL Unhide All]**.

1. Mettez en évidence les éléments en cliquant avec le bouton droit de la souris et en sélectionnant **[!UICONTROL Spotlight]**, puis choisissez une option. L’effet de soulignement vous permet de mettre en surbrillance et d’atténuer les éléments d’une plage.
1. Ajoutez une légende de couleur à l’espace de travail. Vous pouvez identifier les valeurs de la carte à l’aide de la légende des couleurs.

   Vous pouvez ajouter une légende de couleur à l’espace de travail et les noeuds changeront de couleur en fonction de la dimension supplémentaire des données.
1. Modifiez la dimension ou la mesure en cliquant avec le bouton droit sur le titre du mappage et en le sélectionnant dans le menu.

   ![](assets/density_map_change_dim.png)

1. Ajoutez des légendes en cliquant avec le bouton droit sur une cellule et en sélectionnant **[!UICONTROL Add Callout]**. Vous pouvez sélectionner différents types ou visualisations dans le menu.

   ![](assets/density_map_callout.png)

1. Comme dans toutes les visualisations, vous pouvez cliquer avec le bouton droit au-dessus de la barre de titre pour afficher des commandes de base telles que Fermer, Enregistrer, Exporter vers Microsoft Excel, Commande, Copier, Réduire et Sans bordure afin d’afficher une visualisation sans bordure.

   ![](assets/density_map_export.png)

1. La carte de densité vous permet de sélectionner et de désélectionner plusieurs éléments similaires à d’autres visualisations :

* Cliquez avec le bouton gauche pour sélectionner un élément.
* Ctrl + clic pour sélectionner plusieurs éléments.
* Appuyez sur Maj et cliquez pour désélectionner un élément.
* Cliquez avec le bouton droit de la souris sur les éléments sélectionnés pour ouvrir un menu. Choisissez ensuite **[!UICONTROL Deselect]** ou **[!UICONTROL Deselect All]** pour effacer les éléments sélectionnés.

## Autres options {#section-d77defb012424de4a7ced8e5c93115bc}

Cliquez avec le bouton droit de la souris sur la carte de densité pour ouvrir un menu avec les options suivantes :

<table id="table_3ADA85031C834792BFD041E186962A41"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ajouter Légende </td> 
   <td colname="col2">Ajoutez un texte ou un graphique en tant que légende dans la visualisation pour identifier ou décrire davantage un élément. <p>Vous pouvez également sélectionner une légende de mesure vierge, un tableau, un graphique de ligne ou un graphique de dispersion en fonction de l’élément sélectionné dans la carte de densité. Vous pouvez ensuite ajouter des mesures et des dimensions à ces visualisations vierges, le cas échéant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Masque </td> 
   <td colname="col2">Les options de masquage vous permettent de masquer les éléments sélectionnés. Cliquez avec le bouton droit de la souris pour afficher les options Masque. <p><span class="uicontrol"> Masquer cet élément</span>(Masquer cet élément): choisissez cette option pour masquer un élément unique que vous avez sélectionné. </p> <p><span class="uicontrol"> Masquer la sélection</span>(Masquer la sélection): choisissez cette option pour masquer plusieurs éléments que vous avez sélectionnés. </p> <p><span class="uicontrol"> Afficher en haut</span>— Choisissez cette option pour afficher uniquement les 100, 50, 25 ou 10 principaux éléments en fonction des valeurs de la carte de densité. </p> <p><span class="uicontrol"> Afficher en bas</span>(Show Bottom): choisissez cette option pour afficher uniquement les 100, 50, 25 ou 10 éléments principaux en bas en fonction des valeurs de la carte de densité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> point phare </td> 
   <td colname="col2"> L’effet de soulignement vous permet de mettre en surbrillance et d’atténuer les éléments d’une plage. Cliquez avec le bouton droit de la souris pour ouvrir un menu d’options. <p><span class="uicontrol"> Afficher en haut</span>— Choisissez cette option pour mettre en surbrillance uniquement les 100, 50, 25 ou 10 principaux éléments en fonction des valeurs de la carte de densité. </p> <p><span class="uicontrol"> Afficher en bas</span>(Show Bottom): choisissez cette option pour mettre en surbrillance uniquement les 100, 50, 25 ou 10 éléments principaux inférieurs en fonction des valeurs de la carte de densité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Désélectionner </p> <p>Tout désélectionner </p> </td> 
   <td colname="col2"> <p> Sélectionnez ces commandes pour désélectionner l’élément actif, le cas échéant, ou désélectionnez tous les éléments sélectionnés. </p> </td> 
  </tr> 
 </tbody> 
</table>

