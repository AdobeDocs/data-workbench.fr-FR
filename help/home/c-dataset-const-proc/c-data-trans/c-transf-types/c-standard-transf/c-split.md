---
description: La transformation Partage divise une chaîne en un vecteur de sous-chaînes basé sur un caractère de délimiteur donné.
title: Split
uuid: 116e8465-8fb1-41eb-9a28-412cee54ab87
exl-id: ea85b095-1306-4938-906d-35d421db6c98
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 3%

---

# Partage{#split}

{{eol}}

La transformation Partage divise une chaîne en un vecteur de sous-chaînes basé sur un caractère de délimiteur donné.

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
   <td colname="col2"> Les conditions dans lesquelles cette transformation est appliquée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Délimiteur </td> 
   <td colname="col2"> <p>Chaîne utilisée pour séparer la chaîne d’entrée en sous-chaînes. Doit comporter un seul caractère. </p> <p> Si vous maintenez la touche Ctrl enfoncée et cliquez avec le bouton droit dans le paramètre Délimiteur, un menu Insérer s’affiche. Ce menu contient une liste de caractères spéciaux, souvent utilisés comme délimiteurs. </p> </td> 
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

Prenons l’exemple d’un site web sur lequel les produits achetés par un client sont répertoriés dans la valeur de requête cs-uri lorsque la page de confirmation associée à un achat réussi est consultée. Voici un exemple d’une telle chaîne :

* /checkout/confirmed.asp?prod_selected=B57481,C46355,Z97123

Le champ cs-uri-stem permet de déterminer si la page demandée par l’entrée de journal est la page de confirmation. Les codes des produits achetés par le client sont répertoriés comme les valeurs séparées par des virgules du nom prod_selected dans la requête cs-uri-query. Le [!DNL Split] La transformation peut être utilisée pour extraire ces informations en fractionnant les codes de produit à la virgule si la valeur de cs-uri-stem correspond à la valeur spécifiée dans la variable [!DNL String Match] condition. Voir [Correspondance de chaîne](../../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f). La transformation suivante décrit la solution à ce problème.

![](assets/cfg_TransformationType_Split.png)

Ici, le champ de sortie est x-produits, qui serait utilisé pour créer la dimension étendue souhaitée qui mappe les produits achetés aux sessions au cours desquelles l’achat a été effectué.
