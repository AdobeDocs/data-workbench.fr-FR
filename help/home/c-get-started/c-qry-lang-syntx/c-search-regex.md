---
description: Les outils de données utilisent des expressions régulières (regex) pour les opérations de recherche et de tri.
title: Expressions régulières
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
exl-id: bb1be6d8-3b7a-47e4-bb29-4a65de99666b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 3%

---

# Expressions régulières{#regular-expressions}

Les outils de données utilisent des expressions régulières (regex) pour les opérations de recherche et de tri.

Dans le champ **[!UICONTROL Search]**, vous pouvez effectuer une recherche en suivant l&#39;instruction &quot;re:&quot; à l&#39;aide d&#39;expressions courantes, par exemple :

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> métacharactère </th> 
   <th colname="col2" class="entry"> description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>. (point) </p> </td> 
   <td colname="col2"> <p>Correspond à un caractère unique, par exemple : <span class="filepath"> re:x.z </span> correspond à "xyz" ou "xxz". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>* (étoile) </p> </td> 
   <td colname="col2"> <p>Correspond à un ou plusieurs caractères, par exemple : <span class="filepath"> re:Z* </span> correspond à "ZZZ". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? (caractère générique) </p> </td> 
   <td colname="col2"> <p>Correspond à 0 ou 1 de l’expression précédente pour forcer une correspondance minimale, par exemple : <span class="filepath"> xy?z </span> correspond à "xy" et "xyz". </p> </td> 
  </tr> 
 </tbody> 
</table>

D’autres expressions courantes peuvent également être utilisées pour créer des chaînes de recherche plus complexes. Les expressions régulières sont utilisées dans tous les champs de recherche des Data Workbench, y compris les panneaux d&#39;entité de requête.

Voir les informations détaillées à l&#39;adresse [expressions régulières](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions).
