---
description: La transformation REMatch est une transformation qui correspond à des motifs qui utilise des expressions régulières pour spécifier un ou plusieurs modèles à rechercher et à capturer dans l’entrée.
title: REMatch
uuid: 8ef80bfa-aea2-45a1-a7d9-38ad33043886
exl-id: 571e6f1c-f557-49c3-9e7c-c31f06132ec7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 3%

---

# REMatch{#rematch}

{{eol}}

La transformation REMatch est une transformation qui correspond à des motifs qui utilise des expressions régulières pour spécifier un ou plusieurs modèles à rechercher et à capturer dans l’entrée.

La transformation crée un champ de sortie pour chaque sous-modèle de capture dans l’expression régulière. Si l’expression régulière ne correspond pas au champ d’entrée, les sorties sont vides et si le champ de sortie existe déjà, les valeurs sont remplacées par les valeurs vides. Pour un bref guide sur l’utilisation des expressions régulières, voir [Expressions régulières](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>Le [!DNL REMatch] La transformation fonctionne de la même manière que la [!DNL RETransform] transformation (voir [RETransform](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-retransform.md#concept-23f80aa0bc204565b337e5c4931f6a74)), qui utilise des expressions régulières pour capturer une chaîne et la stocke dans un champ de sortie unique.

[!DNL REMatch] analyse une chaîne plus efficacement que plusieurs [!DNL RETransform] transformations ou une seule [!DNL RETransform] une transformation suivie d&#39;une [!DNL Flatten] transformation. Voir [Aplatissement](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-flatten.md#concept-7acd351a6d2444bd960ca412ae3333ce).

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
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Respect de la casse </td> 
   <td colname="col2"> True ou false. Indique si la correspondance est sensible à la casse. </td> 
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
   <td colname="col2"> <p>Nom de la chaîne ou du vecteur de sortie. Dans le cas de vecteurs de chaîne en entrée, les sorties sont également des vecteurs de chaîne. </p> <p> Un champ de sortie doit exister pour chaque sous-modèle de capture dans l’expression. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL REMatch] Les transformations peuvent être très lentes et peuvent prendre en compte une grande partie du temps de traitement des données.

Dans cet exemple, un [!DNL REMatch] transformation analyse une date au format AAAA-MM-JJ dans les champs x-année, x-mois et x-jour. Pour la date 2007-01-02, les valeurs de x-year, x-month et x-day sont 2007, 01 et 02, respectivement.

![](assets/cfg_TransformationType_REMatch.png)
