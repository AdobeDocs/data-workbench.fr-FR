---
description: En mathématiques, la formule de l'aversine est une équation qui donne des distances de cercle entre deux points sur une sphère identifiée à partir de leurs longitudes et latitudes.
title: Haversine
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
exl-id: e700c0a0-1a1a-4c56-bb4f-1deb1b39b059
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# Haversine{#haversine}

En mathématiques, la formule de l&#39;aversine est une équation qui donne des distances de cercle entre deux points sur une sphère identifiée à partir de leurs longitudes et latitudes.

Comme la formule, la transformation [!DNL Haversine] requiert deux ensembles de paramètres [!DNL Latitude] et [!DNL Longitude], en utilisant ces quatre entrées pour calculer la distance réelle entre deux emplacements sur la Terre.

Cette distance peut être représentée par des kilomètres ou des kilomètres en changeant le drapeau &quot;En kilomètres&quot; de faux à vrai.

![](assets/cfg_TransformationType_Haversine.png)

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez entrer n&#39;importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d&#39;application de cette transformation. |  |
| Champ Latitude 1 | La latitude du point 1. |  |
| Champ Latitude 2 | La latitude du point 2. |  |
| Champ Longitude 1 | Longitude du point 1. |  |
| Champ Longitude 2 | Longitude du point 2. |  |
| Sortie | Une fois calculé, le champ [!DNL Output] contient les distances entre les points désignés comme éléments dans une Dimension. |  |

Par exemple, si vous codez en latitude et longitude leur magasin en Lat1, Lon1 et que vous utilisez une recherche d’adresse IP longue et longue pour leurs clients, les distances d’accès à un magasin à partir duquel la plupart des clients achètent ou viennent peuvent être déterminées.

>[!NOTE]
>
>Si vous souhaitez identifier les distances pour d’autres emplacements, chaque emplacement doit disposer de son propre ensemble de champs lat et lon.
