---
description: Les outils de données fournissent un ensemble de transformations qui permet au serveur des outils de données d’incorporer des données de recherche dans le jeu de données.
solution: Analytics
title: Intégration des données de recherche
topic: Data workbench
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Intégration des données de recherche{#integrating-lookup-data}

Les outils de données fournissent un ensemble de transformations qui permet au serveur des outils de données d’incorporer des données de recherche dans le jeu de données.

Les données de recherche sont des données externes provenant de bases de données d’entreprise ou de fichiers de recherche que vous pouvez combiner avec des données d’événement pour créer le jeu de données. En général, vous utilisez des données de recherche pour augmenter les données d’événement provenant de vos sources de journal. D’un point de vue conceptuel, vous pouvez envisager d’utiliser des données de recherche pour remplir les enregistrements de données d’événement avec des colonnes d’informations supplémentaires.

Lorsque vous utilisez des données de recherche, vous les chargez dans une table de recherche résidente de la mémoire. Une colonne du tableau doit contenir une clé commune qui existe également dans les enregistrements de données d’événement. Les données de la table de recherche peuvent être chargées à partir d&#39;un fichier plat ou d&#39;une source de données ODBC. Les données de recherche peuvent être intégrées dans le jeu de données pendant la phase de traitement du journal ou de transformation du processus de construction du jeu de données.

Pour incorporer des données de recherche, vous devez d’abord générer un fichier de recherche ou disposer des informations nécessaires pour accéder à une base de données SQL, puis définir une ou plusieurs des transformations suivantes dans les fichiers de configuration du jeu de données pour le traitement et la transformation des journaux.

**Pour intégrer des données de recherche dans le jeu de données**

1. Générez votre fichier de recherche. Voir [Renseigner le tableau](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8)de recherche.
1. Définissez l’un des types de transformations suivants dans le paramètre Transformations du fichier de configuration de jeu de données approprié :

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>Notez que la [!DNL ODBCLookup] transformation ne fonctionne que lorsqu’elle est définie dans le [!DNL Transformation.cfg] fichier ou dans un [!DNL Transformation Dataset Include] fichier.

