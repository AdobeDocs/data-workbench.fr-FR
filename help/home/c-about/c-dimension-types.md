---
description: Plusieurs types de dimensions sont disponibles dans le serveur Data Workbench. Il est donc important de connaître le type de dimension lors de l’utilisation d’une dimension pour créer des mesures, des filtres ou des dimensions dérivées.
title: Types de dimension
uuid: 07659373-8d9b-473d-8daa-ca8e7ac4afe8
exl-id: cbc25504-2c1c-4622-adc1-c9bbac8e12fb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 66%

---

# Types de dimension{#dimension-types}

{{eol}}

Plusieurs types de dimensions sont disponibles dans le serveur Data Workbench. Il est donc important de connaître le type de dimension lors de l’utilisation d’une dimension pour créer des mesures, des filtres ou des dimensions dérivées.

Insight Server peut créer et gérer les types de dimensions suivants :

<table id="table_1A79B6C57ED145B6AA3BB05DD37AAD1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Types de dimension </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> dénombrable </td> 
   <td colname="col2">Type de dimension dans lequel le nombre d’éléments de la dimension peut être comptabilisé par le système. Ces dimensions doivent être déduites d’autres dimensions de ce type. Les dimensions dénombrables peuvent entretenir des relations de type parents/enfants. <p>Exemples : Visiteur, Session, Page vue, Réservation et Commande. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simple </td> 
   <td colname="col2">Dimension qui entretient une relation de type "un à plusieurs" avec une dimension dénombrable parent. Une dimension simple peut être considérée comme une propriété d’éléments de sa dimension parente. <p>Exemple : Référent du visiteur est une dimension simple avec un parent de la dimension Visiteur. Chaque visiteur ne peut avoir qu’un seul Référent de visiteur (son premier référent HHTP), mais il est possible que plusieurs visiteurs aient le même référent. Le référent de visiteur est donc une relation de type « un à plusieurs » avec la dimension Visiteur. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numérique </td> 
   <td colname="col2">Dimension qui contient des valeurs numériques classées et une relation de type "un à plusieurs" avec une dimension dénombrable parent. Une dimension numérique peut être considérée comme une propriété numérique d’éléments de sa dimension parent. Les dimensions numériques sont généralement utilisées pour définir des mesures de « somme ». <p>Exemple : la dimension numérique « Recettes de la session » définit les recettes, en dollars, de chaque session. Un seul montant de recettes est affecté à chaque session, mais un nombre indéfini de sessions peut comporter les mêmes recettes. Par conséquent, « Recettes de la session » constitue une relation de type « un à plusieurs » avec Session. Une mesure "Recettes" peut être définie comme <span class="filepath"> sum(Session_Revenue, Session)</span>, indiquant le montant total des recettes pour les sessions sélectionnées. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Multiple-à-multiple </td> 
   <td colname="col2">Dimension qui entretient une relation de type "plusieurs à plusieurs" avec une dimension dénombrable parent. Une relation de type « plusieurs à plusieurs » peut être considérée comme représentant un « ensemble » de valeurs pour chaque élément de sa dimension parent. Une dimension de type « plusieurs à plusieurs » équivaut à une dimension dénombrable (anonyme) avec son parent et une dimension simple avec un parent de la dimension dénombrable anonyme. <p>Exemple : la dimension de type plusieurs à plusieurs « Expression de recherche » comporte un parent de Session. Chaque session peut utiliser zéro ou plusieurs expressions de recherche et une expression de recherche peut être utilisée dans un nombre indéfini de sessions. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2">Dimension qui entretient une relation un-à-un avec une dimension dénombrable parent. Les noms des éléments de la dimension Denormal peuvent véhiculer des informations sur les éléments correspondants de la dimension parente. La dimension Denormal peut être considérée comme le point de stockage d’une valeur de chaîne arbitraire pour chaque élément du parent. Les dimensions Denormal peuvent être utilisées avec la fonctionnalité d’exportation de segments d’Insight Server pour produire des informations détaillées sur un sous-ensemble ou « segment » d’une dimension dénombrable. Elles peuvent, en outre, être référencées dans des formules de mesure et des visualisations de feuille de calcul ou encore être utilisées (avec certaines restrictions) pour définir des filtres. <p>Exemple : la dimension Denormal « Adresse de courriel » comporte un parent de Visiteur. Chaque visiteur possède une adresse de courriel et chaque élément de la dimension « Adresse de courriel » est associé à un seul visiteur. Même si deux visiteurs possèdent la même adresse de courriel, celle-ci constitue deux éléments distincts de la dimension « Adresse de courriel ». Une exportation de segment peut faire référence à la dimension « Adresse de courriel » pour générer l’adresse de courriel de chaque visiteur d’un segment. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure </td> 
   <td colname="col2">Dimension qui vous permet de créer un ensemble de dimensions temporelles locales absolues ou périodiques (telles que Jour, Jour de la semaine, Heure, Heure du jour, etc.) en fonction d’un champ d’horodatage que vous spécifiez. Lorsque vous définissez ces dimensions, vous pouvez également faire débuter la semaine par un autre jour que le lundi en indiquant le paramètre Premier jour de la semaine. <p>Exemple : la dimension temporelle Session comporte un parent de Session. Par conséquent, la dimension définit un ensemble de dimensions temporelles (Jour, Jour de la semaine, Heure, Heure du jour, Mois et Semaine) dont les éléments correspondent aux moments auxquels ont débuté les sessions des visiteurs sur le site. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dérivé </td> 
   <td colname="col2">Les dimensions dérivées, plutôt que d’être définies dans la configuration du jeu de données en fonction des données en cours de traitement, sont définies dans le profil en fonction d’autres dimensions ou mesures. Bon nombre de dimensions dérivées sont créées automatiquement afin de générer différents types de visualisations. <p>Par exemple, lorsqu’un utilisateur crée un site ou une cartographie des processus, Insight Server crée de manière silencieuse une dimension "Préfixe". D’autres dimensions (c’est le cas, par exemple, des dimensions temporelles de création de rapports) sont définies par des fichiers dans le répertoire Dimensions d’un profil. </p></td> 
  </tr> 
 </tbody> 
</table>
