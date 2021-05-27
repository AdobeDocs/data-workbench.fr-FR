---
description: Si vous utilisez des données web, vous pouvez utiliser la transformation ExtractValue pour extraire une valeur d’une chaîne de requête, d’un cookie ou d’un champ codé de manière similaire dans les données de votre site web.
title: ExtractValue
uuid: 305827a2-04e6-421f-82cb-923d62b02e70
exl-id: 5bafe64f-081a-49ec-997e-68e8f6915a71
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# ExtractValue{#extractvalue}

Si vous utilisez des données web, vous pouvez utiliser la transformation ExtractValue pour extraire une valeur d’une chaîne de requête, d’un cookie ou d’un champ codé de manière similaire dans les données de votre site web.

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
   <td colname="col2"> Les conditions dans lesquelles cette transformation est appliquée. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Name </td> 
   <td colname="col2"> <p>Nom(s) du ou des champs à extraire de la requête de saisie. </p> <p> <p>Remarque :  Si le Nom d’entrée est un vecteur (c’est-à-dire qu’il existe plusieurs noms), une seule valeur est extraite. </p> </p> </td> 
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

Si vous souhaitez extraire une expression de recherche, vous pouvez extraire l’expression entière et, si vous le souhaitez, la diviser en termes de recherche à l’aide d’une transformation [!DNL Tokenize]. Pour plus d’informations sur la transformation [!DNL Tokenize], voir [Tokenize](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-tokenize.md#concept-f460aa5df3a7476e971af29cf5d9b32c).

Cet exemple configure une transformation [!DNL ExtractValue] pour extraire les valeurs du champ x-v-search-querynames à partir de cs(referrer-query) et les stocker dans le champ x-search-phrase .

![](assets/cfg_TransformationType_ExtractValue.png)
