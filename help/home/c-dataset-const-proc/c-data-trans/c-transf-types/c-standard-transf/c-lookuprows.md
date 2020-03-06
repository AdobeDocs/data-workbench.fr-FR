---
description: La transformation LookupRows examine les autres entrées du journal avec le même ID de suivi et définit la valeur du champ de sortie sur la valeur d’un champ désigné dans la ligne d’entrée.
solution: Analytics
title: Lignes de recherche
topic: Data workbench
uuid: 4cff7cf1-00c8-4ab1-8adc-3805518226d3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Lignes de recherche{#lookuprows}

La transformation LookupRows examine les autres entrées du journal avec le même ID de suivi et définit la valeur du champ de sortie sur la valeur d’un champ désigné dans la ligne d’entrée.

Comme la [!DNL LookupRows] transformation effectue sa recherche sur les entrées du journal et non sur les fichiers de recherche, elle est très similaire à la [!DNL CrossRows] transformation. Voir [CrossRows](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2).

Pour fonctionner, la [!DNL LookupRows] transformation nécessite que les données soient classées dans le temps et regroupées par ID de suivi dans vos données source. Par conséquent, [!DNL LookupRows] fonctionne uniquement lorsqu’il est défini dans le [!DNL Transformation.cfg] fichier ou dans un [!DNL Transformation Dataset Include] fichier.

Lorsque vous passez en revue les descriptions des paramètres du tableau suivant, tenez compte des points suivants :

* La ligne de sortie est la ligne de données sur laquelle la transformation fonctionne à un moment donné.
* Les lignes d’entrée sont toutes les autres lignes de données (avant, après ou incluant la ligne de sortie) dont les valeurs du champ d’entrée servent d’entrées à la transformation.

<table id="table_AB68A89ECD5C45F39B8433F994BBD7D8"> 
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
   <td colname="col2"> Limite la sortie de la transformation à certaines entrées de journal. Si la condition n’est pas remplie pour une entrée de journal spécifique, le champ du paramètre Sortie de valeur de ligne de sortie reste inchangé. L'entrée peut toujours être utilisée pour affecter d'autres entrées du journal. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition d’entrée </td> 
   <td colname="col2">Accepte les entrées pour la transformation à partir de certaines lignes d’entrée uniquement. Si la <span class="wintitle"> condition d’entrée</span> n’est pas remplie pour une ligne d’entrée spécifique, le champ d’entrée de cette ligne est ignoré et n’affecte pas les autres lignes de sortie. Cependant, le champ de sortie de cette ligne est toujours modifié selon la condition spécifiée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée de clé de ligne d’entrée </td> 
   <td colname="col2"> Nom du champ à utiliser comme clé pour les lignes d’entrée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée Valeur de ligne d’entrée </td> 
   <td colname="col2"> Nom du champ de la ligne d’entrée dont la valeur est copiée dans le champ du paramètre Output de la valeur de la ligne de sortie si toutes les conditions sont remplies. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opération </td> 
   <td colname="col2"> <p>Opération qui, pour chaque ligne de sortie, est appliquée à toutes les lignes d’entrée satisfaisant à toutes les conditions définies par les paramètres <span class="wintitle"> Condition d’entrée</span> et Entrée de ligne clé d’entrée pour produire une sortie : 
     <ul id="ul_16FB152CB558497794DDED72A2F05CDD"> 
      <li id="li_22DA9F814E4E42D0B21E90B63A2A7A0E"> FIRST génère la valeur du champ dans le paramètre Entrée valeur de ligne d’entrée à partir de la première ligne d’entrée correspondante dans les données (et non de la première ligne correspondante après la ligne de sortie). </li> 
      <li id="li_45E00C3DE0494A1CB5C09B942088F161"> LAST génère la valeur du champ dans le paramètre Entrée valeur de ligne d’entrée de la dernière ligne d’entrée dans les données (et non la dernière ligne correspondante avant la ligne de sortie). </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée de clé de ligne de sortie </td> 
   <td colname="col2"> Nom du champ à utiliser comme clé pour la ligne de sortie. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sortie de la valeur de ligne de sortie </td> 
   <td colname="col2">Nom du champ de la ligne de sortie dont la valeur est copiée à partir du champ du paramètre Entrée valeur de ligne d’entrée si toutes les conditions sont remplies. Toutes les lignes de sortie avec les mêmes <span class="wintitle"> valeurs d’entrée de clé de ligne de sortie et de trackingid x-trackingid ont la même </span>valeur de sortie <span class="wintitle"></span> de ligne de sortie. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Les paramètres Entrée de clé de ligne d’entrée, Entrée de valeur de ligne et Condition d’entrée définissent ensemble le fichier de recherche pour chaque ID de suivi, tandis que les paramètres Entrée de clé de ligne de sortie, Entrée de valeur de ligne de sortie et Condition contrôlent ce qui est recherché dans le fichier et quelle valeur est stockée dans le champ spécifié par Sortie de ligne de sortie.

Pour mieux comprendre le fonctionnement de la transformation, tenez compte des points suivants :

* Pour chaque ligne de sortie satisfaisant à la condition et ayant une entrée de clé de ligne de sortie non vide :

   * Recherchez la ligne d’entrée PREMIER ou DERNIER de sorte que

      * la ligne d’entrée satisfait à la condition d’entrée, et
      * le x-trackingid de la ligne d’entrée est égal au x-trackingid de la ligne de sortie, et
      * l’entrée de clé de ligne d’entrée de la ligne d’entrée est égale à l’entrée de clé de ligne de sortie de la ligne de sortie,

* et définissez la sortie de la ligne de sortie Valeur de la ligne de sortie sur Entrée Valeur de ligne de sortie Entrée de la ligne d’entrée.

Remarques concernant [!DNL LookupRows]

* Les valeurs de clé vierge ne correspondent à rien. Même s’il existe des lignes d’entrée avec des clés vides et des valeurs non vides qui correspondent à la [!DNL Input Condition], une valeur [!DNL Output Row Key Input] &quot; produira toujours une [!DNL Output Row Value Output] valeur &quot;&quot;.

* Si elle n’est pas interdite par la [!DNL Input Condition], une ligne peut se vérifier si ses [!DNL Input Row Key Input] et [!DNL Output Row Key Input] valeurs sont les mêmes.

Si vous disposez de plusieurs valeurs de clé, vous pouvez les combiner à l’aide d’une [!DNL Format] transformation (voir [Format](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-format.md#concept-3de04869181e4694ab072b092186684b)) avant d’appliquer une [!DNL LookupRows] transformation.

Supposons que vous disposez d’un site Web qui comporte une page d’enregistrement des animaux de compagnie, où le nom et la race sont entrés, et une page &quot;Achetez un jouet&quot; plus tard, où seul le nom de l’animal de compagnie est utilisé. Vous souhaitez pouvoir lier le nom de l&#39;animal à la race de l&#39;animal de compagnie entrée dans la page d&#39;inscription. Pour ce faire, vous pouvez créer la [!DNL LookupRows] transformation suivante :

![](assets/cfg_TransformationType_LookupRows.png)

Examinons cet exemple à l&#39;aide de l&#39;aperçu précédent :

* Pour chaque ligne de sortie satisfaisant d&#39;avoir une valeur non vide de cs-uri-query(petname) :

   * Recherchez la dernière ligne d’entrée de telle sorte que

      * la ligne d’entrée contient une valeur non vide de cs-uri-query(petbreed), et
      * le x-trackingid de la ligne d’entrée est égal au x-trackingid de la ligne de sortie, et
      * la valeur de cs-uri-query(petname) de la ligne d&#39;entrée est égale à la valeur de cs-uri-query(petname) de la ligne de sortie,

* et définissez la valeur de x-pet-breed de la ligne de sortie sur la valeur de cs-uri-query(petbreed) de la ligne d’entrée.

La [!DNL LookupRows] transformation utilise le nom de l’animal de compagnie (clé) pour vous assurer que la race d’animaux de compagnie est liée à la fois à l’enregistrement de l’animal de compagnie et aux pages d’achat des jouets afin que vous puissiez analyser les jouets achetés pour chaque race d’animaux de compagnie, même pour les visiteurs ayant plusieurs animaux de compagnie.
