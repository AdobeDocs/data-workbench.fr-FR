---
description: Tableau présentant les conventions applicables lors de la création de transformations.
title: Conventions de construction des transformations
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
exl-id: c2552c52-c6d3-4c9f-8359-b5a58bf1a59f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 2%

---

# Conventions de construction des transformations{#conventions-for-constructing-transformations}

{{eol}}

Tableau présentant les conventions applicables lors de la création de transformations.

<table id="table_BEB0F6C416D144B5A2DD3D1A21613B21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Convention </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Exécution séquentielle </td> 
   <td colname="col2"> <p>Les transformations au sein d’un fichier de configuration de jeu de données sont appliquées de manière séquentielle aux entrées du journal (c’est-à-dire dans l’ordre dans lequel elles sont répertoriées dans le fichier de configuration). Par conséquent, les transformations doivent être répertoriées dans l’ordre où leurs sorties sont utilisées comme entrées à d’autres transformations. Plus précisément, si la sortie d’une transformation est utilisée comme entrée d’une autre transformation, il est important que cette première transformation soit répertoriée avant cette dernière dans les fichiers de configuration du jeu de données. Dans le cas contraire, le serveur Data Workbench génère une erreur. </p> <p> Les étapes de traitement permettent de classer les transformations définies dans plusieurs fichiers d’inclusion de jeux de données. Pour tous les fichiers d’inclusion de jeux de données associés à une étape de traitement spécifique, les transformations sont organisées en fonction de leurs entrées et sorties. En outre, si plusieurs jeux de données incluent des fichiers dans des données de sortie d’étape vers le même champ à la suite d’une transformation, le serveur Data Workbench génère une erreur. </p> <p> Pour plus d’informations sur les étapes, voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Fichier de configuration de traitement du journal</a>, <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md"> Fichier de configuration de transformation</a>, et <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Fichiers d’inclusion de jeux de données</a>. </p> <p>A <span class="wintitle"> Carte de dépendance des conversions</span> peut afficher la manière dont un champ est modifié par une série de transformations. Voir <a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md"> Outils de configuration des jeux de données</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Noms de sortie </td> 
   <td colname="col2"> La plupart des transformations spécifient un champ de sortie. Si la sortie est un champ étendu défini par l’utilisateur, le nom de ce champ doit commencer par "x-". Les noms des champs de sortie ne peuvent pas contenir d’espaces ni de caractères spéciaux. Les noms des champs étendus peuvent être écrits en minuscules (par exemple, "x-NewCampaignName" ou "x-New-Campaign-Name") à des fins de lisibilité, mais ils sont traités par le logiciel comme étant insensibles à la casse. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Champs de saisie </td> 
   <td colname="col2"> <p>Les champs de saisie se rapportent à l’un des champs de base ou à un champ créé par l’utilisateur et résultant de la sortie d’une transformation précédente. Si une chaîne constante est nécessaire, une chaîne entre guillemets peut être utilisée à la place d’une ligne de base ou d’un champ créé par l’utilisateur. </p> <p> Pour obtenir la liste de certains des champs de données que le serveur Data Workbench peut traiter couramment, voir <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md"> Champs d’enregistrement des données d’événement</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chaînes simples et vecteurs de chaînes </td> 
   <td colname="col2"> Toutes les transformations opèrent sur des chaînes et/ou des vecteurs de chaînes. Les chaînes simples sont des séquences littérales de caractères. Les vecteurs de chaîne contiennent aucune ou plusieurs chaînes simples dans un ordre spécifique. </td> 
  </tr> 
 </tbody> 
</table>
