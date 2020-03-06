---
description: Lors de la création d’un calque de point d’élément qui fait référence à un fichier de recherche pour obtenir des données de latitude et de longitude, l’emplacement du point est obtenu en récupérant chaque élément et sa latitude et longitude associées dans le fichier de recherche.
solution: Analytics
title: Définition des calques de points d’élément référençant les fichiers de recherche
topic: Data workbench
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Définition des calques de points d’élément référençant les fichiers de recherche{#defining-element-point-layers-referencing-lookup-files}

Lors de la création d’un calque de point d’élément qui fait référence à un fichier de recherche pour obtenir des données de latitude et de longitude, l’emplacement du point est obtenu en récupérant chaque élément et sa latitude et longitude associées dans le fichier de recherche.

Au lieu d’utiliser un fichier de recherche, vous pouvez utiliser la [!DNL Dynamic Points] fonctionnalité qui incorpore la latitude et la longitude d’un emplacement dans le nom de chaque élément d’une dimension. Voir [Définition De Calques De Point D’Élément À L’Aide De Points](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)Dynamiques.

Pour définir un calque de point d’élément qui fait référence à un fichier de recherche, vous devez créer ou avoir déjà accès aux éléments suivants :

* **Une dimension** définie dans le [!DNL Transformation.cfg] fichier ou un jeu de données de transformation inclut le fichier. Pour plus d’informations sur les fichiers de configuration de transformation, voir le Guide *de configuration des jeux de* données.

* **Fichier** de recherche contenant les données utilisées pour tracer chaque point de données. Ce fichier doit contenir au moins trois colonnes de données pour chaque point de données : la clé, la longitude et la latitude. Pour plus d’informations sur le format requis du fichier de recherche, voir Format [du fichier de recherche de point d’](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121)élément.

* **Fichier** de calque spécifiant l’emplacement du fichier de recherche et identifiant la dimension et la mesure associées, ainsi que les noms des colonnes de clé, de longitude et de latitude dans le fichier de recherche. Pour plus d’informations sur le format requis du fichier de calque, voir Format [du fichier de calque de point d’](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981)élément.

>[!NOTE]
>
>Le [!DNL Zip Points.layer] fichier, fourni avec le [!DNL Geography] profil, est un calque de point d’élément qui identifie le [!DNL Zipcode.dim] fichier, le [!DNL Sessions.metric] [!DNL Zip Points.txt] fichier, le fichier de recherche et les noms des colonnes de clé, de longitude, de latitude et de nom dans le fichier de recherche.

