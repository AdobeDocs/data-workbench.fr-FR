---
description: Une dimension Denormal entretient une relation de type "un à un" avec sa dimension dénombrable parent.
solution: Analytics
title: Dimensions Denormal
topic: Data workbench
uuid: f172fbce-e967-41ce-9958-9062561ecbcc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensions Denormal{#denormal-dimensions}

Une dimension Denormal entretient une relation de type &quot;un à un&quot; avec sa dimension dénombrable parent.

Vous définiriez une dimension Denormal chaque fois que la dimension souhaitée contient un élément unique pour chaque élément de son parent. Par exemple, [!DNL EMail Address] est une dimension Denormal avec un parent de Visiteur. Chaque visiteur possède une adresse électronique et chaque élément de la dimension Adresse électronique est l’adresse électronique d’un visiteur unique. Même si deux visiteurs ont la même adresse électronique, les adresses sont des éléments distincts de la dimension Adresse électronique.

Vous pouvez utiliser des dimensions Denormal dans n’importe quelle visualisation de tableau, dans des tableaux détaillés ou pour créer des filtres. En outre, vous pouvez utiliser des dimensions Denormal avec la fonctionnalité d’exportation de segments du serveur de l’outil de données pour exporter des valeurs de champs (par exemple [!DNL Tracking ID] ou [!DNL EMail Address]) qui ont beaucoup de valeurs. Toute donnée de segment que vous souhaitez exporter doit être définie comme une dimension dans le profil. Vous devez donc créer une dimension dénormalisée qui stocke les chaînes brutes des données du champ.

>[!NOTE]
>
>Lors de l’utilisation d’une dimension dénormalisée dans un tableau ou d’une autre visualisation qui attend une dimension normale, une dimension dénormalisée dérivée est créée automatiquement. La dimension dénormalisée dérivée a une relation de type &quot;un à plusieurs&quot; avec la dimension parent.

Pour plus d’informations sur la visualisation des tableaux détaillés et les filtres, voir le chapitre Visualisations d’analyse du Guide *de l’utilisateur des outils de* données. Pour plus d’informations sur l’exportation de segments, voir le chapitre Configuration de l’interface et des fonctionnalités d’analyse du Guide *de l’utilisateur des outils de* données.

>[!NOTE]
>
>Les dimensions Denormal peuvent être très coûteuses en temps de requête et en espace disque. Une dimension Denormal avec parent [!DNL Page View]et une chaîne d’entrée moyenne de 50 octets peuvent ajouter 25 Go de données aux tampons dans un jeu de données standard volumineux, équivalant à environ 13 dimensions de page vue simples ou numériques, ou environ 125 dimensions de niveau de session. N’ajoutez jamais de dimension dénormalisée à un jeu de données sans évaluer soigneusement l’impact sur les performances.

Les dimensions Denormal sont définies par les paramètres suivants :

<table id="table_532AD791E39B4CF296FFA1C33FB8302E"> 
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
   <td colname="col2"> Nom descriptif de la dimension tel qu’il apparaît dans les outils de données. Le nom de la dimension ne peut pas inclure de trait d’union (-). </td> 
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
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> Valeur associée à la dimension parent (Parent). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Éléments normalisés </td> 
   <td colname="col2"> Paramètre de réglage des performances spécifiant le nombre d’éléments de dimension dont les noms doivent être stockés dans la mémoire système. La définition de ce paramètre sur une valeur plus élevée entraîne l’utilisation d’une dimension Denormal plus de RAM, mais entraîne des requêtes plus rapides. La valeur par défaut est 16383. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opération </td> 
   <td colname="col2"> <p>Les opérations disponibles sont les suivantes : </p> <p> 
     <ul id="ul_CCDC45838A3941BD949B6D21EA0492B3"> 
      <li id="li_F33898192A82437692B5C15684EFCF64"> PREMIER NONBLANC : La première valeur d’entrée non vide est utilisée, qu’elle provienne ou non de la première entrée de journal. Si <span class="wintitle"> Input</span> est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. </li> 
      <li id="li_4ADD0A368BB74B64AD29126C8E7B333F"> PREMIÈRE LIGNE : La valeur de la première entrée de journal associée à l’élément de dimension parent est utilisée, même si l’entrée est vide. Si <span class="wintitle"> Input</span> est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. Si cette valeur est vide ou non, ou si l’entrée de journal appropriée ne répond pas à la condition de la dimension, aucune valeur n’est utilisée. </li> 
      <li id="li_C93CA22ADA634F21A6488BB3BEE7CB23"> DERNIER NONBLANK : La dernière valeur d’entrée non vide est utilisée, qu’elle provienne ou non de la dernière entrée du journal. Si <span class="wintitle"> Input</span> est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. </li> 
      <li id="li_2FFE585521B14FE5ABBF66AAC47F22C4"> DERNIÈRE LIGNE : La valeur de la dernière entrée de journal associée à l’élément de dimension parent est utilisée, même si l’entrée est vide. Si <span class="wintitle"> Input</span> est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. Si cette valeur est vide ou non, ou si l’entrée de journal appropriée ne répond pas à la condition de la dimension, aucune valeur n’est utilisée. </li> 
     </ul> </p> <p> <p>Remarque :  Si l’option Opération ne donne aucune valeur, une valeur vide ("") est utilisée. </p> </p> <p> Vous devez spécifier une opération pour vous assurer que la dimension est définie comme prévu. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> Nom de la dimension parent. Toute dimension dénombrable peut être une dimension parent. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

La dimension Denormal illustrée dans cet exemple utilise toutes les données du champ x-trackingid comme entrée et les inclut dans une dimension nommée Identifiant visiteur. Pour un segment de visiteurs que vous avez créé, vous pouvez exporter les données dans la dimension Identifiant visiteur (ainsi que toute autre dimension définie).

![](assets/cfg_Transformation_Dim_Denormal.png)

