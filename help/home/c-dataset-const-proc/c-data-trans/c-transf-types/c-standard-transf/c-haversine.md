---
description: En mathématiques, la formule haversine est une équation qui donne des distances circulaires entre deux points sur une sphère identifiée à partir de leurs longitudes et latitudes.
solution: Analytics
title: Haversine
topic: Data workbench
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Haversine{#haversine}

En mathématiques, la formule haversine est une équation qui donne des distances circulaires entre deux points sur une sphère identifiée à partir de leurs longitudes et latitudes.

Comme la formule, la [!DNL Haversine] transformation nécessite deux ensembles de [!DNL Latitude] et [!DNL Longitude] paramètres, en utilisant ces quatre entrées pour calculer la distance réelle à travers la Terre entre deux emplacements.

Cette distance peut être représentée par des kilomètres ou des kilomètres en changeant le drapeau &quot;En kilomètres&quot; de faux à vrai.

![](assets/cfg_TransformationType_Haversine.png)

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d’application de cette transformation. |  |
| Champ Latitude 1 | La latitude du point 1. |  |
| Champ Latitude 2 | La latitude du point 2. |  |
| Champ Longitude 1 | Longitude du point 1. |  |
| Champ Longitude 2 | Longitude du point 2. |  |
| Sortie | Une fois calculé, le [!DNL Output] champ contient des distances entre les points désignés comme éléments dans une dimension. |  |

Par exemple, si vous codez en Lat1, Lon1 dans la latitude et la longitude de de leur magasin et que vous utilisez une recherche par IP longue et longue pour leurs clients, les distances à parcourir jusqu’à un magasin auprès duquel la plupart des clients achètent ou viennent peuvent être déterminées.

>[!NOTE]
>
>Si vous souhaitez identifier les distances pour d’autres emplacements, chaque emplacement individuel doit disposer de ses propres champs de liste et de lien.

