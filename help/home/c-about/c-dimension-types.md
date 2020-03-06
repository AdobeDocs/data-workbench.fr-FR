---
description: Plusieurs types de dimensions sont disponibles dans le serveur de l’outil de données. Il est donc important de connaître le type de dimension lorsque vous utilisez une dimension pour créer des mesures, des filtres ou des dimensions dérivées.
solution: Analytics
title: Types de dimension
topic: Data workbench
uuid: 07659373-8d9b-473d-8daa-ca8e7ac4afe8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Types de dimension{#dimension-types}

Plusieurs types de dimensions sont disponibles dans le serveur de l’outil de données. Il est donc important de connaître le type de dimension lorsque vous utilisez une dimension pour créer des mesures, des filtres ou des dimensions dérivées.

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
   <td colname="col1"> Comptable </td> 
   <td colname="col2">Type de dimension dans lequel le nombre d’éléments de la dimension peut être compté par le système. Ces dimensions doivent être déduites d’autres dimensions de ce type. Les dimensions dénombrables peuvent entretenir des relations de type parents/enfants. <p>Exemples : Visiteur, Session, Page vue, Réservation et Commande. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simple </td> 
   <td colname="col2">Dimension qui entretient une relation de type "un à plusieurs" avec une dimension dénombrable parent. Une dimension simple peut être considérée comme une propriété d’éléments de sa dimension parente. <p>Exemple : Référent du visiteur est une dimension simple avec un parent de la dimension Visiteur. Chaque visiteur ne peut avoir qu’un seul Référent de visiteur (son premier référent HHTP), mais il est possible que plusieurs visiteurs aient le même référent. Le référent de visiteur est donc une relation de type « un à plusieurs » avec la dimension Visiteur. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numérique </td> 
   <td colname="col2">Une dimension qui a des valeurs numériques ordonnées et une relation de type "un à plusieurs" avec une dimension dénombrable parent. Une dimension numérique peut être considérée comme une propriété numérique d’éléments de sa dimension parent. Les dimensions numériques sont généralement utilisées pour définir des mesures de « somme ». <p>Exemple : la dimension numérique « Recettes de la session » définit les recettes, en dollars, de chaque session. Un seul montant de recettes est affecté à chaque session, mais un nombre indéfini de sessions peut comporter les mêmes recettes. Par conséquent, « Recettes de la session » constitue une relation de type « un à plusieurs » avec Session. A metric “Revenue” might be defined as <span class="filepath"> sum(Session_Revenue, Session)</span>, giving the total amount of revenue for the selected Sessions. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plusieurs à plusieurs </td> 
   <td colname="col2">Dimension qui entretient une relation de type "plusieurs à plusieurs" avec une dimension dénombrable parent. Une relation de type « plusieurs à plusieurs » peut être considérée comme représentant un « ensemble » de valeurs pour chaque élément de sa dimension parent. Une dimension de type « plusieurs à plusieurs » équivaut à une dimension dénombrable (anonyme) avec son parent et une dimension simple avec un parent de la dimension dénombrable anonyme. <p>Exemple : la dimension de type plusieurs à plusieurs « Expression de recherche » comporte un parent de Session. Chaque session peut utiliser zéro ou plusieurs expressions de recherche et une expression de recherche peut être utilisée dans un nombre indéfini de sessions. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2">Dimension qui entretient une relation de type "un à un" avec une dimension dénombrable parent. Les noms des éléments de la dimension Denormal peuvent véhiculer des informations sur les éléments correspondants de la dimension parente. La dimension Denormal peut être considérée comme le point de stockage d’une valeur de chaîne arbitraire pour chaque élément du parent. Les dimensions Denormal peuvent être utilisées avec la fonctionnalité d’exportation de segments d’Insight Server pour produire des informations détaillées sur un sous-ensemble ou « segment » d’une dimension dénombrable. Elles peuvent, en outre, être référencées dans des formules de mesure et des visualisations de feuille de calcul ou encore être utilisées (avec certaines restrictions) pour définir des filtres. <p>Exemple : la dimension Denormal « Adresse de courriel » comporte un parent de Visiteur. Chaque visiteur possède une adresse de courriel et chaque élément de la dimension « Adresse de courriel » est associé à un seul visiteur. Même si deux visiteurs possèdent la même adresse de courriel, celle-ci constitue deux éléments distincts de la dimension « Adresse de courriel ». Une exportation de segment peut faire référence à la dimension « Adresse de courriel » pour générer l’adresse de courriel de chaque visiteur d’un segment. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure </td> 
   <td colname="col2">Dimension qui vous permet de créer un ensemble de dimensions temporelles locales absolues ou périodiques (telles que Jour, Jour de la semaine, Heure, Heure du jour, etc.) en fonction d’un champ d’horodatage que vous spécifiez. Lorsque vous définissez ces dimensions, vous pouvez également faire débuter la semaine par un autre jour que le lundi en indiquant le paramètre Premier jour de la semaine. <p>Exemple : la dimension temporelle Session comporte un parent de Session. Par conséquent, la dimension définit un ensemble de dimensions temporelles (Jour, Jour de la semaine, Heure, Heure du jour, Mois et Semaine) dont les éléments correspondent aux moments auxquels ont débuté les sessions des visiteurs sur le site. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dérivé </td> 
   <td colname="col2">Les dimensions dérivées, plutôt que d’être définies dans la configuration du jeu de données en fonction des données en cours de traitement, sont définies dans le profil en fonction d’autres dimensions ou mesures. Bon nombre de dimensions dérivées sont créées automatiquement afin de générer différents types de visualisations. <p>Par exemple, lorsqu’un utilisateur construit un site ou une carte de processus, Insight Server crée silencieusement une dimension "Préfixe". D’autres dimensions (c’est le cas, par exemple, des dimensions temporelles de création de rapports) sont définies par des fichiers dans le répertoire Dimensions d’un profil. </p></td> 
  </tr> 
 </tbody> 
</table>

