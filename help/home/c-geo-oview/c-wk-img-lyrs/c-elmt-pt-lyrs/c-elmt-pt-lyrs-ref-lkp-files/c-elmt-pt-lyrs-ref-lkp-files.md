---
description: Lors de la création d’une couche de point d’élément qui référence un fichier de recherche pour obtenir des données de latitude et de longitude, l’emplacement du point est obtenu en récupérant chaque élément et sa latitude et longitude associées dans le fichier de recherche.
title: Définir des calques de point d’élément faisant référence à des fichiers Lookup
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 4%

---

# Définir des calques de point d’élément faisant référence à des fichiers Lookup{#defining-element-point-layers-referencing-lookup-files}

{{eol}}

Lors de la création d’une couche de point d’élément qui référence un fichier de recherche pour obtenir des données de latitude et de longitude, l’emplacement du point est obtenu en récupérant chaque élément et sa latitude et longitude associées dans le fichier de recherche.

Au lieu d’utiliser un fichier de recherche, vous pouvez utiliser la variable [!DNL Dynamic Points] qui incorpore la latitude et la longitude d’un emplacement dans le nom de chaque élément d’une dimension. Voir [Définir des calques de point d’élément à l’aide de points dynamiques](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

Pour définir une couche de point d’élément qui fait référence à un fichier de recherche, vous devez créer ou disposer déjà des éléments suivants :

* **Une dimension** défini dans la variable [!DNL Transformation.cfg] d’un fichier ou d’un jeu de données de transformation. Pour plus d’informations sur les fichiers de configuration de transformation, voir *Guide de configuration des jeux de données*.

* **Un fichier de recherche** contenant les données utilisées pour tracer chaque point de données. Ce fichier doit contenir au moins trois colonnes de données pour chaque point de données : la clé, la longitude et la latitude. Pour plus d’informations sur le format requis du fichier de recherche, voir [Format de fichier Lookup de point d’élément](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **Un fichier de calque** qui spécifie l’emplacement du fichier de recherche et identifie la dimension et la mesure connexes, ainsi que les noms des colonnes key, longitude et latitude dans le fichier de recherche. Pour plus d’informations sur le format requis du fichier de calque, voir [Format de fichier de calque de point d’élément](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>Le [!DNL Zip Points.layer] , fourni avec la variable [!DNL Geography] profile est un calque de point d’élément qui identifie [!DNL Zipcode.dim] , [!DNL Sessions.metric] , [!DNL Zip Points.txt] fichier de recherche et les noms des colonnes key, longitude, latitude et nom dans le fichier de recherche.
