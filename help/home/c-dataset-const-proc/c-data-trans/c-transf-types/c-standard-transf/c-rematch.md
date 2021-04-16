---
description: La transformation REMatch est une transformation qui correspond à un modèle et qui utilise des expressions régulières pour spécifier un ou plusieurs modèles à rechercher et à capturer dans l’entrée.
title: REMatch
uuid: 8ef80bfa-aea2-45a1-a7d9-38ad33043886
exl-id: 571e6f1c-f557-49c3-9e7c-c31f06132ec7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 4%

---

# REMatch{#rematch}

La transformation REMatch est une transformation qui correspond à un modèle et qui utilise des expressions régulières pour spécifier un ou plusieurs modèles à rechercher et à capturer dans l’entrée.

La transformation crée un champ de sortie pour chaque sous-modèle capturé dans l’expression régulière. Si l’expression régulière ne correspond pas au champ d’entrée, les sorties sont vides et si le champ de sortie existe déjà, les valeurs sont remplacées par les valeurs vides. Pour un bref guide sur l&#39;utilisation des expressions régulières, voir [Expressions régulières](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>La transformation [!DNL REMatch] opère de la même manière que la transformation [!DNL RETransform] (voir [RETransform](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-retransform.md#concept-23f80aa0bc204565b337e5c4931f6a74)), qui utilise des expressions régulières pour capturer une chaîne et la stocke dans un champ de sortie unique.

[!DNL REMatch] analyse une chaîne plus efficacement que plusieurs  [!DNL RETransform] transformations ou une seule  [!DNL RETransform] transformation suivie d’une  [!DNL Flatten] transformation. Voir [Aplatir](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-flatten.md#concept-7acd351a6d2444bd960ca412ae3333ce).

<table id="table_7077578512B249E986BC79AE770CBD9A"> 
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
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Respect de la casse </td> 
   <td colname="col2"> Vrai ou faux. Indique si la correspondance est sensible à la casse. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions d'application de cette transformation. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expression </td> 
   <td colname="col2"> Expression régulière utilisée pour la correspondance. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> Champ par rapport auquel l’expression régulière est évaluée. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sorties </td> 
   <td colname="col2"> <p>Nom de la chaîne de sortie ou du vecteur. Dans le cas des vecteurs de chaîne en entrée, les résultats sont également des vecteurs de chaîne. </p> <p> Un champ de sortie doit exister pour chaque sous-modèle capturant dans l’expression. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL REMatch] les transformations peuvent être très lentes et prendre en compte une grande partie du temps de traitement des données.

Dans cet exemple, une transformation [!DNL REMatch] analyse une date au format AAAA-MM-JJ dans les champs x-année, x-mois et x-jour. Pour la date de 2007-01-02, les valeurs de x-an, x-month et x-day seront respectivement 2007, 01 et 02.

![](assets/cfg_TransformationType_REMatch.png)
