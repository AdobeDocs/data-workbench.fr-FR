---
description: Le groupement de chaînes de requête permet d'intégrer un grand nombre de champs.
title: Groupement des chaînes de requête
uuid: 7dc5ba71-984f-4899-99d2-f79b57fb616d
exl-id: 4052cf7e-abdf-4e16-9f42-521c4e719786
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%

---

# Groupement des chaînes de requête{#query-string-grouping}

{{eol}}

Le groupement de chaînes de requête permet d&#39;intégrer un grand nombre de champs.

Le groupement de chaînes de requête est spécifique à chaque profil, mais fonctionne bien dans les transformations comme indiqué dans cet exemple :

1. Créez les paires que vous souhaitez regrouper en ajoutant un fichier de configuration personnalisé ( [!DNL E:\...\Dataset\Log Processing\SC Fields.cfg]), puis en ajoutant le type de transformation *BuildNameValuePair* comme paramètre.

   ```
   2 = BuildNameValuePair:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to build)
             Name = string: Custom Events 
             Output = string: x-event-list       
   ```

1. Créez un fichier pour extraire les données condensées dans les champs que vous souhaitez utiliser en ajoutant un fichier de configuration personnalisé ( [!DNL E:\...\Dataset\Transformation\SC Fields Transformation.cfg]), puis en ajoutant le type de transformation *ExtractNameValuePairs* comme paramètre.

   ```
   2 = ExtractNameValuePairs:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Field = string: x-event-list 
         Name = string: Custom Events 
         Output Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to extract) 
             Name = string: Custom Events 
             Output = string: x-event-list   
   ```

## Autres utilisations {#section-cc5d2b0c9e194fc88a5a18a06ef22f5e}

Si vous disposez de nombreux champs avec des evars, des props et des variables personnalisées, vous pouvez, lors du traitement du journal, créer une paire de valeurs de nom pour combiner les champs dans un rapport. Vous pouvez, par exemple, créer des paires nom-valeur dans des champs combinés afin de réduire le nombre de [!DNL tempDB] taille du fichier.

![](assets/query_string_grouping.png)
