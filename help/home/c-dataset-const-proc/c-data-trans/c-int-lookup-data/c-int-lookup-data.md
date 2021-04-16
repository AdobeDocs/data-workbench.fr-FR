---
description: L’outil de données fournit un ensemble de transformations qui permet au serveur de l’outil de données d’incorporer des données de recherche dans le jeu de données.
title: Intégration des données Lookup
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
exl-id: 150d3aae-4431-488f-8f19-b522637ee935
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 2%

---

# Intégration des données Lookup{#integrating-lookup-data}

L’outil de données fournit un ensemble de transformations qui permet au serveur de l’outil de données d’incorporer des données de recherche dans le jeu de données.

Les données de recherche sont des données externes provenant de bases de données d’entreprise ou de fichiers de recherche que vous pouvez combiner avec des données de événement pour créer le jeu de données. En général, vous utilisez des données de recherche pour augmenter les données de événement provenant de vos sources de journal. Conceptuellement, vous pouvez envisager d&#39;utiliser des données de recherche pour remplir les enregistrements de données de événement avec des colonnes d&#39;informations supplémentaires.

Lorsque vous utilisez des données de recherche, vous les chargez dans une table de recherche résidente de la mémoire. Une colonne de la table doit contenir une clé commune qui existe également dans les enregistrements de données de événement. Les données de la table de choix elle-même peuvent être chargées à partir d&#39;un fichier plat ou d&#39;une source de données ODBC. Les données de recherche peuvent être incorporées dans le jeu de données pendant la phase de traitement du journal ou de transformation du processus de construction du jeu de données.

Pour incorporer des données de recherche, vous devez d&#39;abord générer un fichier de recherche ou disposer des informations nécessaires pour accéder à une base de données SQL, puis définir une ou plusieurs des transformations suivantes dans les fichiers de configuration du jeu de données pour le traitement et la transformation des journaux.

**Pour intégrer des données de recherche dans le jeu de données**

1. Générez votre fichier de recherche. Voir [Renseigner la table de recherche](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8).
1. Définissez l’un des types de transformations suivants dans le paramètre Transformations du fichier de configuration de jeu de données approprié :

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>Notez que la transformation [!DNL ODBCLookup] ne fonctionne que lorsqu&#39;elle est définie dans le fichier [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include].
