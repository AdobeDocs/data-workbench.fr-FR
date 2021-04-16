---
description: La projection de l'UTM (Universal Transverse Mercator) est définie par huit paramètres.
title: Projections Transverses universelles de Mercator
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
exl-id: 7d7610c3-14e7-474e-b792-ad413c86a2ef
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# Projections Transverses universelles de Mercator{#universal-transverse-mercator-projections}

La projection de l&#39;UTM (Universal Transverse Mercator) est définie par huit paramètres.

Lors de la spécification d&#39;une projection Universal Transverse Mercator pour une couche d&#39;image de terrain, vos fichiers d&#39;image de terrain doivent être alignés avec la valeur false (projetée) au nord vers le haut de l&#39;image et la valeur false à l&#39;est vers la droite de l&#39;image.

Pour spécifier une projection UTM pour toute source d&#39;image de relief, vous devez ouvrir le fichier [!DNL Terrain Images.cfg] dans un éditeur de texte tel que Notepad, définir le paramètre Infos projection sur &quot;TransverseMercatorProjection&quot; et ajouter des paramètres pour la projection UTM.

**Pour spécifier une projection de Mercator transversal universel**

1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour en vue le contenu. Le fichier [!DNL Terrain Images.cfg] se trouve dans ce répertoire.

1. Cliquez avec le bouton droit sur la coche de la colonne *nom du serveur* pour [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la colonne [!DNL Temp] pour [!DNL Terrain Images.cfg].

1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le fichier [!DNL Terrain Images.cfg]apparaît dans une fenêtre du Bloc-notes.

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
| Aplatissement inversé ellipsoïde, axe semi-majeur ellipsoïde | Les paramètres de l&#39;ellipsoïde utilisé pour la projection. L&#39;axe semimajor est spécifié en mètres. |
| Fausse dérive | La fausse côte du méridien central de la projection, en mètres. Pour UTM, c&#39;est toujours 500 000. |
| Faux tout | Le faux pas de l&#39;équateur dans la projection, en mètres. Pour l’UTM, il s’agit de 0 pour les zones de l’hémisphère nord et de 10 000 pour les zones de l’hémisphère sud. |
| Coordonnées du coin nord-ouest, coordonnées du coin sud-est | Les coordonnées (en mètres projetés) des coins supérieur gauche et inférieur droit de l’image. |
| Premier Meridian | Longitude du méridien central de la projection, spécifiée en degrés à l&#39;est de Greenwich. Des nombres négatifs peuvent être utilisés pour spécifier des degrés vers l&#39;ouest. |
| Facteur d&#39;échelle | Rapport entre le rayon du cylindre de projection et l&#39;axe semimajor de l&#39;ellipsoïde. Pour les projections Universal Transverse Mercator (UTM), il s’agit toujours de 0,9996. |
