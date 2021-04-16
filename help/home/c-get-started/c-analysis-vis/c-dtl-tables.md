---
description: Les tableaux de détails vous permettent de vue d’informations supplémentaires sur un sous-ensemble de données, qui est défini par les sélections que vous effectuez dans d’autres visualisations.
title: Tableau des détails
uuid: 2becff5e-c78d-4ac7-8cda-814ad0193efd
exl-id: d7f0b768-f341-41e8-904b-ec98a25f7aa9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 3%

---

# Tableau des détails{#detail-table}

Les tableaux de détails vous permettent de vue d’informations supplémentaires sur un sous-ensemble de données, qui est défini par les sélections que vous effectuez dans d’autres visualisations.

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
   <td colname="col2"> <p>Toute dimension dénombrable pour laquelle vous souhaitez vue des informations détaillées sur les attributs et les mesures. Le niveau est précédé par le nombre d'éléments affichés par rapport au nombre d'éléments disponibles, par exemple 6/444 indique que 6 éléments sont affichés sur un possible 444. Dans l’exemple ci-dessus, le niveau Visiteur indique que tous les détails fournis sont basés sur le visiteur. Le niveau Vues de page indique que tous les détails fournis dépendent de la vue de page. L’affichage simultané de plusieurs niveaux s’avère utile lorsque vous souhaitez analyser des données dont les parents sont dénombrables. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribut </p> </td> 
   <td colname="col02"> <p>Vert </p> </td> 
   <td colname="col2"> <p>Toute dimension qui correspond à un-à-plusieurs ou à un-à-un avec le niveau, tel que Ville à Visiteurs. Chaque ligne affiche l’élément associé à chaque élément du niveau que vous avez sélectionné. Dans l’exemple ci-dessus, les attributs Domaine et Ville liste le domaine et la ville pour chacun des exemples de visiteurs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mesure </p> </td> 
   <td colname="col02"> <p>Bleu </p> </td> 
   <td colname="col2"> <p>Détails de la mesure sur le niveau que vous avez sélectionné. Dans l’exemple ci-dessus, avec le niveau défini sur Visiteurs, la mesure Vues de page affiche le nombre de vues de page pour un visiteur individuel, tandis que le niveau Vues de page fournit les détails sur chacune de ces vues de page. </p> </td> 
  </tr> 
 </tbody> 
</table>

Supposons que vous travailliez sur les données du site Web et que vous souhaitiez identifier les pages visitées par les visiteurs dans certaines villes et certains domaines au cours d&#39;une période donnée.

Vous devez d’abord créer une visualisation qui affiche la période qui vous intéresse, puis vous devez sélectionner cette période. Vous pouvez maintenant ajouter un tableau détaillé pour vue les détails désirés pour un échantillon de visiteurs dans le jeu de données.

Pour vue aux détails décrits ci-dessus, vous devez effectuer les étapes suivantes :

1. Cliquez avec le bouton droit de la souris dans le tableau des détails, puis cliquez sur **[!UICONTROL Add Level]** > **[!UICONTROL Visitor]**.
1. Cliquez avec le bouton droit de la souris dans le tableau des détails, puis cliquez sur **[!UICONTROL Add Level]** > **[!UICONTROL Page View]**.
1. Cliquez avec le bouton droit sur l&#39;en-tête de niveau **[!UICONTROL Visitors]** et cliquez sur **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL Domain]**.
1. Cliquez avec le bouton droit dans l&#39;en-tête de niveau Visiteur et cliquez sur **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL City]**.
1. Cliquez avec le bouton droit dans l&#39;en-tête de niveau Visiteur et cliquez sur **[!UICONTROL Add Metric]** > **[!UICONTROL Page Views]**.
1. Cliquez avec le bouton droit dans l&#39;en-tête de niveau Vues de page et cliquez sur **[!UICONTROL Add Attribute]** > **[!UICONTROL Page]** > **[!UICONTROL Page]**.

L’exemple d’espace de travail suivant vous montre les détails associés pour un échantillonnage aléatoire de six visiteurs sur le site pendant la période que vous avez spécifiée.

![](assets/client-tab1.png)

## Ajouter un niveau {#section-f948d3361fd84906ac4d9ebce520bfd0}

* Cliquez avec le bouton droit de la souris dans le tableau détaillé et cliquez sur **[!UICONTROL Add Level]** > *&lt;**[!UICONTROL dimension name]***.

![](assets/mnu_DetailsTable_AddLevel.png)

## Supprimer un niveau {#section-a8c820e0b656451e98e5ea75373edefc}

* Cliquez avec le bouton droit sur l’en-tête de niveau existant et cliquez sur **[!UICONTROL Remove Level]** > *&lt;**[!UICONTROL dimension name]***.

![](assets/mnu_DetailsTable_Level.png)

## Ajouter des attributs et des mesures {#section-cdda2df3c9a448d5b9770686c8b8efb3}

* Cliquez avec le bouton droit sur un en-tête d&#39;attribut ou de mesure, puis cliquez sur **[!UICONTROL Add Attribute]** > *&lt;**[!UICONTROL attribute name]*** ou **[!UICONTROL Add Metric]** > *&lt;**[!UICONTROL metric name]***.

![](assets/mnu_DetailsTable.png)

## Supprimer des attributs et des mesures {#section-4002ac957a2846678f9940270987d651}

* Cliquez avec le bouton droit sur la colonne à supprimer, puis cliquez sur **[!UICONTROL Remove Attribute]** > *&lt;**[!UICONTROL attribute name]*** ou **[!UICONTROL Remove Metric]** > *&lt;**[!UICONTROL metric name]***.

![](assets/mnu_DetailsTable.png)

## Exporter vers Microsoft Excel {#section-a9eaba63c88a4598836a34669ba8cac1}

Pour plus d’informations sur l’exportation de fenêtres, voir [Exportation de données de fenêtre](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
