---
description: La condition Comparer et la condition Plage exigent que vous spécifiiez le type de comparaison à effectuer pour la condition.
title: Types de test pour les opérations de test
uuid: dc0433dd-a35e-472e-8975-f58347512c11
exl-id: 8abed46e-e76d-47c0-bbe9-cf98cf2d61e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 2%

---

# Types de test pour les opérations de test{#test-types-for-test-operations}

{{eol}}

La condition Comparer et la condition Plage exigent que vous spécifiiez le type de comparaison à effectuer pour la condition.

Le tableau suivant décrit les types disponibles ( [!DNL LEXICAL], [!DNL NUMERIC], et [!DNL DATETIME]).

<table id="table_1B3AD8BDF0414D0AB8EE0E6D1B53E2CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de test </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Remarques </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> INTEGER</span> </p> </td> 
   <td colname="col2"> <p>Commence par transformer le champ d’entrée en un entier. Si cela n’est pas possible, une valeur de zéro est utilisée. Le test renvoie true uniquement si la valeur d’entrée entière résultante est supérieure ou égale à la valeur minimale spécifiée et inférieure ou égale à la valeur maximale spécifiée. </p> </td> 
   <td colname="col3"> <p>Si l’un des champs min. ou max. n’est pas renseigné, le système utilise la valeur min. ou max. appropriée disponible pour les entiers signés 64 bits. </p> <p> Si la valeur minimale ou maximale spécifiée dans la condition n’est pas analysée correctement en valeur entière, le système remplace zéro et n’arrête pas le traitement du jeu de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> DATETIME</span> </p> </td> 
   <td colname="col2"> <p>Commence par transformer le champ de saisie en date. Si le champ de saisie ne peut pas être transformé en date valide, le test de condition renvoie false (faux). Si le champ peut être transformé en date, le test renvoie true uniquement si la date d’entrée est postérieure ou égale à la date minimale spécifiée et à la date maximale spécifiée. </p> </td> 
   <td colname="col3"> <p>Si les dates min. et max. ne sont pas valides, le jeu de données n’est pas construit. </p> <p> Si les dates min. ou max. ne sont pas fournies, le système remplace de manière appropriée la date min. (1er janvier 1600) ou la date max. (au cours du 24ème siècle). </p> <p> Adobe recommande d’utiliser l’un des formats suivants pour <span class="wintitle"> DATETIME</span>: </p> 
    <ul id="ul_44F469CC5D974382AF70D7B1975CF077"> 
     <li id="li_DB5FD4AFD6B34436ACD7C13282F64956"> 1er janvier 2013 HH:MM:SS EDT </li> 
     <li id="li_307580C3F97D495BB16F1212DB38CE37"> 1er janvier 2013 HH:MM:SS GMT </li> 
    </ul> <p> Le fuseau horaire est défini par défaut sur GMT s’il n’est pas spécifié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LEXIQUE</span> </p> </td> 
   <td colname="col2"> <p>Renvoie "true" uniquement si le champ d’entrée est lexiquement supérieur ou égal à la chaîne spécifiée comme minimum et inférieur ou égal à la chaîne spécifiée dans la valeur maximale. </p> </td> 
   <td colname="col3"> <p>La comparaison lexicale utilise la valeur ASCII des caractères dans les chaînes passant de la gauche à la droite pour comparer les caractères. Pour le premier caractère qui ne correspond pas, celui dont la valeur ASCII est la plus grande est considéré comme étant le plus grand des deux. Dans le cas où une chaîne est plus courte que l’autre, mais que tous les caractères jusqu’à ce moment-là ont été identiques, la chaîne la plus longue est considérée comme la plus grande des deux. Si les chaînes correspondent à des caractères et ont exactement la même longueur, elles sont considérées comme lexiquement équivalentes. </p> </td> 
  </tr> 
 </tbody> 
</table>
