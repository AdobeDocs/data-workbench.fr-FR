---
description: Les tableaux de détail vous permettent d’afficher des informations supplémentaires sur un sous-ensemble de données, qui est défini par les sélections que vous effectuez dans d’autres visualisations.
title: Tableau des détails
uuid: 2becff5e-c78d-4ac7-8cda-814ad0193efd
exl-id: d7f0b768-f341-41e8-904b-ec98a25f7aa9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 3%

---

# Tableau des détails{#detail-table}

{{eol}}

Les tableaux de détail vous permettent d’afficher des informations supplémentaires sur un sous-ensemble de données, qui est défini par les sélections que vous effectuez dans d’autres visualisations.

Les informations supplémentaires que vous voyez sont un échantillonnage de toutes les données disponibles.

![](assets/vis_details.png)

Le tableau suivant décrit les éléments d&#39;un tableau détaillé.

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
   <td colname="col2"> <p>Toute dimension dénombrable pour laquelle vous souhaitez afficher des informations détaillées sur les attributs et les mesures. Le niveau est précédé du nombre d'éléments affichés sur le nombre d'éléments disponibles, par exemple 6/444 indique que 6 éléments sont affichés sur un possible 444. Dans l’exemple ci-dessus, le niveau Visiteurs indique que tous les détails fournis sont basés sur le visiteur. Le niveau Pages vues indique que tous les détails fournis sont basés sur la page vue. L’affichage simultané de plusieurs niveaux s’avère utile lorsque vous souhaitez analyser des données ayant différents parents dénombrables. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribut </p> </td> 
   <td colname="col02"> <p>Vert </p> </td> 
   <td colname="col2"> <p>Toute dimension qui correspond à un-à-plusieurs ou à un-à-un avec le niveau, comme Ville aux visiteurs. Chaque ligne affiche l’élément associé à chaque élément du niveau que vous avez sélectionné. Dans l’exemple ci-dessus, les attributs Domaine et Ville répertorient le domaine et la ville pour chacun des exemples de visiteurs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mesure </p> </td> 
   <td colname="col02"> <p>Bleu </p> </td> 
   <td colname="col2"> <p>Détails de la mesure sur le niveau que vous avez sélectionné. Dans l’exemple ci-dessus, avec le niveau défini sur Visiteurs, la mesure Pages vues affiche le nombre de pages vues pour un visiteur individuel, tandis que le niveau Pages vues fournit le détail de chacune de ces pages vues. </p> </td> 
  </tr> 
 </tbody> 
</table>

Supposons que vous travailliez avec les données du site web et que vous souhaitiez déterminer les pages consultées par les visiteurs de villes particulières et de domaines particuliers lors d’une période donnée.

Tout d’abord, vous devez créer une visualisation qui affiche la période qui vous intéresse, puis vous devez sélectionner cette période. Vous pouvez maintenant ajouter un tableau détaillé pour afficher les détails souhaités pour un exemple de nombre de visiteurs dans le jeu de données.

Pour afficher les détails décrits ci-dessus, vous devez effectuer les étapes suivantes :

1. Cliquez avec le bouton droit dans le tableau de détails, puis cliquez sur **[!UICONTROL Add Level]** > **[!UICONTROL Visitor]**.
1. Cliquez avec le bouton droit dans le tableau de détails, puis cliquez sur **[!UICONTROL Add Level]** > **[!UICONTROL Page View]**.
1. Cliquez avec le bouton droit de la souris sur le **[!UICONTROL Visitors]** en-tête de niveau et cliquez sur **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL Domain]**.
1. Cliquez avec le bouton droit dans l’en-tête du niveau Visiteurs, puis cliquez sur **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL City]**.
1. Cliquez avec le bouton droit dans l’en-tête du niveau Visiteurs, puis cliquez sur **[!UICONTROL Add Metric]** > **[!UICONTROL Page Views]**.
1. Cliquez avec le bouton droit dans l’en-tête de niveau Pages vues, puis cliquez sur **[!UICONTROL Add Attribute]** > **[!UICONTROL Page]** > **[!UICONTROL Page]**.

L’exemple d’espace de travail suivant montre les détails associés à un échantillonnage aléatoire de six visiteurs sur le site pendant la période que vous avez spécifiée.

![](assets/client-tab1.png)

## Ajouter un niveau {#section-f948d3361fd84906ac4d9ebce520bfd0}

* Cliquez avec le bouton droit dans le tableau détaillé, puis cliquez sur **[!UICONTROL Add Level]** > *&lt;**[!UICONTROL dimension name]**>*.

![](assets/mnu_DetailsTable_AddLevel.png)

## Supprimer un niveau {#section-a8c820e0b656451e98e5ea75373edefc}

* Cliquez avec le bouton droit de la souris sur l’en-tête de niveau existant, puis cliquez sur **[!UICONTROL Remove Level]** > *&lt;**[!UICONTROL dimension name]**>*.

![](assets/mnu_DetailsTable_Level.png)

## Ajout d’attributs et de mesures {#section-cdda2df3c9a448d5b9770686c8b8efb3}

* Cliquez avec le bouton droit sur un en-tête d’attribut ou de mesure, puis cliquez sur **[!UICONTROL Add Attribute]** > *&lt;**[!UICONTROL attribute name]**>* ou **[!UICONTROL Add Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_DetailsTable.png)

## Suppression d’attributs et de mesures {#section-4002ac957a2846678f9940270987d651}

* Cliquez avec le bouton droit sur la colonne à supprimer, puis cliquez sur **[!UICONTROL Remove Attribute]** > *&lt;**[!UICONTROL attribute name]**>* ou **[!UICONTROL Remove Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_DetailsTable.png)

## Exporter vers Microsoft Excel {#section-a9eaba63c88a4598836a34669ba8cac1}

Pour plus d’informations sur l’exportation de fenêtres, voir [Exportation des données de fenêtre](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
