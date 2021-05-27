---
description: Le format de projection latitude-longitude (LatLonProjection) du fichier Terrain Images.cfg est défini par quatre paramètres de latitude et de longitude.
title: Projections latitude-longitude
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# Projections latitude-longitude{#latitude-longitude-projections}

Le format de projection latitude-longitude (LatLonProjection) du fichier Terrain Images.cfg est défini par quatre paramètres de latitude et de longitude.

Pour spécifier une LatLonProjection pour les images non projetées (images brutes non projetées et images générales, non projetées), vous pouvez saisir les paramètres de LatLonProjection dans la fenêtre [!DNL Terrain Images.cfg] dans Data Workbench. Voir [Pour spécifier une LatLonProjection pour les images non projetées](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

Pour spécifier une projection LatLon pour les images avec des informations de projection incorporées, vous devez ouvrir le fichier [!DNL Terrain Images.cfg] dans un éditeur de texte tel que Notepad, définir le paramètre Infos de projection sur &quot;LatLonProjection&quot; et ajouter des paramètres pour la projection LatLon. Voir [Pour spécifier une LatLonProjection pour les images dans les informations de projection incorporées...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [Pour spécifier une projection LatLon pour les images non projetées](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [Pour spécifier une projection LatLon pour les images dans les informations de projection incorporées...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## Pour spécifier une projection LatLon pour les images non projetées {#section-26554eefe645481faba68396fa13756a}

1. Ouvrez le fichier [!DNL Terrain Images.cfg] dans Data Workbench et ajoutez une source de couche d’image du terrain comme décrit dans [Pour définir une couche d’image du terrain](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

1. Modifiez les paramètres Informations de projection à l’aide du tableau de paramètres suivant comme guide :

   | Paramètre | Description |
   |---|---|
   | Lat0 | La latitude du bord supérieur de l’image, en degrés, où 90 est le pôle Nord et -90 est le pôle Sud. |
   | Lat1 | Latitude du bord inférieur de l’image. |
   | Lon0 | Longitude du bord gauche de l’image, en degrés, où les nombres positifs sont orientés et les nombres négatifs, longitude ouest. |
   | Lon1 | Longitude du bord droit de l’image. |

1. Enregistrez le fichier en cliquant avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre et en cliquant sur **[!UICONTROL Save]**.

1. Pour enregistrer les modifications apportées localement à la machine du serveur Data Workbench, dans la balise [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Terrain Images.cfg] dans la colonne [!DNL Temp], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

## Pour spécifier une projection LatLon pour les images dans les informations de projection incorporées {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. Dans la balise [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour en visualiser le contenu. Le fichier [!DNL Terrain Images.cfg] se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne nom du serveur pour [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche s’affiche dans la colonne [!DNL Temp] pour [!DNL Terrain Images.cfg].

1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le fichier [!DNL Terrain Images.cfg] apparaît dans une fenêtre du Bloc-notes.

1. Modifiez les paramètres Informations de projection à l’aide de l’exemple de fragment de fichier suivant comme guide. Veillez à spécifier le type de projection comme indiqué ci-dessous. Pour obtenir une description des paramètres, reportez-vous au tableau LatLonProjection Parameters de la procédure précédente.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
