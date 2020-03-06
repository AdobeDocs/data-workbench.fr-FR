---
description: Evaluez un arbre de décision à l’aide de l’option Arborescence de régression avec les nouvelles fonctionnalités d’échantillonnage et de visualisation.
title: Option d'arborescence de régression pour l'arbre de décision
uuid: 1e3b5d5f-1fed-49c9-9a4d-d220c28075ac
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Option d&#39;arborescence de régression pour l&#39;arbre de décision{#regression-tree-option-for-decision-tree}

Evaluez un arbre de décision à l’aide de l’option Arborescence de régression avec les nouvelles fonctionnalités d’échantillonnage et de visualisation.

Evaluez un arbre de décision à l’aide de l’option Arborescence de régression en cliquant avec le bouton droit de la souris et en sélectionnant Options > Arborescence **de** régression dans une visualisation Arborescence de décision.

**Mise à jour du créateur** d&#39;arbre de décision : Le nouvel algorithme a été introduit pour la création d’un arbre [de](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/decision-trees/c-decision-trees.html)décision. Il traite des données plus générales et fournit une visualisation plus informative pour améliorer la précision de la prédiction.

**Amélioration du module** d’échantillonnage des données : Un modèle d’échantillonnage adaptatif mis à jour permet à l’arbre de décision et à la note de propension d’obtenir des résultats plus précis.

![](assets/CART-RegressionTreeOptions.jpg)

Le vert et le rouge indiquent vrai ou faux. La saturation de la couleur (rouge profond ou rouge clair, par exemple) est utilisée pour indiquer la probabilité. Par exemple, un noeud avec un rouge profond a une probabilité très élevée d’être faux, tandis qu’un noeud avec un rouge clair a une probabilité plus faible d’être faux. Un noeud vert profond a une très forte probabilité d&#39;être vrai.

Tous les arbres de décision ont des largeurs de branches variables pour indiquer le niveau de trafic pour cette branche de l&#39;arbre.

Dans une visualisation Arborescence de décision, cliquez avec le bouton droit de la souris et sélectionnez Options > Arborescence **de** régression. Lorsque cette option est sélectionnée, des paramètres supplémentaires sont fournis :

<table id="table_39E025A3E0B549B4BEDCE0D30A499211"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Régression, paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Utiliser chaque fonction une seule fois</b> </p> </td> 
   <td colname="col2"> <p>La sélection de cette option n’utilise pas une fonctionnalité plus d’une fois (comme l’arborescence de décision d’origine). Par conséquent, si vous avez cinq entrées, l’arborescence ne sera pas supérieure à cinq niveaux et la structure de l’arborescence ressemblera à celle d’un arbre de décision (mais un peu plus compliquée). Cette option rend la création de l'arbre rapide en utilisant chaque fonction une seule fois (comme un arbre de décision d'origine). L’utilisation de cette fonctionnalité est un paramètre par défaut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Paramètre de niveau de l'arborescence de régression </b> </p> </td> 
   <td colname="col2"> <p>Cette option contrôle la complexité de l’arborescence de régression. Selon vos données, vous devrez peut-être créer une arborescence <i>fine</i> (avec une structure complexe avec plus de noeuds) pour obtenir une classification d’arborescence plus significative. Si vous avez beaucoup de données, alors un arbre relativement <i>grossier</i> (moins compliqué avec moins de noeuds d'arbre) pourrait bien fonctionner. </p> <p> <p>Remarque : <i>Typical</i> est le paramètre par défaut. Dans certains cas extrêmes, le paramètre <i>Typical</i> ne fonctionne pas aussi bien que le paramètre <i>grossier</i> ou <i>fin</i> peut offrir une meilleure vue des données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Très bien</i>: Arborescence la plus complexe avec les niveaux de création de rapports les plus granulaires et la plupart des branches. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Standard</i>: Niveau moyen de granularité et de branches. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Gros</i>: Arborescence la moins complexe avec le moins de catégories définies et le moins de branches définies. </p> </td> 
  </tr> 
 </tbody> 
</table>

