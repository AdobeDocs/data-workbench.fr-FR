---
description: Le regroupement de chaînes de requête permet d’intégrer un grand nombre de champs ensemble.
title: Groupement des chaînes de requête
uuid: 7dc5ba71-984f-4899-99d2-f79b57fb616d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Groupement des chaînes de requête{#query-string-grouping}

Le regroupement de chaînes de requête permet d’intégrer un grand nombre de champs ensemble.

Le regroupement des chaînes de requête est spécifique à chaque profil, mais fonctionne bien dans les transformations comme indiqué dans cet exemple :

1. Créez les paires que vous souhaitez regrouper en ajoutant un fichier de configuration personnalisé ( [!DNL E:\...\Dataset\Log Processing\SC Fields.cfg]), puis en ajoutant le paramètre Type de transformation *BuildNameValuePair* en tant que paramètre.

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

1. Créez un nouveau fichier pour extraire les données condensées dans les champs que vous souhaitez utiliser en ajoutant un fichier de configuration personnalisé ( [!DNL E:\...\Dataset\Transformation\SC Fields Transformation.cfg]), puis en ajoutant les paires *de valeur* de type de transformationExtractNameValuePairs en tant que paramètre.

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

Si vous disposez de nombreux champs avec des variables evar, prop et variable personnalisées, vous pouvez, au cours du traitement du journal, créer une paire de valeurs de nom pour combiner des champs dans un rapport. Par exemple, vous pouvez créer des paires nom-valeur dans des champs combinés pour réduire la taille du [!DNL tempDB] fichier.

![](assets/query_string_grouping.png)
