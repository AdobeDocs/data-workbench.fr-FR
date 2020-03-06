---
description: Tableau présentant les conventions applicables lors de la création de transformations.
solution: Analytics
title: Conventions pour la construction de transformations
topic: Data workbench
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Conventions pour la construction de transformations{#conventions-for-constructing-transformations}

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
   <td colname="col2"> <p>Les transformations d’un fichier de configuration de jeu de données sont appliquées de manière séquentielle aux entrées du journal (c’est-à-dire dans l’ordre dans lequel elles sont répertoriées dans le fichier de configuration). Par conséquent, les transformations doivent être répertoriées dans l’ordre dans lequel leurs sorties sont utilisées comme entrées pour d’autres transformations. Plus précisément, si la sortie d’une transformation est utilisée comme entrée pour une autre transformation, il est important que cette première transformation soit répertoriée avant la dernière transformation dans les fichiers de configuration du jeu de données. Sinon, le serveur de l’outil de données génère une erreur. </p> <p> Les étapes de traitement permettent d’organiser les transformations définies dans plusieurs jeux de données, y compris les fichiers. Pour tous les fichiers du jeu de données, y compris les fichiers associés à une étape de traitement particulière, les transformations sont organisées en fonction de leurs entrées et sorties. En outre, si plusieurs jeux de données incluent des fichiers dans une sortie d’étape dans le même champ à la suite d’une transformation, le serveur de l’outil de données génère une erreur. </p> <p> Pour plus d’informations sur les étapes, voir Fichier <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> de configuration</a>de traitement du <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md"> journal, Fichier</a>de configuration de transformation et Fichier <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> de configuration de jeu de données</a>Inclure les fichiers. </p> <p>Une carte <span class="wintitle"> de dépendance des</span> conversions peut indiquer comment un champ est modifié par une série de transformations. Voir Outils <a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md"> de configuration</a>des jeux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Noms de sortie </td> 
   <td colname="col2"> La plupart des transformations spécifient un champ de sortie. Si la sortie est un champ étendu défini par l’utilisateur, le nom de ce champ doit commencer par "x-". Les noms des champs de sortie ne peuvent pas contenir d’espaces ni de caractères spéciaux. Les noms des champs étendus peuvent être écrits en minuscules, telles que "x-NewCampaignName" ou "x-New-Campaign-Name" pour plus de lisibilité, mais ils sont traités par le logiciel comme étant non sensibles à la casse. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Champs d’entrée </td> 
   <td colname="col2"> <p>Les champs d’entrée se rapportent à l’un des champs de ligne de base ou à un champ créé par l’utilisateur et résultant de la sortie d’une transformation précédente. Si une chaîne constante est nécessaire, une chaîne entre guillemets peut être utilisée à la place d’une ligne de base ou d’un champ créé par l’utilisateur. </p> <p> Pour obtenir la liste de certains champs de données couramment définis que le serveur de l’outil de données peut traiter, voir Champs <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md"> d’enregistrement des données d’</a>événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chaînes simples et vecteurs de chaînes </td> 
   <td colname="col2"> Toutes les transformations opèrent sur des chaînes et/ou des vecteurs de chaînes. Les chaînes simples sont des séquences littérales de caractères. Les vecteurs de chaîne contiennent zéro ou plusieurs chaînes simples dans un ordre spécifique. </td> 
  </tr> 
 </tbody> 
</table>

