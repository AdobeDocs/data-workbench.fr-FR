---
description: La transformation Math permet l’utilisation d’opérations arithmétiques sur les champs dans les entrées de journal.
title: Math
uuid: 9e1a5950-8fb2-48e9-b9a1-82c5165fba10
exl-id: d8b9cacd-67d1-447c-94dd-7028aa371dfa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 7%

---

# Mathématiques{#math}

{{eol}}

La transformation Math permet l’utilisation d’opérations arithmétiques sur les champs dans les entrées de journal.

Les opérations peuvent inclure des entiers décimaux et des constantes à virgule flottante.

<table id="table_FDF3DDF1960E43E391A67C9DC2A0E302"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Les conditions dans lesquelles cette transformation est appliquée. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expression </td> 
   <td colname="col2"> <p>Expression arithmétique qui décrit le calcul à effectuer. </p> <p> Vous pouvez utiliser l’une des opérations et fonctions répertoriées ci-dessous et vous pouvez incorporer des noms de champ dans l’expression : </p> <p> Opérations 
     <ul id="ul_DB5915FADA0A41A3B11F1F48615F40A9">
      <li id="li_CA9EA97243F04760A81313C17EE057B3"> Addition (+) </li>
      <li id="li_908A272EBA2340098C20F22AA8D9ED26"> Soustraction (-) </li>
      <li id="li_C62257FF3AAB436D9148BBEA441621D7"> Multiplication (*) </li>
      <li id="li_B5A9EAB3E49D4CB9A297172199F23542"> Division (/) </li>
      <li id="li_D2D2B51DB2C8412A9B6F9D5F3CC03F8A"> Reste (%) </li>
      <li id="li_07E7E368FFD2437A852B785E159848E5"> Elévation à une puissance (^) </li>
     </ul></p> <p>Fonctions 
     <ul id="ul_E335AE8D684340AA998C4A2633FFDEE1">
      <li id="li_E036FF0B5DF244DDBFEDA9BFEDC62251"> sgn(x). Renvoie 1 si x est positif, 0 si x est zéro ou -1 si x est négatif. </li>
      <li id="li_90CD8899DDC14778A95930C2768C82BC"> abs(x). Renvoie la valeur absolue de x. </li>
      <li id="li_F4AF23F343F74BD88B7166B1C2BB065E"> floor(x). Renvoie le plus grand entier inférieur ou égal à x. </li>
      <li id="li_A31379A3659240C3A629BFAF19A6DDF1"> round(x). Renvoie l’entier le plus proche de x. </li>
      <li id="li_9C0A0F3A4A304026B543F2A64B98B922"> log(b,x). Renvoie le logarithme de x base b. </li>
      <li id="li_124D62C2CA5A42CBBCC5DB18FAA8920E"> min(x, y,..). Renvoie le plus petit de tous ses arguments. </li>
      <li id="li_3B7B9FC1C0BF4E7688F9F49130B97B7F"> max(x,y,...). Renvoie le plus grand de tous ses arguments. </li>
     </ul></p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sortie </td> 
   <td colname="col2"> Nom du champ contenant le résultat de l’opération arithmétique. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

Dans cet exemple, qui utilise les champs de données collectés à partir du trafic du site web, un nouveau champ nommé x-page-duration est calculé en soustrayant x-last-pv-timestamp de x-timestamp, puis en ajoutant 1. La sortie n’est calculée que si le champ défini par l’utilisateur x-last-pv-timestamp (qui représente l’horodatage de la dernière page vue d’un visiteur), est renseigné ou &quot;pas vide&quot;.

![](assets/cfg_TransformationType_Math.png)

Pour plus d’informations sur la variable [!DNL Not Empty] condition, voir [Conditions](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).
