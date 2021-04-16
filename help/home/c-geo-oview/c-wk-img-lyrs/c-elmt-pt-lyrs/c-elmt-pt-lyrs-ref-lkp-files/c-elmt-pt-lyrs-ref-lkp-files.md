---
description: Lors de la création d’un calque de point d’élément qui fait référence à un fichier de recherche pour obtenir des données de latitude et de longitude, l’emplacement du point est obtenu en récupérant chaque élément et sa latitude et longitude associées dans le fichier de recherche.
title: Définir des calques de point d’élément faisant référence à des fichiers Lookup
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 4%

---

# Définir des calques de point d’élément faisant référence à des fichiers Lookup{#defining-element-point-layers-referencing-lookup-files}

Lors de la création d’un calque de point d’élément qui fait référence à un fichier de recherche pour obtenir des données de latitude et de longitude, l’emplacement du point est obtenu en récupérant chaque élément et sa latitude et longitude associées dans le fichier de recherche.

Au lieu d&#39;utiliser un fichier de recherche, vous pouvez utiliser la fonctionnalité [!DNL Dynamic Points], qui incorpore la latitude et la longitude d&#39;un emplacement dans le nom de chaque élément d&#39;une dimension. Voir [Définition de calques de points d’élément à l’aide de points dynamiques](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

Pour définir un calque de point d’élément qui fait référence à un fichier de recherche, vous devez créer ou avoir déjà accès aux éléments suivants :

* **Une** dimension définie dans le  [!DNL Transformation.cfg] fichier ou un jeu de données de transformation inclut le fichier. Pour plus d&#39;informations sur les fichiers de configuration de transformation, consultez le *Guide de configuration des jeux de données*.

* **Un** fichier de recherche contenant les données utilisées pour tracer chaque point de données. Ce fichier doit contenir au moins trois colonnes de données pour chaque point de données : la clé, la longitude et la latitude. Pour plus d’informations sur le format requis du fichier de recherche, voir [Format du fichier de recherche de point d’élément](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **Un** fichier de calque qui spécifie l’emplacement du fichier de recherche et identifie la dimension et la mesure associées, ainsi que les noms des colonnes de clé, de longitude et de latitude dans le fichier de recherche. Pour plus d’informations sur le format requis du fichier de calque, voir [Format de fichier de couche de point d’élément](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>Le fichier [!DNL Zip Points.layer], fourni avec le profil [!DNL Geography], est une couche de point d’élément qui identifie le fichier [!DNL Zipcode.dim], le fichier [!DNL Sessions.metric], le fichier de recherche [!DNL Zip Points.txt] et les noms des colonnes de clé, de longitude, de latitude et de nom dans le fichier de recherche.
