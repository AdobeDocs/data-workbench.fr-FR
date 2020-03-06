---
description: Une dimension de type "plusieurs à plusieurs" entretient une relation de type "plusieurs à plusieurs" avec sa dimension dénombrable parent.
solution: Analytics
title: Dimensions multiples
topic: Data workbench
uuid: 42c909e8-1228-4210-9406-ffc0d92372fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensions multiples{#many-to-many-dimensions}

Une dimension de type &quot;plusieurs à plusieurs&quot; entretient une relation de type &quot;plusieurs à plusieurs&quot; avec sa dimension dénombrable parent.

Vous pouvez considérer une dimension de type &quot;plusieurs à plusieurs&quot; comme une représentation d’un ensemble de valeurs pour chaque élément de sa dimension parent. Par exemple, la dimension &quot;plusieurs à plusieurs&quot; Expression de recherche est une dimension de niveau Session (elle a un parent de Session). Il représente l’ensemble des expressions de recherche associées à chaque session dans la dimension Session. Une seule phrase de recherche peut être utilisée dans n’importe quel nombre de sessions et une seule session peut inclure zéro ou plusieurs phrases de recherche. Par conséquent, la dimension Expression de recherche entretient une relation de type &quot;plusieurs à plusieurs&quot; avec la dimension Session.

Plusieurs à plusieurs dimensions sont définies par les paramètres suivants :

<table id="table_A6D495008DFF4DD28A3ECD718D775E54"> 
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
   <td colname="col2"> Nom descriptif de la dimension tel qu’il apparaît à l’utilisateur dans les outils de données. Le nom de la dimension ne peut pas inclure de trait d’union (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la dimension étendue. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions dans lesquelles la relation entre le parent et la valeur du champ d’entrée doit être créée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Masqué </td> 
   <td colname="col2"> Détermine si la dimension apparaît dans l’interface de l’outil de données. Par défaut, ce paramètre est défini sur false. Si, par exemple, la dimension doit être utilisée uniquement comme base d’une mesure, vous pouvez définir ce paramètre sur true pour masquer la dimension de l’affichage des outils de données. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> <p>Valeur associée à la dimension parent (Parent). Si ce champ est un vecteur de chaînes, chaque élément du vecteur a sa propre relation avec le parent. </p> <p> <p>Remarque :  Si la valeur d’entrée de chaque entrée de journal pour un élément de la dimension parent est vide, aucun élément de la dimension de type "plusieurs à plusieurs" ne se rapportera à cet élément de la dimension parent. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> Nom de la dimension parent. Toute dimension dénombrable peut être une dimension parent. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Cet exemple illustre la définition d’une dimension de type &quot;plusieurs à plusieurs&quot; à l’aide des données d’événement collectées à partir du trafic du site Web. Cette dimension &quot;plusieurs à plusieurs&quot;, nommée &quot;Produit sélectionné&quot;, associe les sessions aux produits achetés par le visiteur au cours de cette session. Le champ x-products contient un vecteur de valeurs, dont chacun est associé à une page vue qui, à son tour, est associée à une session.

![](assets/cfg_Transformation_Dim_ManytoMany.png)

En créant une telle transformation, vous pouvez créer une visualisation dans les outils de données qui décrit la relation entre la dimension de produit sélectionnée et le nombre de sessions impliquant chacun des produits.
