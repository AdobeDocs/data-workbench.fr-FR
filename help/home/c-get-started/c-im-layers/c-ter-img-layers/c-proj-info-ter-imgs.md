---
description: Les outils de données prennent en charge à la fois les projections latitude-longitude et les projections UTM (Universal Transverse Mercator) pour toutes les sources de calques d’images du terrain.
solution: Analytics
title: Spécification des informations de projection pour les images de terrain
topic: Data workbench
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Spécification des informations de projection pour les images de terrain{#specify-projection-information-for-terrain-images}

Les outils de données prennent en charge à la fois les projections latitude-longitude et les projections UTM (Universal Transverse Mercator) pour toutes les sources de calques d’images du terrain.

Les informations de projection sont requises pour les bitmaps bruts non projetés et les images générales, non projetées. Vous pouvez spécifier des informations de projection pour les images avec des informations de projection incorporées, même si elles ne sont généralement pas requises car les paramètres de la projection sont déterminés automatiquement à partir de données géodésiques incorporées dans l’image elle-même. Les sections suivantes fournissent des détails sur la spécification de ces formats de projection dans le [!DNL Terrain Images.cfg] fichier.

## Projections de latitude-longitude {#section-6e335357ec28462ba39c565e0a5986c7}

Le format de projection latitude-longitude (LatLonProjection) dans le [!DNL Terrain Images.cfg] fichier est défini par quatre paramètres pour la latitude et la longitude.

Pour spécifier une LatLonProjection pour les images non projetées (images brutes non projetées et images générales, non projetées), vous pouvez saisir les paramètres de la LatLonProjection dans la [!DNL Terrain Images.cfg] fenêtre des Outils de données.

Pour spécifier une LatLonProjection pour les images avec des informations de projection incorporées, vous devez ouvrir le [!DNL Terrain Images.cfg] fichier dans un éditeur de texte tel que le Bloc-notes, définir le paramètre Infos sur LatLonProjection et ajouter des paramètres pour le [!DNL LatLonProjection].

**Pour spécifier une projection LatLon pour les images non projetées**

1. Ouvrez le [!DNL Terrain Images.cfg] fichier dans les Outils de données et ajoutez une source de calque d’image de terrain comme décrit dans [Pour définir une couche](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f)d’image de terrain.
1. Modifiez les paramètres Infos sur la projection à l’aide du tableau de paramètres suivant comme guide :

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
   <td colname="col2"> <p>La latitude du bord supérieur de l'image, en degrés, où 90 est le pôle Nord et -90 est le pôle Sud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>latitude du bord inférieur de l’image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>Longitude du bord gauche de l’image, en degrés, où les nombres positifs sont orientaux et les nombres négatifs sont longitudes ouest. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>Longitude du bord droit de l’image. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et en cliquant sur **[!UICONTROL Save]**.
1. Pour enregistrer les modifications apportées localement sur l’ordinateur du serveur Outils de données, dans la [!DNL Server Files Manager]colonne, cliquez avec le bouton droit de la souris sur la coche [!DNL Terrain Images.cfg] dans la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

**Pour spécifier une LatLonProjection pour les images dans les informations de projection incorporée**

Dans la [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en afficher le contenu. Le [!DNL Terrain Images.cfg] fichier se trouve dans ce répertoire.

Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom du serveur [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Terrain Images.cfg].

Cliquez avec le bouton droit sur la coche nouvellement créée dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le [!DNL Terrain Images.cfg] fichier apparaît dans une fenêtre du Bloc-notes.

Modifiez les paramètres Infos sur la projection à l’aide de l’exemple de fragment de fichier suivant comme guide. Veillez à spécifier le type de projection comme indiqué ci-dessous. Pour obtenir la description des paramètres, reportez-vous au tableau Paramètres LatLonProjection de la procédure précédente.

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## Projections de Mercator transversal universel {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

La projection UTM (Universal Transverse Mercator) est définie par huit paramètres. Lors de la spécification d’une projection Universal Transverse Mercator pour une couche d’image de terrain, vos fichiers d’image de terrain doivent être alignés avec la valeur false (projetée) vers le nord en haut de l’image et la valeur false vers l’est à droite de l’image.

Pour spécifier une projection UTM pour toute source d’image de terrain, vous devez ouvrir le [!DNL Terrain Images.cfg] fichier dans un éditeur de texte tel que le Bloc-notes, définir le paramètre Infos sur &quot;TransverseMercatorProjection&quot; et ajouter des paramètres pour la projection UTM.

**Pour spécifier une projection de Mercator transversal universel**

1. Dans la [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en afficher le contenu. Le [!DNL Terrain Images.cfg] fichier se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom du serveur [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Terrain Images.cfg.]
1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le [!DNL Terrain Images.cfg] fichier apparaît dans une fenêtre du Bloc-notes.
1. Modifiez les paramètres Infos sur la projection à l’aide de l’exemple de fragment de fichier et du tableau de paramètres ci-dessous comme guides. Veillez à spécifier le type de projection comme indiqué ci-dessous.

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
   <td colname="col1"> <p>Aplatissement inversé des ellipsoïdes, axe semimajor des ellipsoïdes </p> </td> 
   <td colname="col2"> <p>Paramètres de l'ellipsoïde utilisé pour la projection. L'axe semestriel est spécifié en mètres. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fausse dérive </p> </td> 
   <td colname="col2"> <p>Le faux levage du méridien central de la projection, en mètres. Pour UTM, c'est toujours 500 000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Faux tout </p> </td> 
   <td colname="col2"> <p>Le faux pas de l'équateur dans la projection, en mètres. Pour l'UTM, il s'agit de 0 pour les zones de l'hémisphère nord et de 10 000 pour les zones de l'hémisphère sud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Coordonnées du coin nord-ouest, coordonnées du coin sud-est </p> </td> 
   <td colname="col2"> <p>Coordonnées (en mètres projetés) des coins supérieur gauche et inférieur droit de l’image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premier méridien </p> </td> 
   <td colname="col2"> <p>Longitude du méridien central de la projection, spécifiée en degrés à l'est de Greenwich. Des nombres négatifs peuvent être utilisés pour indiquer des degrés vers l'ouest. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Facteur d’échelle </p> </td> 
   <td colname="col2"> <p>Rapport entre le rayon du cylindre de projection et l'axe semimajor de l'ellipsoïde. Pour les projections de l’UTM (Universal Transverse Mercator), il s’agit toujours de 0,9996. </p> </td> 
  </tr> 
 </tbody> 
</table>

