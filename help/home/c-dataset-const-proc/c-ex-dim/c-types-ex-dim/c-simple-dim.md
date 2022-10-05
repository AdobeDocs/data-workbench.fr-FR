---
description: Une dimension simple entretient une relation de type "un à plusieurs" avec sa dimension dénombrable parent.
title: Dimensions simples
uuid: 3bca2354-02c4-4739-a7da-acccdb0efdfd
exl-id: 2acad750-7c48-40f1-8130-ab056ac8bf0d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 1%

---

# Dimensions simples{#simple-dimensions}

{{eol}}

Une dimension simple entretient une relation de type &quot;un à plusieurs&quot; avec sa dimension dénombrable parent.

Une dimension simple est toujours un enfant d’une dimension dénombrable. Vous pouvez considérer une dimension simple comme une représentation d’une propriété des éléments de sa dimension parent. Par exemple, si vous utilisez des données web, vous pouvez définir la dimension Référent du visiteur , qui est une dimension simple avec une dimension parent du visiteur. Il représente le premier référent HTTP pour chaque visiteur dans la dimension Visiteur . Chaque visiteur dans la dimension Visiteur ne comporte qu’un seul référent de visiteur, mais de nombreux visiteurs peuvent avoir le même référent de visiteur. Par conséquent, la dimension Référent du visiteur entretient une relation de type &quot;un à plusieurs&quot; avec la dimension Visiteur .

Les dimensions simples sont définies par les paramètres suivants :

<table id="table_E6F729DFA226459DBFC1776CE8CB81F8"> 
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
   <td colname="col2"> Nom descriptif de la dimension tel qu’il apparaît dans Data Workbench. Le nom de la dimension ne peut pas contenir de trait d’union (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la dimension étendue. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions dans lesquelles la relation entre le Parent et la valeur du champ de saisie doit être créée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Masqué </td> 
   <td colname="col2"> Détermine si la dimension apparaît dans l’interface de Data Workbench. Par défaut, ce paramètre est défini sur false. Si, par exemple, la dimension doit être utilisée uniquement comme base d’une mesure, vous pouvez définir ce paramètre sur true pour masquer la dimension de l’affichage Data Workbench. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> Champ de valeurs associé à la dimension parent (Parent). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chargement de fichier </td> 
   <td colname="col2"> <p>Facultatif. Fichier de valeurs disponibles pour la relation. Vous utilisez un fichier de chargement lorsque l’une des conditions suivantes s’applique : </p> <p> 
     <ul id="ul_056C4A8E46AA479397DC63173C035D5C"> 
      <li id="li_C26EB5A4AB3C4BEB8EB3A217A5A2377E"> Les valeurs ont un ordre de tri spécifique que vous souhaitez conserver dans l’affichage de Data Workbench. Par exemple, vous pouvez créer une dimension Trimestre dont les éléments (trimestres de l’année) s’affichent toujours par ordre chronologique. </li> 
      <li id="li_5D4DF56BC6124D038A7260131B1F3DB3"> Vous souhaitez créer des espaces réservés pour les valeurs qui ne figurent peut-être pas dans les données, mais qui doivent apparaître dans l’affichage de Data Workbench. </li> 
     </ul> </p> <p> Si une valeur n’est pas présente dans le fichier, elle est ajoutée à la fin des valeurs lorsqu’elle est affichée dans Data Workbench. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opération </td> 
   <td colname="col2"> <p>Les opérations disponibles sont les suivantes : </p> <p> 
     <ul id="ul_88AE4279413C42609D8B53EC64B5E913"> 
      <li id="li_DD9623D006844BC28B2AAA8E12AA04E1"> PREMIER NONBLANK : La première valeur d’entrée non vide est utilisée, qu’elle provienne ou non de la première entrée de journal. Si Input est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. </li> 
      <li id="li_0FBE7F0B7B9744D994ECEDAA08F0045C"> PREMIÈRE LIGNE : La valeur de la première entrée de journal associée à l’élément de dimension parent est utilisée, même si l’entrée est vide. Si Input est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. Si cette valeur est vide ou non numérique, ou si l’entrée de journal appropriée ne répond pas à la condition de la dimension, aucune valeur n’est utilisée. </li> 
      <li id="li_C17190BC699D4A099DC5326C07D1044D"> LAST NONBLANK : La dernière valeur d’entrée non vide est utilisée, qu’elle provienne ou non de la dernière entrée de journal. Si Input est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. </li> 
      <li id="li_00BAE86F12004C098F6A455908DB7062"> DERNIÈRE LIGNE : La valeur de la dernière entrée de journal associée à l’élément de dimension parent est utilisée, même si l’entrée est vide. Si Input est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. Si cette valeur est vide ou non numérique, ou si l’entrée de journal appropriée ne répond pas à la condition de la dimension, aucune valeur n’est utilisée. </li> 
     </ul> </p> <p> <p>Remarque : Si l’opération ne donne aucune valeur ou une valeur vide pour une entrée de journal spécifique, l’élément correspondant de la dimension parent sera associé à l’élément "Aucun" de la dimension simple. </p> </p> <p> Vous devez spécifier une opération pour vous assurer que la dimension est définie comme prévu. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> Nom de la dimension parent. Toute dimension dénombrable peut être une dimension parente. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Cet exemple illustre la définition d’une dimension simple à l’aide des données d’événement collectées à partir du trafic du site web et d’un fichier de chargement.

Prenons l’exemple d’un sondage des cookies Scouts filles préférés des visiteurs du site. Une page web capture ce vote et le renvoie au serveur web dans la paire nom-valeur favoritecookie. Un seul vote par visiteur est comptabilisé, mais les visiteurs peuvent changer d&#39;avis et voter à nouveau, le cas échéant. Il s’agit d’une relation de type &quot;un à plusieurs&quot; : un visiteur peut avoir plusieurs votes, mais chaque vote est associé à un seul visiteur. Par conséquent, le parent de la dimension est les visiteurs (une seule voix par visiteur) et l’opération est DERNIÈRE LIGNE (afin qu’ils puissent changer d’avis et voter à nouveau).

Des espaces réservés doivent exister pour tous les types de cookies afin que les types de cookies recevant des votes n’apparaissent pas dans l’affichage de Data Workbench. Pour ces raisons, un fichier de chargement a été défini, qui contient la liste des types de cookies qui peuvent être sélectionnés. Le contenu de ce fichier, enregistré dans un fichier nommé [!DNL cookietypes.txt], ressemble à ce qui suit :

Les trésors animaux

Caramel Delights

Crèmes de pâtisserie au citron

Pièces de beurre d&#39;arachide

Raccourcis

Minces

La dimension finale est définie comme illustré ci-dessous :

![](assets/cfg_Transformation_Dim_Simple.png)
