---
description: Lors de la création d’un calque de point d’élément à l’aide de points dynamiques, les données de latitude et de longitude sont intégrées à chaque élément de la dimension.
solution: Analytics
title: Définition de calques de points d’élément à l’aide de points dynamiques
topic: Data workbench
uuid: f4b41969-329a-4c33-a8db-8d85597fa577
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Définition de calques de points d’élément à l’aide de points dynamiques{#define-element-point-layers-using-dynamic-points}

Lors de la création d’un calque de point d’élément à l’aide de points dynamiques, les données de latitude et de longitude sont intégrées à chaque élément de la dimension.

Pour définir un calque de point d’élément à l’aide de points dynamiques, vous devez créer ou avoir déjà accès aux éléments suivants :

* Une dimension, définie dans le [!DNL Transformation.cfg] fichier ou un [!DNL transformation dataset include] fichier, dans laquelle chaque élément contient la chaîne &quot;latitude, longitude&quot; ou &quot;latitude, longitude, nom&quot;.

   Pour connaître les étapes de création d’une dimension, consultez le Guide *de configuration des jeux de* données.

* Fichier de calque spécifiant la dimension associée.

Pour plus d’informations sur le format requis du fichier de calque, voir Format [du fichier de calque de point d’](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#section-0645fbc761c14bb986f3d6f02df407a0)élément.

>[!NOTE]
>
>Lors de [!DNL Dynamic Points]l’utilisation, il est essentiel de s’assurer que la cardinalité de la dimension spécifiée dans le fichier de calque est raisonnable. Si chaque ligne d’un jeu de données a une latitude et une longitude différentes, la dimension se remplit rapidement et la plupart des lignes tombent dans un élément Petits éléments. L’élément Petits éléments n’ayant pas de latitude et de longitude, il n’apparaît pas sur le globe.

## Format du fichier de calque de point d’élément {#section-0645fbc761c14bb986f3d6f02df407a0}

Chaque fichier de calque de points d’élément utilisant des points dynamiques doit être formaté à l’aide du modèle suivant :

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_8756BDCC49F447C0855BA64BC0078A0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2"> <p>Nom de la dimension (défini dans un fichier de configuration de transformation), qui doit contenir des éléments avec la chaîne "latitude,longitude" ou "latitude,longitude,nom", comme illustré dans les exemples suivants : 
     <ul id="ul_CC12F05459C640F5AB3C295932B04F83"> 
      <li id="li_9023CFA04A0F407E9DF0E1A4D71BB18C">37.5181,-77.1903 </li> 
      <li id="li_F002AB3AB98049A4AF1588B51167C7FA">35.3317,-77.8126, Quelque part </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mesure </td> 
   <td colname="col2"> Nom de la mesure évaluée par rapport à la dimension spécifiée dans le paramètre Dimension. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Points dynamiques </td> 
   <td colname="col2"> Active les points dynamiques. Définissez cette variable sur true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Echelle </td> 
   <td colname="col2"> Facultatif. Valeur utilisée pour dimensionner les points du calque. La valeur par défaut est 100. Des valeurs plus élevées agrandissent les points et des valeurs plus petites les réduisent. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Couleur </td> 
   <td colname="col2"> Facultatif. Vecteur de couleur RVB, exprimé sous la forme (rouge, vert, bleu). Pour chaque couleur du vecteur, vous pouvez saisir une valeur comprise entre 0,0 et 1,0. Par exemple, (1.0, 0.0, 0.0) est rouge vif et (0.5, 0.5, 0.5) est gris. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mode de rendu </td> 
   <td colname="col2"> <p>Facultatif. Valeur entière représentant le mode de rendu à utiliser pour le calque. Les trois modes disponibles sont les suivants : 
     <ul id="ul_C7A74B9B085741C8B7116E4F110DF830"> 
      <li id="li_75CC2BE35C594B6895F743A1967A2E07">Mode de rendu 1. La taille des points est définie dans l’espace de l’écran (les points restent une taille constante par rapport à l’écran de l’ordinateur). Les points sont rendus à l’aide de polygones, de sorte qu’il n’existe aucune limite supérieure à la taille du point. Il s’agit du mode de rendu par défaut. </li> 
      <li id="li_5B19C5B0F59548E28DCE7F7CD319E210">Mode de rendu 2. La taille du point est définie dans l’espace mondial (les points restent une taille constante par rapport au globe). Les points sont rendus à l’aide de polygones, de sorte qu’il n’existe aucune limite supérieure à la taille du point. </li> 
      <li id="li_DF0C9AEFE82642C9BD5AEA79770D2896">Mode de rendu 3. La taille du point est définie dans l’espace de l’écran. Les points sont rendus à l’aide de points d’inflexion OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Le [!DNL IP Coordinates.layer] fichier est formaté comme suit :

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```

