---
description: La projection UTM (Universal Transverse Mercator) est définie par huit paramètres.
solution: Analytics
title: Projections de Mercator transversal universel
topic: Data workbench
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Projections de Mercator transversal universel{#universal-transverse-mercator-projections}

La projection UTM (Universal Transverse Mercator) est définie par huit paramètres.

Lors de la spécification d’une projection Universal Transverse Mercator pour une couche d’image de terrain, vos fichiers d’image de terrain doivent être alignés avec la valeur false (projetée) vers le nord en haut de l’image et la valeur false vers l’est à droite de l’image.

Pour spécifier une projection UTM pour toute source d’image de terrain, vous devez ouvrir le [!DNL Terrain Images.cfg] fichier dans un éditeur de texte tel que le Bloc-notes, définir le paramètre Infos sur &quot;TransverseMercatorProjection&quot; et ajouter des paramètres pour la projection UTM.

**Pour spécifier une projection de Mercator transversal universel**

1. Dans la [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en afficher le contenu. Le [!DNL Terrain Images.cfg] fichier se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom *du* serveur [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Terrain Images.cfg].

1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le [!DNL Terrain Images.cfg]fichier apparaît dans une fenêtre du Bloc-notes.

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

| Paramètre | Description |
|---|---|
| Aplatissement inversé des ellipsoïdes, axe semimajor des ellipsoïdes | Paramètres de l&#39;ellipsoïde utilisé pour la projection. L&#39;axe semestriel est spécifié en mètres. |
| Fausse dérive | Le faux levage du méridien central de la projection, en mètres. Pour UTM, c&#39;est toujours 500 000. |
| Faux tout | Le faux pas de l&#39;équateur dans la projection, en mètres. Pour l&#39;UTM, il s&#39;agit de 0 pour les zones de l&#39;hémisphère nord et de 10 000 pour les zones de l&#39;hémisphère sud. |
| Coordonnées du coin nord-ouest, coordonnées du coin sud-est | Coordonnées (en mètres projetés) des coins supérieur gauche et inférieur droit de l’image. |
| Premier méridien | Longitude du méridien central de la projection, spécifiée en degrés à l&#39;est de Greenwich. Des nombres négatifs peuvent être utilisés pour indiquer des degrés vers l&#39;ouest. |
| Facteur d’échelle | Rapport entre le rayon du cylindre de projection et l&#39;axe semimajor de l&#39;ellipsoïde. Pour les projections de l’UTM (Universal Transverse Mercator), il s’agit toujours de 0,9996. |

