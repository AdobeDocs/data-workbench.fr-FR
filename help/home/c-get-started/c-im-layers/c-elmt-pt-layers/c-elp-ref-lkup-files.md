---
description: Lors de la création d’un calque de point d’élément qui fait référence à un fichier de recherche pour obtenir des données de latitude et de longitude, l’emplacement du point est obtenu en récupérant chaque élément et sa latitude et longitude associées dans le fichier de recherche.
solution: Analytics
title: Définition de calques de points d’élément faisant référence à des fichiers de recherche
topic: Data workbench
uuid: 32c8de7a-4316-4f91-9810-7f584bc7fb0b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Définition de calques de points d’élément faisant référence à des fichiers de recherche{#define-element-point-layers-referencing-lookup-files}

Lors de la création d’un calque de point d’élément qui fait référence à un fichier de recherche pour obtenir des données de latitude et de longitude, l’emplacement du point est obtenu en récupérant chaque élément et sa latitude et longitude associées dans le fichier de recherche.

>[!NOTE]
>
>Au lieu d’utiliser un fichier de recherche, vous pouvez utiliser la fonctionnalité Points dynamiques, qui incorpore la latitude et la longitude d’un emplacement dans le nom de chaque élément d’une dimension. Voir [Définition De Calques De Point D’Élément À L’Aide De Points](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#concept-51adc5e1df8a48e7bd7a582967e4c512)Dynamiques.

Pour définir un calque de point d’élément qui fait référence à un fichier de recherche, vous devez créer ou avoir déjà accès aux éléments suivants :

* **Une dimension** définie dans le [!DNL Transformation.cfg file] ou un [!DNL transformation dataset include] fichier. Pour plus d’informations sur les fichiers de configuration de transformation, voir le Guide *de configuration des jeux de* données.

* **Fichier** de recherche contenant les données utilisées pour tracer chaque point de données. Ce fichier doit contenir au moins trois colonnes de données pour chaque point de données : la clé, la longitude et la latitude. Pour plus d’informations sur le format requis du fichier de recherche, voir Format [de fichier de couche de point d’](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2)élément.

* **Fichier** de calque spécifiant l’emplacement du fichier de recherche et identifiant la dimension et la mesure associées, ainsi que les noms des colonnes de clé, de longitude et de latitude dans le fichier de recherche. Pour plus d’informations sur le format requis du fichier de calque, voir Format [du fichier de calque de point d’](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2)élément.

   >[!NOTE]
   >
   >Le [!DNL Zip Points.layer] fichier, fourni avec le [!DNL Geography] profil, est un calque de point d’élément qui identifie le [!DNL Zipcode.dim] fichier, le [!DNL Sessions.metric] [!DNL Zip Points.txt] fichier, le fichier de recherche et les noms des colonnes de clé, de longitude, de latitude et de nom dans le fichier de recherche.

## Format du fichier de recherche de point d’élément {#section-0bc8c652c1bd40eb84078f2af71a5c06}

Le fichier de recherche de calque de point d’élément doit contenir au moins trois colonnes :

* **[!DNL Key]colonne :**Cette colonne doit contenir des données de clé communes, ce qui permet au serveur Outils de données de connecter les données du fichier de recherche à celles du jeu de données. La[!DNL key]colonne doit être la première colonne du fichier de recherche. Chaque ligne de cette colonne identifie un élément de la dimension.

* **[!DNL Longitude]colonne :**Cette colonne doit contenir la longitude de chaque point de données de la[!DNL Key]colonne.

* **[!DNL Latitude]colonne :**Cette colonne doit contenir la latitude de chaque point de données de la[!DNL Key]colonne.

* **[!DNL Name]colonne (facultatif) :**Si vous souhaitez spécifier un nom à afficher sur la carte pour chaque point de données, vous pouvez inclure une[!DNL Name]colonne dans le fichier de recherche.

Chaque ligne du fichier de [!DNL Zip Points.txt] recherche contient un code postal dans la première colonne, suivi de la longitude, de la latitude et du nom de la ville associée.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

## Format du fichier de calque de point d’élément {#section-52d7e92be8354d979af9e7a2210b76f2}

Chaque [!DNL .layer] fichier de calque de point d’élément qui fait référence à un fichier de recherche doit être formaté à l’aide du modèle suivant :

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

<table id="table_7287F8869DD04886BE1477CBB11EB796"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Chemins de données </td> 
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
   <td colname="col2"> <p>nom de la colonne dans le fichier de recherche contenant les données de clé commune, qui permet au serveur Outils de données d’intégrer les données dans le fichier de recherche dans le jeu de données. Il doit s’agir de la première colonne du fichier de recherche. </p> <p>Chaque ligne de cette colonne est un élément d’une dimension. Cette dimension doit être définie dans le fichier <span class="filepath"> Transformation.cfg</span> ou dans un fichier d’inclusion <span class="wintitle"> d’un jeu de données de</span> transformation et spécifiée dans le paramètre Dimension de ce fichier. Pour plus d’informations sur les fichiers de configuration de transformation, voir le Guide <i>de configuration des jeux de</i>données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2">Nom de la dimension (défini dans un fichier de configuration de transformation) contenant des éléments qui correspondent aux lignes de données de la colonne <span class="wintitle"> Clé</span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mesure </td> 
   <td colname="col2"> Nom de la mesure évaluée par rapport à la dimension spécifiée dans le paramètre Dimension. </td> 
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
     <ul id="ul_F15E43B3BFE54CDD8026837027E25819"> 
      <li id="li_5405D939540E4D0FA7828D2623D72C44">Mode de rendu 1. La taille des points est définie dans l’espace de l’écran (les points restent une taille constante par rapport à l’écran de l’ordinateur). Les points sont rendus à l’aide de polygones, de sorte qu’il n’existe aucune limite supérieure à la taille du point. Il s’agit du mode de rendu par défaut. </li> 
      <li id="li_61C5AA926777449E8804C7BCE9E46F9B">Mode de rendu 2. La taille du point est définie dans l’espace mondial (les points restent une taille constante par rapport au globe). Les points sont rendus à l’aide de polygones, de sorte qu’il n’existe aucune limite supérieure à la taille du point. </li> 
      <li id="li_C00527F959354D3BB7422EFFE1FB5135">Mode de rendu 3. La taille du point est définie dans l’espace de l’écran. Les points sont rendus à l’aide de points d’inflexion OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Le [!DNL Zip Points.layer] fichier est formaté comme suit :

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

