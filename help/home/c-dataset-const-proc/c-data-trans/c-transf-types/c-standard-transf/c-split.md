---
description: La transformation Scinder divise une chaîne en un vecteur de sous-chaînes basé sur un caractère de délimiteur donné.
title: Split
uuid: 116e8465-8fb1-41eb-9a28-412cee54ab87
exl-id: ea85b095-1306-4938-906d-35d421db6c98
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 3%

---

# Split{#split}

La transformation Scinder divise une chaîne en un vecteur de sous-chaînes basé sur un caractère de délimiteur donné.

[!DNL Split] est particulièrement utile pour extraire des valeurs individuelles d’une collection de valeurs associées à une seule valeur de nom de requête URI.

<table id="table_C97DA4E45DA844FAB8D61AABA22FF809"> 
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
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez entrer n'importe quel nom ici. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions d'application de cette transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Délimiteur </td> 
   <td colname="col2"> <p>Chaîne utilisée pour séparer la chaîne d’entrée en sous-chaînes. Doit être un caractère de longueur unique. </p> <p> Si vous maintenez la touche Ctrl enfoncée et cliquez avec le bouton droit dans le paramètre Délimiteur, un menu Insertion s'affiche. Ce menu contient une liste de caractères spéciaux qui sont souvent utilisés comme délimiteurs. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> Nom du champ dont la valeur est fractionnée pour créer le vecteur de chaîne de sortie. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sortie </td> 
   <td colname="col2"> Nom du champ de sortie. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Prenons l&#39;exemple d&#39;un site Web sur lequel les produits achetés par un client sont répertoriés comme faisant partie de la valeur cs-uri-requête lorsque la page de confirmation associée à un achat réussi est consultée. Voici un exemple de chaîne de ce type :

* /checkout/confirmed.asp?prod_selected=B57481,C46355,Z97123

Le champ cs-uri-stem permet de déterminer si la page demandée par l&#39;entrée de journal est la page de confirmation. Les codes des produits que le client a achetés sont répertoriés en tant que valeurs séparées par des virgules du nom prod_selected dans la requête cs-uri. La transformation [!DNL Split] peut être utilisée pour extraire ces informations en divisant les codes de produit par la virgule si la valeur de cs-uri-stem correspond à la valeur spécifiée dans la condition [!DNL String Match]. Voir [Correspondance de chaîne](../../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f). La transformation suivante décrit en détail la solution à ce problème.

![](assets/cfg_TransformationType_Split.png)

Dans ce cas, le champ de sortie est x-products, qui serait utilisé pour créer la dimension étendue souhaitée qui mappe les produits achetés aux sessions au cours desquelles l’achat a été effectué.
