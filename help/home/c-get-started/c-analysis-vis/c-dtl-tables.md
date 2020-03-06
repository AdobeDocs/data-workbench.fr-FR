---
description: Les tableaux de détails vous permettent d’afficher des informations supplémentaires sur un sous-ensemble de données, défini par les sélections que vous effectuez dans d’autres visualisations.
solution: Analytics
title: Tableau des détails
topic: Data workbench
uuid: 2becff5e-c78d-4ac7-8cda-814ad0193efd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Detail table{#detail-table}

Les tableaux de détails vous permettent d’afficher des informations supplémentaires sur un sous-ensemble de données, défini par les sélections que vous effectuez dans d’autres visualisations.

Les informations supplémentaires que vous voyez sont un échantillon de toutes les données disponibles.

![](assets/vis_details.png)

Le tableau suivant décrit les éléments d’un tableau détaillé.

<table id="table_C88C7F7F5AEA4820B908923E45CC0A62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col02" class="entry"> Couleur </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Niveau </p> </td> 
   <td colname="col02"> <p>Rose </p> </td> 
   <td colname="col2"> <p>Toute dimension dénombrable pour laquelle vous souhaitez afficher des informations détaillées sur les attributs et les mesures. Le niveau est précédé par le nombre d’éléments affichés par rapport au nombre d’éléments disponibles ; par exemple, 6/444 indique que 6 éléments sont affichés sur 444 éléments possibles. Dans l’exemple ci-dessus, le niveau Visiteurs indique que tous les détails fournis sont basés sur le visiteur. Le niveau Pages vues indique que tous les détails fournis reposent sur la page vue. L’affichage simultané de plusieurs niveaux s’avère utile lorsque vous souhaitez analyser des données dont les parents sont différents. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribut </p> </td> 
   <td colname="col02"> <p>Vert </p> </td> 
   <td colname="col2"> <p>Toute dimension qui correspond à un-à-plusieurs ou à un-à-un avec le niveau, comme Ville vers Visiteurs. Chaque ligne affiche l’élément associé à chaque élément du niveau que vous avez sélectionné. Dans l’exemple ci-dessus, les attributs Domaine et Ville répertorient le domaine et la ville de chacun des exemples de visiteurs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mesure </p> </td> 
   <td colname="col02"> <p>Bleu </p> </td> 
   <td colname="col2"> <p>Détail de la mesure sur le niveau que vous avez sélectionné. Dans l’exemple ci-dessus, avec le niveau Visiteurs défini, la mesure Pages vues affiche le nombre de pages vues pour un visiteur individuel, tandis que le niveau Pages vues fournit des détails sur chacune de ces pages vues. </p> </td> 
  </tr> 
 </tbody> 
</table>

Supposons que vous travailliez avec les données du site Web et que vous souhaitiez savoir quelles pages les visiteurs de certaines villes et de domaines particuliers ont visitées au cours d’une période donnée.

Vous devez d’abord créer une visualisation qui affiche la période qui vous intéresse, puis sélectionner cette période. Vous pouvez désormais ajouter un tableau détaillé pour afficher les détails souhaités pour un échantillon de visiteurs dans le jeu de données.

Pour afficher les détails décrits ci-dessus, procédez comme suit :

1. Cliquez avec le bouton droit de la souris dans le tableau des détails, puis cliquez sur **[!UICONTROL Add Level]** > **[!UICONTROL Visitor]**.
1. Cliquez avec le bouton droit de la souris dans le tableau des détails, puis cliquez sur **[!UICONTROL Add Level]** > **[!UICONTROL Page View]**.
1. Cliquez avec le bouton droit de la souris sur l’en-tête de **[!UICONTROL Visitors]** niveau, puis cliquez sur **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL Domain]**.
1. Cliquez avec le bouton droit de la souris dans l’en-tête de niveau Visiteurs, puis cliquez sur **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL City]**.
1. Cliquez avec le bouton droit de la souris dans l’en-tête de niveau Visiteurs, puis cliquez sur **[!UICONTROL Add Metric]** > **[!UICONTROL Page Views]**.
1. Cliquez avec le bouton droit de la souris dans l’en-tête du niveau Pages vues, puis cliquez sur **[!UICONTROL Add Attribute]** > **[!UICONTROL Page]** > **[!UICONTROL Page]**.

L’exemple d’espace de travail suivant présente les détails associés à un échantillonnage aléatoire de six visiteurs du site pendant la période que vous avez spécifiée.

![](assets/client-tab1.png)

## Ajouter un niveau {#section-f948d3361fd84906ac4d9ebce520bfd0}

* Cliquez avec le bouton droit dans le tableau détaillé, puis cliquez sur **[!UICONTROL Add Level]** > *&lt;**[!UICONTROL dimension name]**>*.

![](assets/mnu_DetailsTable_AddLevel.png)

## Supprimer un niveau {#section-a8c820e0b656451e98e5ea75373edefc}

* Cliquez avec le bouton droit de la souris sur l’en-tête de niveau existant et cliquez sur **[!UICONTROL Remove Level]** > *&lt;**[!UICONTROL dimension name]**>*.

![](assets/mnu_DetailsTable_Level.png)

## Add attributes and metrics {#section-cdda2df3c9a448d5b9770686c8b8efb3}

* Cliquez avec le bouton droit de la souris sur un attribut ou un en-tête de mesure, puis cliquez sur **[!UICONTROL Add Attribute]** > *&lt;**[!UICONTROL attribute name]**>* ou **[!UICONTROL Add Metric]** > *&lt;**[!UICONTROL metric name]**>.*

![](assets/mnu_DetailsTable.png)

## Suppression d’attributs et de mesures {#section-4002ac957a2846678f9940270987d651}

* Cliquez avec le bouton droit sur la colonne à supprimer, puis cliquez sur **[!UICONTROL Remove Attribute]** > *&lt;**[!UICONTROL attribute name]**>* ou **[!UICONTROL Remove Metric]** > *&lt;**[!UICONTROL metric name]**>.*

![](assets/mnu_DetailsTable.png)

## Exporter vers Microsoft Excel {#section-a9eaba63c88a4598836a34669ba8cac1}

Pour plus d’informations sur l’exportation de fenêtres, voir [Exportation de données](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)de fenêtre.
