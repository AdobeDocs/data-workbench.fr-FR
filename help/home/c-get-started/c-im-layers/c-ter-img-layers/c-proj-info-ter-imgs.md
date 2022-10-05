---
description: Data Workbench prend en charge les projections latitude-longitude et les projections UTM (Universal Transverse Mercator) pour toutes les sources de couche d’image du terrain.
title: Préciser les informations de projection des images du terrain
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
exl-id: 2638c5d4-164d-411b-8464-0a3af81b6537
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 3%

---

# Préciser les informations de projection des images du terrain{#specify-projection-information-for-terrain-images}

{{eol}}

Data Workbench prend en charge les projections latitude-longitude et les projections UTM (Universal Transverse Mercator) pour toutes les sources de couche d’image du terrain.

Les informations de projection sont requises pour les images bitmap brutes non projetées et les images générales, non projetées. Vous pouvez spécifier des informations de projection pour les images avec des informations de projection incorporées, bien qu’elles ne soient généralement pas nécessaires car les paramètres de projection sont déterminés automatiquement à partir de données géodésiques incorporées dans l’image elle-même. Les sections suivantes fournissent des détails sur la spécification de ces formats de projection dans [!DNL Terrain Images.cfg] fichier .

## Projections latitude-longitude {#section-6e335357ec28462ba39c565e0a5986c7}

Le format de projection latitude-longitude (LatLonProjection) dans la variable [!DNL Terrain Images.cfg] est défini par quatre paramètres pour la latitude et la longitude.

Pour spécifier une projection LatLon pour les images non projetées (images brutes non projetées et images générales, non projetées), vous pouvez saisir les paramètres de la projection LatLon dans la variable [!DNL Terrain Images.cfg] en Data Workbench.

Pour spécifier une projection LatLon pour les images avec les informations de projection incorporées, vous devez ouvrir la fenêtre [!DNL Terrain Images.cfg] dans un éditeur de texte tel que Notepad, définissez le paramètre Informations sur la projection sur LatLonProjection et ajoutez les paramètres de la variable [!DNL LatLonProjection].

**Pour spécifier une projection LatLon pour les images non projetées**

1. Ouvrez le [!DNL Terrain Images.cfg] en Data Workbench et ajoutez une source de calque d’image du terrain, comme décrit à la section [Pour définir un calque d’image du terrain](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).
1. Modifiez les paramètres Informations de projection à l’aide du tableau de paramètres suivant comme guide :

<table id="table_32F6EADB2DA34592ABD6FFAC9E00BB27"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lat0 </p> </td> 
   <td colname="col2"> <p>La latitude du bord supérieur de l’image, en degrés, où 90 est le pôle Nord et -90 est le pôle Sud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>Latitude du bord inférieur de l’image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>Longitude du bord gauche de l’image, en degrés, où les nombres positifs sont orientés et les nombres négatifs, longitude ouest. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>Longitude du bord droit de l’image. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Enregistrez le fichier en cliquant avec le bouton droit de la souris **[!UICONTROL (modified)]** en haut de la fenêtre et en cliquant sur **[!UICONTROL Save]**.
1. Pour enregistrer les modifications apportées localement à l’ordinateur du serveur de Data Workbench, dans la variable [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche pour [!DNL Terrain Images.cfg] dans le [!DNL Temp] , puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

**Pour spécifier une projection LatLon pour les images dans les informations de projection incorporée**

Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour afficher son contenu. Le [!DNL Terrain Images.cfg] se trouve dans ce répertoire.

Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom de serveur pour [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la variable [!DNL Temp] column pour [!DNL Terrain Images.cfg].

Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans le [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le [!DNL Terrain Images.cfg] s’affiche dans une fenêtre Bloc-notes.

Modifiez les paramètres Informations de projection à l’aide de l’exemple de fragment de fichier suivant comme guide. Veillez à spécifier le type de projection comme indiqué ci-dessous. Pour obtenir une description des paramètres, reportez-vous au tableau LatLonProjection Parameters de la procédure précédente.

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## Projections Transverses universelles de Mercator {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

La projection Transverse universelle (UTM) est définie par huit paramètres. Lors de la spécification d’une projection Transverse universelle de Mercator pour une couche d’image du terrain, vos fichiers image du terrain doivent être alignés avec la valeur false (projetée) au nord vers le haut de l’image, et la valeur false à l’est vers la droite de l’image.

Pour spécifier une projection UTM pour n’importe quelle source d’image du terrain, vous devez ouvrir la [!DNL Terrain Images.cfg] dans un éditeur de texte tel que Notepad, définissez le paramètre Informations de projection sur &quot;TransverseMercatorProjection&quot;, puis ajoutez les paramètres de la projection UTM.

**Pour spécifier une projection Transverse universelle de Mercator**

1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour afficher son contenu. Le [!DNL Terrain Images.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom de serveur pour [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la variable [!DNL Temp] column pour [!DNL Terrain Images.cfg.]
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans le [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le [!DNL Terrain Images.cfg] s’affiche dans une fenêtre Bloc-notes.
1. Modifiez les paramètres Informations de projection à l’aide de l’exemple de fragment de fichier et du tableau de paramètres ci-dessous sous forme de guides. Veillez à spécifier le type de projection comme indiqué ci-dessous.

   ```
   Projection Info = TransverseMercatorProjection:
     Ellipsoid Inverse Flattening = double: 294.9786982139006
     Ellipsoid Semimajor Axis = double: 6378206.4000000004
     False Easting = double: 500000
     False Northing = double: 0
     Northwest Corner Coordinates = v3d: (550339, 5.42059e+006, 0)
     Prime Meridian = double: -123
     Scale Factor = double: 0.9996
     Southeast Corner Coordinates = v3d: (555099, 5.41356e+006, 0)
   ```

<table id="table_71AEEAE808B9436B9846987A54D5D1D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ellipsoid Inverse Flattening, Ellipsoid Semimajor Axe </p> </td> 
   <td colname="col2"> <p>Les paramètres de l'ellipsoid utilisé pour la projection. L’axe du point-virgule est spécifié en mètres. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fausse accolade </p> </td> 
   <td colname="col2"> <p>La fausse côte du méridien central de la projection, en mètres. Pour UTM, il s’agit toujours de 500 000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Faux rien </p> </td> 
   <td colname="col2"> <p>Le faux pas de l'équateur dans la projection, en mètres. Pour UTM, il s’agit de 0 pour les zones de l’hémisphère nord et de 10 000 pour les zones de l’hémisphère sud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Coordonnées du coin nord-ouest, coordonnées du coin sud-est </p> </td> 
   <td colname="col2"> <p>Coordonnées (en mètres projetés) des coins supérieur gauche et inférieur droit de l’image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premier ministre Meridian </p> </td> 
   <td colname="col2"> <p>Longitude du méridien central de la projection, exprimée en degrés à l’est de Greenwich. Des nombres négatifs peuvent être utilisés pour spécifier les degrés ouest. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Facteur d’échelle </p> </td> 
   <td colname="col2"> <p>Rapport entre le rayon du cylindre de projection et l’axe semimajor de l’ellipsoid. Pour les projections Universal Transverse Mercator (UTM), il s’agit toujours de 0,9996. </p> </td> 
  </tr> 
 </tbody> 
</table>
