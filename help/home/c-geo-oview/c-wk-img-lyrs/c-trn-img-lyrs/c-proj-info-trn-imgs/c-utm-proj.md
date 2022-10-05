---
description: La projection Transverse universelle (UTM) est définie par huit paramètres.
title: Projections Transverses universelles de Mercator
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
exl-id: 7d7610c3-14e7-474e-b792-ad413c86a2ef
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# Projections Transverses universelles de Mercator{#universal-transverse-mercator-projections}

{{eol}}

La projection Transverse universelle (UTM) est définie par huit paramètres.

Lors de la spécification d’une projection Transverse universelle de Mercator pour une couche d’image du terrain, vos fichiers image du terrain doivent être alignés avec la valeur false (projetée) au nord vers le haut de l’image, et la valeur false à l’est vers la droite de l’image.

Pour spécifier une projection UTM pour n’importe quelle source d’image du terrain, vous devez ouvrir la [!DNL Terrain Images.cfg] dans un éditeur de texte tel que Notepad, définissez le paramètre Informations de projection sur &quot;TransverseMercatorProjection&quot;, puis ajoutez les paramètres de la projection UTM.

**Pour spécifier une projection Transverse universelle de Mercator**

1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour afficher son contenu. Le [!DNL Terrain Images.cfg] se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* column pour [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la variable [!DNL Temp] column pour [!DNL Terrain Images.cfg].

1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans le [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le [!DNL Terrain Images.cfg]s’affiche dans une fenêtre Bloc-notes.

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

| Paramètre | Description |
|---|---|
| Ellipsoid Inverse Flattening, Ellipsoid Semimajor Axe | Les paramètres de l&#39;ellipsoid utilisé pour la projection. L’axe du point-virgule est spécifié en mètres. |
| Fausse accolade | La fausse côte du méridien central de la projection, en mètres. Pour UTM, il s’agit toujours de 500 000. |
| Faux rien | Le faux pas de l&#39;équateur dans la projection, en mètres. Pour UTM, il s’agit de 0 pour les zones de l’hémisphère nord et de 10 000 pour les zones de l’hémisphère sud. |
| Coordonnées du coin nord-ouest, coordonnées du coin sud-est | Coordonnées (en mètres projetés) des coins supérieur gauche et inférieur droit de l’image. |
| Premier ministre Meridian | Longitude du méridien central de la projection, exprimée en degrés à l’est de Greenwich. Des nombres négatifs peuvent être utilisés pour spécifier les degrés ouest. |
| Facteur d’échelle | Rapport entre le rayon du cylindre de projection et l’axe semimajor de l’ellipsoid. Pour les projections Universal Transverse Mercator (UTM), il s’agit toujours de 0,9996. |
