---
description: Une dimension numérique se compose d’éléments numériques ordonnés et a une relation de type "un à plusieurs" avec sa dimension dénombrable parent.
solution: Analytics
title: Dimensions numériques
topic: Data workbench
uuid: 19fab770-1535-41b2-bad1-811eba5f3575
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensions numériques{#numeric-dimensions}

Une dimension numérique se compose d’éléments numériques ordonnés et a une relation de type &quot;un à plusieurs&quot; avec sa dimension dénombrable parent.

Vous pouvez considérer une dimension numérique comme une représentation des propriétés numériques des éléments de la dimension parent. Par exemple, si vous travaillez avec des données Web, vous pouvez définir la dimension numérique Recettes de la session, qui définit une quantité de recettes, en dollars, pour chaque session de la dimension Session. Chaque session comporte un seul montant de recettes associées, mais plusieurs sessions peuvent avoir le même montant de recettes associées. Par conséquent, la dimension Recettes de la session entretient une relation de type &quot;un à plusieurs&quot; avec la dimension Session.

Les dimensions numériques sont souvent utilisées pour définir des mesures qui additionnent des valeurs, comptabilisent les occurrences d’une condition ou recherchent une valeur minimale ou maximale. Par exemple, une mesure nommée &quot;Recettes&quot; peut être définie à l’aide de la dimension Recettes de la session : sum(Session_Revenue, Session). Définie de cette manière, la mesure Recettes indique le montant total des recettes pour les sessions sélectionnées.

Les dimensions numériques ne peuvent pas être parents d’autres dimensions.

Les dimensions numériques sont définies par les paramètres suivants :

<table id="table_15B849DD0BFC4D57AD6CF28898901324"> 
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
   <td colname="col1"> Valeurs du clip </td> 
   <td colname="col2"> True ou false. Indique si la valeur d’entrée (après l’opération) doit être coupée entre les valeurs Min et Max. Si l’option Valeurs d’élément est définie sur true, la valeur est tronquée dans cette plage. Si la valeur de l’élément est false, aucune valeur n’est renvoyée pour l’élément de la dimension parent. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la dimension étendue. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions dans lesquelles le champ de saisie contribue à la création de la dimension numérique. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Taille fixe </td> 
   <td colname="col2"> True ou false. Contrôle le nombre d’éléments d’une dimension (cardinalité). Si la valeur est true, tous les éléments de Min. à Max. sont inclus dans la dimension. Si la valeur est false, la taille de la dimension augmente à mesure que des valeurs sont ajoutées. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Masqué </td> 
   <td colname="col2"> Détermine si la dimension apparaît dans l’interface de l’outil de données. Par défaut, ce paramètre est défini sur false. Si, par exemple, la dimension doit être utilisée uniquement comme base d’une mesure, vous pouvez définir ce paramètre sur true pour masquer la dimension de l’affichage des outils de données. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> <p>Valeur à utiliser avec l’opération spécifiée ou la valeur d’entrée pour laquelle vous souhaitez comptabiliser les occurrences. </p> <p> Si ce champ est un vecteur de chaînes, l’évaluation se produit pour chaque élément du vecteur. Ainsi, par exemple, un vecteur de longueur 3 et une opération de COUNT ajoutent 3 au nombre. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> min </td> 
   <td colname="col2"> Limite inférieure du résultat de la dimension finale. </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Max </td> 
   <td colname="col2"> Limite supérieure du résultat de la dimension finale. </td> 
   <td colname="col3"> 1e6 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Décalage </td> 
   <td colname="col2"> Voir Echelle dans ce tableau. </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opération </td> 
   <td colname="col2"> <p>Les opérations disponibles sont les suivantes : </p> <p> 
     <ul id="ul_E04733E5E8824A2BAAB90D9356078D99"> 
      <li id="li_CAEE9167D45540BEAC538345F250B509"> NOMBRE : Le nombre total de valeurs non vides dans le champ <span class="wintitle"> Entrée</span> pour toutes les entrées du journal qui respectent la condition de la dimension est utilisé. Si le champ <span class="wintitle"> Entrée</span> est un champ vectoriel, le nombre total de valeurs non vides dans chaque entrée du journal est comptabilisé. </li> 
      <li id="li_64A4D671E78642BD9A9334F8098450B9"> PREMIER NONBLANC : La première valeur d’entrée non vide est utilisée, qu’elle provienne ou non de la première entrée de journal. Si <span class="wintitle"> Input</span> est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. Si la valeur n’est pas un nombre, aucune valeur n’est utilisée. </li> 
      <li id="li_C967964729BD4A638FF78D8883CE513F"> PREMIÈRE LIGNE : La valeur de la première entrée de journal associée à l’élément de dimension parent est utilisée, même si l’entrée est vide. Si <span class="wintitle"> Input</span> est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. Si cette valeur est vide ou non, ou si l’entrée de journal appropriée ne répond pas à la condition de la dimension, aucune valeur n’est utilisée. </li> 
      <li id="li_74171B17F480478B8547E1A361B22DA4"> DERNIER NONBLANK : La dernière valeur d’entrée non vide est utilisée, qu’elle provienne ou non de la dernière entrée du journal. Si <span class="wintitle"> Input</span> est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. Si la valeur n’est pas un nombre, aucune valeur n’est utilisée. </li> 
      <li id="li_1253ECF507BD4BBF97CBB2FA12915045"> DERNIÈRE LIGNE : La valeur de la dernière entrée de journal associée à l’élément de dimension parent est utilisée, même si l’entrée est vide. Si <span class="wintitle"> Input</span> est un champ vectoriel, la première ligne du vecteur de l’entrée de journal appropriée est utilisée. Si cette valeur est vide ou non, ou si l’entrée de journal appropriée ne répond pas à la condition de la dimension, aucune valeur n’est utilisée. </li> 
      <li id="li_20819E3944544F98853D6A02814F47B2"> SUM : Le total de toutes les valeurs numériques du champ <span class="wintitle"> Entrée</span> sur toutes les entrées du journal qui respectent la condition de la dimension est utilisé. S’il n’existe pas d’entrées de journal ou si aucune valeur numérique n’est trouvée, la valeur numérique 0 est utilisée. </li> 
      <li id="li_086C2E57604B4645A9203A984C6F9A04">MIN ou MAX : La valeur numérique minimale ou maximale trouvée dans le champ <span class="wintitle"> Entrée</span> pour toutes les entrées du journal qui respectent la condition de la dimension est utilisée. S’il n’existe aucune entrée de journal ou aucune valeur numérique, aucune valeur n’est utilisée. </li> 
     </ul> </p> <p> <p>Remarque :  Vous devez spécifier une opération pour vous assurer que la dimension est définie comme prévu. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> Nom de la dimension parent. Toute dimension dénombrable peut être une dimension parent. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Echelle </td> 
   <td colname="col2"> <p>Pour obtenir la valeur ordinale de la dimension, le résultat de l’opération est transformé comme suit : </p> <p> (échelle * entrée) + décalage </p> </td> 
   <td colname="col3"> 1.0 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Si [!DNL Operation] ne renvoie aucune valeur ou [!DNL Clip Values] est false et que la valeur n’est pas comprise entre [!DNL Min] et [!DNL Max], aucun élément de la dimension numérique n’est lié à l’élément de la dimension parent.

Cet exemple illustre la définition d’une dimension numérique à l’aide des données d’événement collectées à partir du trafic du site Web. Cette dimension numérique, appelée &quot;Compteur d’affichage d’annonce&quot;, compte le nombre de fois où le visiteur voit une publicité au cours d’une session donnée. L’hypothèse est que toutes les ressources de publication sont demandées au serveur Web avec ad= dans le cadre de la requête cs-uri-query. Dans cet exemple, le nombre de fois (NOMBRE) où le visiteur est présenté avec une publicité est la valeur de l’intérêt, et non la valeur réelle dans le champ.

![](assets/cfg_Transformation_Dim_Numeric.png)

