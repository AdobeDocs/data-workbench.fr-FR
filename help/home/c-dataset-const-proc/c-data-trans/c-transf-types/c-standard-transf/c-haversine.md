---
description: En mathématiques, la formule de l'aversine est une équation qui donne les distances des cercles entre deux points sur une sphère identifiée à partir de leurs longitudes et latitudes.
title: Haversine
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
exl-id: e700c0a0-1a1a-4c56-bb4f-1deb1b39b059
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# Haversine{#haversine}

En mathématiques, la formule de l&#39;aversine est une équation qui donne les distances des cercles entre deux points sur une sphère identifiée à partir de leurs longitudes et latitudes.

Comme la formule, la transformation [!DNL Haversine] nécessite deux ensembles de paramètres [!DNL Latitude] et [!DNL Longitude], en utilisant ces quatre entrées pour calculer la distance réelle sur Terre entre deux emplacements.

Cette distance peut être représentée sous forme de kilomètres en changeant le drapeau &quot;En Kilomètres&quot; de faux à vrai.

![](assets/cfg_TransformationType_Haversine.png)

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Les conditions dans lesquelles cette transformation est appliquée. |  |
| Champ Latitude 1 | La latitude du point 1. |  |
| Champ Latitude 2 | La latitude du point 2. |  |
| Champ de longitude 1 | Longitude du point 1. |  |
| Champ de longitude 2 | Longitude du point 2. |  |
| Sortie | Une fois calculé, le champ [!DNL Output] contient les distances entre les points désignés comme éléments dans une Dimension. |  |

Par exemple, si vous codez une latitude et une longitude de leur magasin en tant que Lat1 et Lon1 et que vous utilisez une recherche d’adresse IP lat et longue pour leurs clients, les distances d’un magasin que la plupart des clients achètent ou viennent d’eux peuvent être déterminées.

>[!NOTE]
>
>Si vous souhaitez identifier les distances d’autres emplacements, chaque emplacement doit disposer de son propre ensemble de champs lat et lon .
