---
description: Une dimension multiple-à-multiple entretient une relation multiple-à-multiple avec sa dimension dénombrable parent.
title: Dimensions multiples-à-multiples
uuid: 42c909e8-1228-4210-9406-ffc0d92372fa
exl-id: 02d1a21c-a5b4-4b58-8089-9b9c68a7b1d1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 3%

---

# Dimensions multiples-à-multiples{#many-to-many-dimensions}

{{eol}}

Une dimension multiple-à-multiple entretient une relation multiple-à-multiple avec sa dimension dénombrable parent.

Vous pouvez considérer une dimension de type &quot;plusieurs à plusieurs&quot; comme une représentation d’un ensemble de valeurs pour chaque élément de sa dimension parent. Par exemple, la dimension &quot;plusieurs à plusieurs&quot; Expression de recherche est une dimension de niveau Session (elle comporte un parent de Session). Il représente le jeu d’expressions de recherche associé à chaque session dans la dimension Session . Une seule expression de recherche peut être utilisée dans n’importe quel nombre de sessions et une seule session peut inclure aucune ou plusieurs expressions de recherche. Par conséquent, la dimension Phrase de recherche entretient une relation multiple-à-multiple avec la dimension Session .

Les dimensions multiples à multiples sont définies par les paramètres suivants :

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
   <td colname="col2"> Nom descriptif de la dimension tel qu’il apparaît à l’utilisateur dans Data Workbench. Le nom de la dimension ne peut pas contenir de trait d’union (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la dimension étendue. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions dans lesquelles la relation entre le parent et la valeur du champ de saisie doit être créée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Masqué </td> 
   <td colname="col2"> Détermine si la dimension apparaît dans l’interface de Data Workbench. Par défaut, ce paramètre est défini sur false. Si, par exemple, la dimension doit être utilisée uniquement comme base d’une mesure, vous pouvez définir ce paramètre sur true pour masquer la dimension de l’affichage Data Workbench. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> <p>La valeur associée à la dimension parent (Parent). Si ce champ est un vecteur de chaînes, alors chaque élément du vecteur a sa propre relation avec le parent. </p> <p> <p>Remarque : Si la valeur d’entrée pour chaque entrée de journal pour un élément de la dimension parent est vide, aucun élément de la dimension multiple-à-multiple ne sera associé à cet élément de la dimension parent. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> Nom de la dimension parent. Toute dimension dénombrable peut être une dimension parente. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Cet exemple illustre la définition d’une dimension de type &quot;plusieurs à plusieurs&quot; à l’aide de données d’événement collectées à partir du trafic du site web. Cette dimension multiple-à-multiple, appelée &quot;Produit sélectionné&quot;, associe les sessions aux produits achetés par le visiteur au cours de cette session. Le champ x-products contient un vecteur de valeurs, chacun étant associé à une page vue qui, à son tour, est associée à une session.

![](assets/cfg_Transformation_Dim_ManytoMany.png)

En créant une telle transformation, vous pouvez créer une visualisation dans Data Workbench qui décrit la relation entre la dimension de produit sélectionnée et le nombre de sessions qui impliquent chacun des produits.
