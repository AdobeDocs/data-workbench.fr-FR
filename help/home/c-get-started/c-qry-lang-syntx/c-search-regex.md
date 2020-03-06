---
description: Les outils de données utilisent des expressions régulières (regex) pour les opérations de recherche et de tri.
solution: Analytics
title: Expressions régulières
topic: Data workbench
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Regular expressions{#regular-expressions}

Les outils de données utilisent des expressions régulières (regex) pour les opérations de recherche et de tri.

Dans le **[!UICONTROL Search]** champ, vous pouvez effectuer une recherche en suivant l’instruction &quot;re:&quot; à l’aide d’expressions courantes, par exemple :

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> métacaractère </th> 
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
   <td colname="col2"> <p>Correspond à un ou plusieurs caractères, par exemple : <span class="filepath"> :Z* </span> correspond à "ZZZ". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? (caractère générique) </p> </td> 
   <td colname="col2"> <p>Correspond à 0 ou 1 de l’expression précédente pour forcer une correspondance minimale, par exemple : <span class="filepath"> xy?z </span> correspond à "xy" et "xyz". </p> </td> 
  </tr> 
 </tbody> 
</table>

D’autres expressions régulières courantes peuvent également être utilisées pour créer des chaînes de recherche plus complexes. Les expressions régulières sont utilisées dans tous les champs de recherche Outils de données, y compris les panneaux d’entité de requête.

Voir des informations détaillées dans les expressions [](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions)régulières.