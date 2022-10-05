---
description: Une dimension Denormal entretient une relation un-à-un avec sa dimension dénombrable parent.
title: Dimensions non normalisées
uuid: f172fbce-e967-41ce-9958-9062561ecbcc
exl-id: 0c4fad38-bc7c-4b63-98ec-c9121e576a36
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 2%

---

# Dimensions non normalisées{#denormal-dimensions}

{{eol}}

Une dimension Denormal entretient une relation un-à-un avec sa dimension dénombrable parent.

Vous pouvez définir une dimension Denormal chaque fois que la dimension souhaitée contient un élément unique pour chaque élément de son parent. Par exemple : [!DNL EMail Address] est une dimension Denormal avec un parent de Visiteur. Chaque visiteur possède une adresse électronique et chaque élément de la dimension Adresse électronique est l’adresse électronique d’un seul visiteur. Même si deux visiteurs possèdent la même adresse électronique, les adresses sont des éléments distincts de la dimension Adresse électronique .

Vous pouvez utiliser des dimensions normalisées dans n’importe quelle visualisation de tableau, dans les tableaux détaillés ou pour créer des filtres. En outre, vous pouvez utiliser des dimensions standard avec la fonctionnalité d’exportation de segments du serveur Data Workbench pour exporter des valeurs de champs (comme [!DNL Tracking ID] ou [!DNL EMail Address]) qui ont beaucoup de valeurs. Puisque toutes les données de segment que vous souhaitez exporter doivent être définies comme une dimension dans le profil, vous devez créer une dimension Denormal qui stocke les chaînes brutes des données du champ.

>[!NOTE]
>
>Lors de l’utilisation d’une dimension Denormal dans un tableau ou une autre visualisation qui exige une dimension normale, une dimension Denormal dérivée est créée automatiquement. La dimension dénormalisée dérivée a une relation de un à plusieurs avec la dimension parent.

Pour plus d’informations sur la visualisation des tableaux détaillés et les filtres, reportez-vous au chapitre Visualisations de l’analyse de la section *Guide de l’utilisateur de Data Workbench*. Pour plus d’informations sur l’exportation de segments, reportez-vous au chapitre Configuration de l’interface et des fonctionnalités d’analyse dans la section *Guide de l’utilisateur de Data Workbench*.

>[!NOTE]
>
>Les dimensions non normalisées peuvent être très coûteuses en temps de requête et en espace disque. Dimension non normalisée avec parent [!DNL Page View]et une chaîne d’entrée moyenne de 50 octets peut ajouter 25 Go de données aux tampons dans un jeu de données standard volumineux, équivalent à environ 13 dimensions de page vue simples ou numériques, ou environ 125 dimensions de niveau session. N’ajoutez jamais de dimension Denormal à un jeu de données sans une évaluation attentive de l’impact sur les performances.

Les dimensions non normalisées sont définies par les paramètres suivants :

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
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> La valeur associée à la dimension parent (Parent). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Éléments normalisés </td> 
   <td colname="col2"> Paramètre d’optimisation des performances qui spécifie le nombre d’éléments de dimension dont les noms doivent être stockés en mémoire système. Si vous définissez ce paramètre sur une valeur supérieure, une dimension Denormal utilise plus de RAM, mais les requêtes sont plus rapides. La valeur par défaut est 16383. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opération </td> 
   <td colname="col2"> <p>Les opérations disponibles sont les suivantes : </p> <p> 
     <ul id="ul_CCDC45838A3941BD949B6D21EA0492B3"> 
      <li id="li_F33898192A82437692B5C15684EFCF64"> PREMIER NONBLANK : La première valeur d’entrée non vide est utilisée, qu’elle provienne ou non de la première entrée de journal. If <span class="wintitle"> Entrée</span> est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. </li> 
      <li id="li_4ADD0A368BB74B64AD29126C8E7B333F"> PREMIÈRE LIGNE : La valeur de la première entrée de journal associée à l’élément de dimension parent est utilisée, même si l’entrée est vide. If <span class="wintitle"> Entrée</span> est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. Si cette valeur est vide ou non numérique, ou si l’entrée de journal appropriée ne répond pas à la condition de la dimension, aucune valeur n’est utilisée. </li> 
      <li id="li_C93CA22ADA634F21A6488BB3BEE7CB23"> LAST NONBLANK : La dernière valeur d’entrée non vide est utilisée, qu’elle provienne ou non de la dernière entrée de journal. If <span class="wintitle"> Entrée</span> est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. </li> 
      <li id="li_2FFE585521B14FE5ABBF66AAC47F22C4"> DERNIÈRE LIGNE : La valeur de la dernière entrée de journal associée à l’élément de dimension parent est utilisée, même si l’entrée est vide. If <span class="wintitle"> Entrée</span> est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. Si cette valeur est vide ou non numérique, ou si l’entrée de journal appropriée ne répond pas à la condition de la dimension, aucune valeur n’est utilisée. </li> 
     </ul> </p> <p> <p>Remarque : Si l’opération ne donne aucune valeur, une valeur vide ("") est utilisée. </p> </p> <p> Vous devez spécifier une opération pour vous assurer que la dimension est définie comme prévu. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> Nom de la dimension parent. Toute dimension dénombrable peut être une dimension parente. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

La dimension Denormal affichée dans cet exemple prend toutes les données du champ x-trackingid en entrée et les inclut dans une dimension nommée Identifiant visiteur. Pour un segment de visiteurs que vous avez créé, vous pouvez exporter les données de la dimension Identifiant visiteur (ainsi que toute autre dimension définie).

![](assets/cfg_Transformation_Dim_Denormal.png)
