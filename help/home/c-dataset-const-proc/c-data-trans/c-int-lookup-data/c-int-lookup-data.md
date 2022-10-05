---
description: Data Workbench fournit un ensemble de transformations qui permet au serveur Data Workbench d’incorporer des données de recherche dans le jeu de données.
title: Intégration des données Lookup
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
exl-id: 150d3aae-4431-488f-8f19-b522637ee935
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 2%

---

# Intégration des données Lookup{#integrating-lookup-data}

{{eol}}

Data Workbench fournit un ensemble de transformations qui permet au serveur Data Workbench d’incorporer des données de recherche dans le jeu de données.

Les données de recherche sont des données externes de bases de données d’entreprise ou de fichiers de recherche que vous pouvez combiner avec des données d’événement pour créer le jeu de données. En règle générale, vous utilisez les données de recherche pour augmenter les données d’événement provenant de vos sources de journal. Sur le plan conceptuel, vous pouvez envisager d’utiliser des données de recherche pour remplir les enregistrements de données d’événement avec des colonnes d’informations supplémentaires.

Lorsque vous utilisez des données de recherche, vous les chargez dans une table de recherche résidente de la mémoire. Une colonne du tableau doit contenir une clé commune qui existe également dans les enregistrements de données d’événement. Les données de la table de recherche elle-même peuvent être chargées à partir d’un fichier plat ou d’une source de données ODBC. Les données de recherche peuvent être intégrées au jeu de données lors de la phase de traitement ou de transformation du journal du processus de construction du jeu de données.

Pour incorporer des données de recherche, vous devez d’abord générer un fichier de recherche ou disposer des informations nécessaires pour accéder à une base de données SQL, puis définir une ou plusieurs des transformations suivantes dans les fichiers de configuration du jeu de données pour le traitement et la transformation des journaux.

**Pour intégrer des données de recherche dans le jeu de données**

1. Générez votre fichier de recherche. Voir [Remplissage du tableau Lookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8).
1. Définissez l’un des types de transformations suivants dans le paramètre Transformations du fichier de configuration du jeu de données approprié :

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>Notez que la variable [!DNL ODBCLookup] La transformation ne fonctionne que lorsqu’elle est définie dans la variable [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include] fichier .
