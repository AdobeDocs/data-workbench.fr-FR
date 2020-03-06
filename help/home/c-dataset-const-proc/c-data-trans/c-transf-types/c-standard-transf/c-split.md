---
description: La transformation Fractionner sépare une chaîne en un vecteur de sous-chaînes basé sur un caractère de délimiteur donné.
solution: Analytics
title: Fractionner
topic: Data workbench
uuid: 116e8465-8fb1-41eb-9a28-412cee54ab87
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Split{#split}

La transformation Fractionner sépare une chaîne en un vecteur de sous-chaînes basé sur un caractère de délimiteur donné.

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
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions d’application de cette transformation. </td> 
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

Prenons l&#39;exemple d&#39;un site Web sur lequel les produits achetés par un client sont répertoriés comme faisant partie de la valeur cs-uri-query lorsque la page de confirmation associée à un achat réussi est consultée. Voici un exemple de chaîne de ce type :

* /checkout/confirmed.asp?prod_selected=B57481,C46355,Z97123

Le champ cs-uri-tige permet de déterminer si la page demandée par l&#39;entrée du journal est la page de confirmation. Les codes des produits que le client a achetés sont répertoriés comme valeurs séparées par des virgules du nom prod_selected dans la requête cs-uri-query. La [!DNL Split] transformation peut être utilisée pour extraire ces informations en divisant les codes de produit par la virgule si la valeur de cs-uri-stem correspond à la valeur spécifiée dans la [!DNL String Match] condition. Voir Correspondance [de chaîne](../../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f). La transformation suivante décrit la solution à ce problème.

![](assets/cfg_TransformationType_Split.png)

Ici, le champ de sortie est x-products, qui sera utilisé pour créer la dimension étendue souhaitée qui met en correspondance les produits achetés avec les sessions au cours desquelles l’achat a été effectué.
