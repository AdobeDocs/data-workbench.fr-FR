---
description: Formatage des informations sur le fichier de calque de point d’élément.
title: Format de fichier de calque de point d’élément
uuid: a8b3d2f4-0ed2-480d-a2a6-75d43025a579
exl-id: 125796f6-a447-4f12-bcf2-3e669783cf1e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 5%

---

# Format de fichier de calque de point d’élément{#element-point-layer-file-format}

Formatage des informations sur le fichier de calque de point d’élément.

Chaque fichier [!DNL .layer] de couche de point d’élément qui référence un fichier de recherche doit être formaté à l’aide du modèle suivant :

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Lookup File Name.txt
  Longitude Column = string: Longitude Column Name
  Latitude Column = string: Latitude Column Name
  Name Column = string: Location Column Name
  Key Column = string: Key Column Name
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_B2BC5FE8C80E4680B9A565878192D75B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Chemins des données </td> 
   <td colname="col2"> Chemin d’accès au fichier de recherche contenant les données de latitude et de longitude. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonne de longitude </td> 
   <td colname="col2"> Nom de la colonne dans le fichier de recherche contenant les données de longitude. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonne Latitude </td> 
   <td colname="col2"> Nom de la colonne dans le fichier de recherche contenant les données de latitude. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonne de nom </td> 
   <td colname="col2"> Facultatif. Nom de la colonne dans le fichier de recherche contenant les noms des emplacements représentés par les données de latitude et de longitude. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonne de clé </td> 
   <td colname="col2"> <p>Le nom de la colonne dans le fichier de recherche contenant les données de clé communes, qui permet au serveur Data Workbench d’intégrer les données dans le fichier de recherche dans le jeu de données. Il doit s’agir de la première colonne du fichier de recherche. </p> <p>Chaque ligne de cette colonne est un élément d’une dimension. Cette dimension doit être définie dans le fichier <span class="filepath"> Transformation.cfg</span> ou dans un fichier d’inclusion de jeux de données de transformation et spécifiée dans le paramètre de Dimension de ce fichier. Pour plus d’informations sur les fichiers de configuration de transformation, consultez le <i>Guide de configuration des jeux de données</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2">Nom de la dimension (défini dans un fichier de configuration de transformation) contenant des éléments qui correspondent aux lignes de données de la colonne <span class="wintitle"> Clé</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mesure </td> 
   <td colname="col2"> Nom de la mesure évaluée par rapport à la dimension spécifiée dans le paramètre de Dimension. </td> 
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
     <ul id="ul_CBB26B32505846A39FEB85E831E1C7AB"> 
      <li id="li_B31528A8858C4418ABCDFF0B4EFB25D7">Mode de rendu 1. La taille des points est définie dans l’espace de l’écran (la taille des points reste constante par rapport à l’écran de l’ordinateur). Les points sont rendus à l’aide de polygones. Il n’existe donc pas de limite supérieure à la taille du point. Il s’agit du mode de rendu par défaut. </li> 
      <li id="li_CA0C3E0DBF004ADBB4D7819C0BF192FC">Mode de rendu 2. La taille du point est définie dans l’espace mondial (les points restent à une taille constante par rapport au globe). Les points sont rendus à l’aide de polygones. Il n’existe donc pas de limite supérieure à la taille du point. </li> 
      <li id="li_8F8729976DDB434D869E81D4381E2688">Mode de rendu 3. La taille du point est définie dans l’espace de l’écran. Les points sont rendus à l’aide de points lissés OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Le fichier [!DNL Zip Points.layer] est formaté comme suit :

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Zip Points.txt
  Longitude Column = string: LONGITUDE
  Latitude Column = string: LATITUDE
  Name Column = string: NAME
  Key Column = string: ZIP_CODE
  Dimension = ref: wdata/model/dim/Zipcode
  Metric = ref: wdata/model/metric/Sessions
```
