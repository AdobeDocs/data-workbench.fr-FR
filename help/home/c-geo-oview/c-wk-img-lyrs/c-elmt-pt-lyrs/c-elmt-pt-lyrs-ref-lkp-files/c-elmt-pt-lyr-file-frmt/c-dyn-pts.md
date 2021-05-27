---
description: Lors de la création d’une couche de point d’élément à l’aide de points dynamiques, les données de latitude et de longitude sont incorporées dans chaque élément de la dimension.
title: Définir des calques de point d’élément à l’aide de points dynamiques
uuid: 5f1b4638-fe45-40be-b963-18dcd5d09afa
exl-id: ad849fe7-b909-40ef-835f-f1764e008de9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 7%

---

# Définir des calques de point d’élément à l’aide de points dynamiques{#defining-element-point-layers-using-dynamic-points}

Lors de la création d’une couche de point d’élément à l’aide de points dynamiques, les données de latitude et de longitude sont incorporées dans chaque élément de la dimension.

Pour définir un calque de point d’élément à l’aide de points dynamiques, vous devez créer ou disposer déjà des éléments suivants :

* **Une dimension**, définie dans le  [!DNL Transformation.cfg] fichier ou un fichier d’inclusion de jeu de données de transformation, dans lequel chaque élément contient la chaîne &quot;latitude, longitude&quot; ou &quot;latitude, longitude, nom&quot;.

   Pour connaître les étapes de création d’une dimension, consultez le *Guide de configuration du jeu de données*.

* **Un** fichier de calque qui spécifie la dimension associée.

   Pour plus d’informations sur le format requis du fichier de calque, voir [Format de fichier de calque de point d’élément](../../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>Lors de l’utilisation de [!DNL Dynamic Points], il est essentiel de s’assurer que la cardinalité de la dimension spécifiée dans le fichier de calque est raisonnable. Si chaque ligne d’un jeu de données comporte une latitude et une longitude différentes, la dimension se remplit rapidement et la plupart des lignes tombent dans un élément Petits éléments. Comme l’élément Small Elements n’a pas de latitude et de longitude, il n’apparaît pas sur le globe.

## Format de fichier de calque de point d’élément {#section-bbcc2baa2f754dba81eba93339a97cbd}

Chaque fichier de calque de point d’élément utilisant des points dynamiques doit être formaté à l’aide du modèle suivant :

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_71AD13D7A9234782A4495DFBBD959F76"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2"> <p>Nom de la dimension (défini dans un fichier de configuration de transformation), qui doit contenir des éléments avec la chaîne "latitude,longitude" ou "latitude,longitude,nom" comme illustré dans les exemples suivants : 
     <ul id="ul_49069B74AF5A4CE28E20BB3B98BB2D89"> 
      <li id="li_296010E3A513424A86AFA09E4DA2DFA4">37.5181, -77.1903 </li> 
      <li id="li_352D380B55044DD5AAB9B6FF8335AAC6">35.3317, -77.8126, Somewhere </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mesure </td> 
   <td colname="col2"> Nom de la mesure évaluée par rapport à la dimension spécifiée dans le paramètre de Dimension. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Points dynamiques </td> 
   <td colname="col2"> Active les points dynamiques. Définissez cette variable sur true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Échelle </td> 
   <td colname="col2"> Facultatif. Valeur utilisée pour dimensionner les points du calque. La valeur par défaut est 100. Des valeurs plus élevées agrandissent les points et des valeurs plus petites les réduisent. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Couleur </td> 
   <td colname="col2"> Facultatif. Le vecteur de couleur RVB, exprimé sous la forme (rouge, vert, bleu). Pour chaque couleur du vecteur, vous pouvez saisir une valeur comprise entre 0,0 et 1,0. Par exemple, (1,0, 0,0, 0,0) est rouge vif et (0,5, 0,5, 0,5) est gris. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mode de rendu </td> 
   <td colname="col2"> <p>Facultatif. Valeur entière représentant le mode de rendu à utiliser pour le calque. Les trois modes disponibles sont les suivants : 
     <ul id="ul_771F0E43E3CD45259918520F092BCCE4"> 
      <li id="li_2B4CF2EC50174143AAD589A08C7457F8">Mode de rendu 1. La taille des points est définie dans l’espace de l’écran (la taille des points reste constante par rapport à l’écran de l’ordinateur). Les points sont rendus à l’aide de polygones. Il n’existe donc pas de limite supérieure à la taille du point. Il s’agit du mode de rendu par défaut. </li> 
      <li id="li_5F0737A941474EF5898735ECD0563D8D">Mode de rendu 2. La taille du point est définie dans l’espace mondial (les points restent à une taille constante par rapport au globe). Les points sont rendus à l’aide de polygones. Il n’existe donc pas de limite supérieure à la taille du point. </li> 
      <li id="li_4B9EDE5FFA8348B9A50E5232CEB98F17">Mode de rendu 3. La taille du point est définie dans l’espace de l’écran. Les points sont rendus à l’aide de points lissés OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Le fichier [!DNL IP Coordinates.layer] est formaté comme suit :

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```
