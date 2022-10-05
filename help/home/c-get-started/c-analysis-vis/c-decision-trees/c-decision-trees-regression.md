---
description: Évaluez un arbre de décision à l’aide de l’option Arborescence de régression avec de nouvelles fonctionnalités d’échantillonnage et de visualisation.
title: Option d’arbre de régression pour l’arbre de décision
uuid: 1e3b5d5f-1fed-49c9-9a4d-d220c28075ac
exl-id: e5f8d525-1530-4169-b246-cdaf30e984c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 3%

---

# Option d’arbre de régression pour l’arbre de décision{#regression-tree-option-for-decision-tree}

{{eol}}

Évaluez un arbre de décision à l’aide de l’option Arborescence de régression avec de nouvelles fonctionnalités d’échantillonnage et de visualisation.

Évaluez un arbre de décision à l’aide de l’option Arborescence de régression en cliquant avec le bouton droit de la souris et en sélectionnant Options > **Arborescence de régression** dans une visualisation Arborescence de décision.

**Créateur d’arbre de décision mis à jour**: Le nouvel algorithme a été introduit pour la création d’un [Arborescence de décision](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/decision-trees/c-decision-trees.html). Il gère des données plus générales et fournit une visualisation plus informative pour améliorer la précision de la prédiction.

**Amélioration du module d’échantillonnage de données**: Un modèle d’échantillonnage adaptatif mis à jour permet à l’arbre de décision et au score de propension d’obtenir des résultats plus précis.

![](assets/CART-RegressionTreeOptions.jpg)

Le vert et le rouge indiquent vrai ou faux. La saturation des couleurs (rouge profond ou rouge clair, par exemple) est utilisée pour indiquer la probabilité. Par exemple, un noeud dont la probabilité est très élevée a une probabilité très élevée d’être faux, tandis qu’un noeud dont la probabilité est faible est fausse. Un noeud avec un vert profond a une très forte probabilité d’être vrai.

Tous les arbres de décision ont des largeurs de branche variables pour indiquer le niveau de trafic de cette branche de l’arborescence.

Dans une visualisation Arborescence de décision, cliquez avec le bouton droit de la souris et sélectionnez Options > **Arborescence de régression**. Lorsque cette option est sélectionnée, des paramètres supplémentaires sont fournis :

<table id="table_39E025A3E0B549B4BEDCE0D30A499211"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre de régression </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Utiliser chaque fonction une seule fois</b> </p> </td> 
   <td colname="col2"> <p>La sélection de cette option n’utilise pas une fonction plusieurs fois (comme l’arbre de décision d’origine). Par conséquent, si vous disposez de cinq entrées, l’arborescence ne sera pas supérieure à cinq niveaux et la structure de l’arborescence ressemblera à un arbre de décision (mais un peu plus complexe). Cette option rend la création de l’arborescence rapide en n’utilisant chaque fonction qu’une seule fois (comme un arbre de décision d’origine). L’utilisation de cette fonctionnalité est un paramètre par défaut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Paramètre de niveau d’arborescence de régression </b> </p> </td> 
   <td colname="col2"> <p>Cette option contrôle la complexité de l’arbre de régression. Selon vos données, vous devrez peut-être créer une <i>Fine</i> arborescence (avec une structure complexe avec plus de noeuds) pour obtenir une classification d’arborescence plus significative. Si vous disposez de nombreuses données, une variable <i>Gros</i> arborescence (moins compliquée avec moins de noeuds d’arborescence) peut fonctionner correctement. </p> <p> <p>Remarque : <i>Typique</i> est le paramètre par défaut. Dans certains cas extrêmes, la variable <i>Typique</i> ne fonctionne pas également et la variable <i>Gros</i> ou <i>Fine</i> peut fournir une meilleure vue des données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Fine</i>: Arborescence la plus complexe avec les niveaux de rapports les plus granulaires et la plupart des branches. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Typique</i>: Niveau moyen de granularité et de branches. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Gros</i>: Arborescence la moins complexe avec le moins de catégories définies et le moins de branches. </p> </td> 
  </tr> 
 </tbody> 
</table>
