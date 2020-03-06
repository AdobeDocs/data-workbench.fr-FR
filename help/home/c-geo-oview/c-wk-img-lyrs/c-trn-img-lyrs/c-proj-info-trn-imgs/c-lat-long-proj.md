---
description: Le format de projection latitude-longitude (LatLonProjection) dans le fichier Terrain Images.cfg est défini par quatre paramètres pour la latitude et la longitude.
solution: Analytics
title: Projections de latitude-longitude
topic: Data workbench
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Projections de latitude-longitude{#latitude-longitude-projections}

Le format de projection latitude-longitude (LatLonProjection) dans le fichier Terrain Images.cfg est défini par quatre paramètres pour la latitude et la longitude.

Pour spécifier une LatLonProjection pour les images non projetées (images brutes non projetées et images générales, non projetées), vous pouvez saisir les paramètres de LatLonProjection dans la [!DNL Terrain Images.cfg] fenêtre de l’outil de données. Voir [Pour spécifier une projection LatLon pour les images](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)non projetées.

Pour spécifier une LatLonProjection pour les images avec des informations de projection incorporées, vous devez ouvrir le [!DNL Terrain Images.cfg] fichier dans un éditeur de texte tel que le Bloc-notes, définir le paramètre Infos sur &quot;LatLonProjection&quot; et ajouter des paramètres pour LatLonProjection. Voir [Pour spécifier une projection LatLon pour les images dans les informations de projection incorporée...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [Pour spécifier une projection LatLon pour les images non projetées](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [Pour spécifier une projection LatLon pour les images dans les informations de projection incorporées...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## Pour spécifier une projection LatLon pour les images non projetées {#section-26554eefe645481faba68396fa13756a}

1. Ouvrez le [!DNL Terrain Images.cfg] fichier dans l’outil de données et ajoutez une source de calque d’image de terrain comme décrit dans [Pour définir une couche](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)d’image de terrain.

1. Modifiez les paramètres Infos sur la projection à l’aide du tableau de paramètres suivant comme guide :

   | Paramètre | Description |
   |---|---|
   | Lat0 | La latitude du bord supérieur de l&#39;image, en degrés, où 90 est le pôle Nord et -90 est le pôle Sud. |
   | Lat1 | latitude du bord inférieur de l’image. |
   | Lon0 | Longitude du bord gauche de l’image, en degrés, où les nombres positifs sont orientaux et les nombres négatifs sont longitudes ouest. |
   | Lon1 | Longitude du bord droit de l’image. |

1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et en cliquant sur **[!UICONTROL Save]**.

1. Pour enregistrer les modifications apportées localement à l’ordinateur serveur de l’outil de données, dans la [!DNL Server Files Manager]colonne, cliquez avec le bouton droit de la souris sur la coche [!DNL Terrain Images.cfg] dans la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Pour spécifier une projection LatLon pour les images dans les informations de projection incorporées {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. Dans la [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en afficher le contenu. Le [!DNL Terrain Images.cfg] fichier se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom du serveur [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Terrain Images.cfg].

1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le [!DNL Terrain Images.cfg] fichier apparaît dans une fenêtre du Bloc-notes.

1. Modifiez les paramètres Infos sur la projection à l’aide de l’exemple de fragment de fichier suivant comme guide. Veillez à spécifier le type de projection comme indiqué ci-dessous. Pour obtenir la description des paramètres, reportez-vous au tableau Paramètres LatLonProjection de la procédure précédente.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```

