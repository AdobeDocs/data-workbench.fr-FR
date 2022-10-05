---
description: La transformation Fusion prend les valeurs du champ d’entrée (généralement un vecteur de chaînes), les combine en une seule chaîne séparée par le délimiteur donné et place la chaîne obtenue dans le champ de sortie donné.
title: Merge
uuid: 9ca2ab22-d854-47b0-8189-f563c1e83d1c
exl-id: 75fa824b-f68d-4ec4-a75d-0f742a7bb1ba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 5%

---

# Fusion{#merge}

{{eol}}

La transformation Fusion prend les valeurs du champ d’entrée (généralement un vecteur de chaînes), les combine en une seule chaîne séparée par le délimiteur donné et place la chaîne obtenue dans le champ de sortie donné.

<table id="table_2458E008C9A14B31A774E6819D07E9BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Les conditions dans lesquelles cette transformation est appliquée. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Par défaut </td> 
   <td colname="col2"> La valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Délimiteur </td> 
   <td colname="col2"> <p>Chaîne utilisée pour séparer les éléments individuels du vecteur de chaîne d’entrée dans la chaîne de sortie unique. </p> <p> Si vous maintenez la touche Ctrl enfoncée et cliquez avec le bouton droit dans le paramètre Délimiteur, une <span class="wintitle"> Insérer</span> s’affiche. Ce menu contient une liste de caractères spéciaux, souvent utilisés comme délimiteurs. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> Un vecteur de valeurs string qui sont combinées pour former la chaîne de sortie. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sortie </td> 
   <td colname="col2"> Nom de la chaîne de sortie. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

Dans cet exemple, un vecteur d’entrée de chaînes est supposé contenir un ensemble de produits sélectionnés pour un achat. Ces produits sont placés dans une seule chaîne de sortie et sont séparés par &quot;::&quot; (deux deux points).

![](assets/cfg_TransformationType_Merge.png)

Ainsi, si le champ d’entrée x-products contenait les valeurs de chaîne B57481, C46355 et Z97123, la chaîne de sortie x-show-products résultante serait B57481 ::C46355::Z97123.
