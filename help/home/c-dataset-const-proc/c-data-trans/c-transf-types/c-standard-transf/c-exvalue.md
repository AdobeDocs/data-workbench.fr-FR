---
description: Si vous travaillez avec des données Web, vous pouvez utiliser la transformation ExtractValue pour extraire une valeur d’une chaîne de requête, d’un cookie ou d’un champ codé de la même manière dans les données de votre site Web.
solution: Analytics
title: ExtractValue
topic: Data workbench
uuid: 305827a2-04e6-421f-82cb-923d62b02e70
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ExtractValue{#extractvalue}

Si vous travaillez avec des données Web, vous pouvez utiliser la transformation ExtractValue pour extraire une valeur d’une chaîne de requête, d’un cookie ou d’un champ codé de la même manière dans les données de votre site Web.

Notez que le ou les noms correspondant à la valeur à extraire peuvent être différents dans chaque entrée de journal.

<table id="table_D16A39BE035043628A4D6F7452952304"> 
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
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions d’application de cette transformation. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom d’entrée </td> 
   <td colname="col2"> <p>Nom(s) du ou des champs à extraire de la requête d’entrée. </p> <p> <p>Remarque :  Si le nom d’entrée est un vecteur (c’est-à-dire qu’il existe plusieurs noms), une seule valeur est extraite. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Requête d’entrée </td> 
   <td colname="col2"> Mappage codé (chaîne de requête, cookie, etc.) à partir duquel la valeur doit être extraite. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeur de sortie </td> 
   <td colname="col2"> Nom du champ utilisé pour capturer la valeur décodée extraite. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

Si vous souhaitez extraire une expression de recherche, vous pouvez extraire l’intégralité de l’expression et, si vous le souhaitez, la diviser en termes de recherche à l’aide d’une [!DNL Tokenize] transformation. Pour plus d’informations sur la [!DNL Tokenize] transformation, voir [Tokenize](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-tokenize.md#concept-f460aa5df3a7476e971af29cf5d9b32c).

Cet exemple configure une [!DNL ExtractValue] transformation pour extraire les valeurs du champ x-v-search-querynames de cs(referrer-query) et les stocker dans le champ x-search-phrase.

![](assets/cfg_TransformationType_ExtractValue.png)

