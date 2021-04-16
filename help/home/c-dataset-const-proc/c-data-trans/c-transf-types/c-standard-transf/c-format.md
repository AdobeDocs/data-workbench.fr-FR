---
description: La transformation Format utilise un ensemble d’entrées et de formats pour créer une sortie correspondant à la structure donnée.
title: Format
uuid: c596902e-21bc-4ce6-9ca4-7ca86dfc0a6c
exl-id: 842b502e-cd16-45b3-ada8-6f2d899f1d54
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 3%

---

# Format{#format}

La transformation Format utilise un ensemble d’entrées et de formats pour créer une sortie correspondant à la structure donnée.

La transformation fonctionne sur des chaînes simples ou des vecteurs de chaînes et produit une sortie en appliquant le format donné à chaque valeur d’entrée jusqu’à ce que toutes les valeurs d’entrée aient été transformées.

<table id="table_3953C993167248AA9A47964A51C4AB5D"> 
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
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez entrer n'importe quel nom ici. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions d'application de cette transformation. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Format </td> 
   <td colname="col2"> <p>Chaîne de formatage utilisée pour spécifier l’aspect de la sortie. </p> <p> %1% fait référence à une valeur du premier vecteur d'entrée, %2% à une valeur du second vecteur d'entrée, etc. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrées </td> 
   <td colname="col2"> <p>Champs contenant des chaînes simples ou des vecteurs de chaîne. Dans le cas des vecteurs de chaîne en tant qu’entrées, la sortie sera également un vecteur de chaîne résultant de l’application du paramètre <span class="wintitle"> Format</span> à chaque ensemble de valeurs d’entrée. </p> <p> <p>Remarque :  La numérotation des entrées début à 0, mais la numérotation des valeurs de substitution de format s’début à %1 %. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sortie </td> 
   <td colname="col2"> Nom du champ créé pour contenir les résultats de la transformation. Si les entrées sont des vecteurs de chaîne, la longueur du vecteur de chaîne de sortie est celle du vecteur d’entrée le plus long. Si certains des vecteurs de chaîne d’entrée sont de longueur plus courte, des chaînes vides sont utilisées pour leur position dans la chaîne de format jusqu’à ce que la longueur du vecteur de sortie soit atteinte. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

Dans cet exemple, deux vecteurs, l’un un vecteur de chaînes représentant les catégories de produits et l’autre un vecteur de chaînes correspondant représentant la quantité de chaque produit acheté, sont transformés en un vecteur unique de longueur équivalente qui se présente comme suit : Produit %1%, Quantité %2%.

![](assets/cfg_TransformationType_Format.png)

Si les vecteurs d&#39;entrée contenaient des catégories de produit de (683, 918) et des quantités de (10, 4), le résultat serait un vecteur de sortie final contenant les deux chaînes suivantes : (&quot;Produit 683, Quantité 10&quot;, &quot;Produit 918, Quantité 4&quot;).
