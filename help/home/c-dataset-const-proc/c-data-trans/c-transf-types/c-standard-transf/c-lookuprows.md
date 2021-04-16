---
description: La transformation LookupRows examine d'autres entrées de journal avec le même ID de suivi et définit la valeur du champ de sortie sur la valeur d'un champ désigné dans la ligne d'entrée.
title: LookupRows
uuid: 4cff7cf1-00c8-4ab1-8adc-3805518226d3
exl-id: caa9a311-b056-4fe8-bb11-1605cc690375
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 1%

---

# LookupRows{#lookuprows}

La transformation LookupRows examine d&#39;autres entrées de journal avec le même ID de suivi et définit la valeur du champ de sortie sur la valeur d&#39;un champ désigné dans la ligne d&#39;entrée.

Comme la transformation [!DNL LookupRows] effectue sa recherche sur les entrées de journal et non sur les fichiers de recherche, elle est très similaire à la transformation [!DNL CrossRows]. Voir [CrossRows](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2).

Pour fonctionner, la transformation [!DNL LookupRows] requiert que les données soient triées dans le temps et regroupées par ID de suivi dans vos données source. Par conséquent, [!DNL LookupRows] ne fonctionne que lorsqu&#39;il est défini dans le fichier [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include].

Lorsque vous passez en revue les descriptions des paramètres du tableau suivant, tenez compte des points suivants :

* La ligne de sortie correspond à la ligne de données sur laquelle la transformation travaille à un moment donné.
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
   <td colname="col2"> Limite la sortie de la transformation à certaines entrées de journal. Si la condition n’est pas remplie pour une entrée de journal particulière, le champ du paramètre Sortie de valeur de ligne de sortie reste inchangé. L'entrée peut toujours être utilisée pour affecter d'autres entrées de journal. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition d’entrée </td> 
   <td colname="col2">Accepte l’entrée pour la transformation à partir de certaines lignes d’entrée seulement. Si la condition <span class="wintitle"> Input</span> n'est pas remplie pour une ligne d'entrée particulière, le champ d'entrée de cette ligne est ignoré et n'affecte pas les autres lignes de sortie. Cependant, le champ de sortie de cette ligne est toujours modifié selon la condition spécifiée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée de clé de ligne d'entrée </td> 
   <td colname="col2"> Nom du champ à utiliser comme clé pour les lignes d’entrée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée de valeur de ligne </td> 
   <td colname="col2"> Nom du champ de la ligne d’entrée dont la valeur est copiée dans le champ du paramètre de sortie Valeur de la ligne de sortie si toutes les conditions sont remplies. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opération </td> 
   <td colname="col2"> <p>Opération qui, pour chaque ligne de sortie, est appliquée à toutes les lignes d'entrée satisfaisant à toutes les conditions définies par les paramètres d'entrée de condition <span class="wintitle"> Input</span> Condition et de ligne d'entrée Key Input pour produire une sortie : 
     <ul id="ul_16FB152CB558497794DDED72A2F05CDD"> 
      <li id="li_22DA9F814E4E42D0B21E90B63A2A7A0E"> FIRST génère la valeur du champ dans le paramètre Input Row Value Input Input Input Input Input Value Input à partir de la première ligne d’entrée correspondante dans les données (et non de la première ligne correspondante après la ligne de sortie). </li> 
      <li id="li_45E00C3DE0494A1CB5C09B942088F161"> LAST génère la valeur du champ dans le paramètre Input Row Value Input Input Input Input Input (Valeur de ligne d’entrée) à partir de la dernière ligne d’entrée des données (et non de la dernière ligne correspondante avant la ligne de sortie). </li> 
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
   <td colname="col2">Nom du champ de la ligne de sortie dont la valeur est copiée à partir du champ du paramètre Entrée valeur de ligne si toutes les conditions sont remplies. Toutes les lignes de sortie avec les mêmes valeurs x-trackingid et <span class="wintitle"> Entrée de clé de ligne de sortie </span>ont la même valeur <span class="wintitle"> Sortie de valeur de ligne de sortie</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Les paramètres Input Row Key Input, Input Row Value Input et Input Condition définissent ensemble le fichier de recherche pour chaque ID de suivi, tandis que les paramètres Output Row Key Input, Output Row Value Input et Condition contrôlent ce qui est recherché dans le fichier et quelle valeur est stockée dans le champ spécifié par Output Row Value.

Pour mieux comprendre le fonctionnement de la transformation, tenez compte des points suivants :

* Pour chaque ligne de sortie correspondant à la condition et ayant une entrée de clé de ligne de sortie non vide :

   * Recherchez la ligne d’entrée PREMIER ou DERNIER telle que

      * la ligne d’entrée satisfait à la condition d’entrée, et
      * le x-trackingid de la ligne d’entrée est égal au x-trackingid de la ligne de sortie, et
      * l’entrée de clé de ligne d’entrée de la ligne d’entrée est égale à l’entrée de clé de ligne de sortie de la ligne de sortie,

* et définissez Output Row Value (Sortie de la valeur de la ligne de sortie) sur Input Row Value (Entrée de la ligne de sortie) Input Row Value (Entrée de la ligne d’entrée).

Considérations relatives à [!DNL LookupRows]

* Les valeurs de clé vierges ne correspondent à rien. Même si des lignes d&#39;entrée avec des clés vides et des valeurs non vides correspondent à [!DNL Input Condition], un [!DNL Output Row Key Input] de &quot;&quot; produira toujours un [!DNL Output Row Value Output] de &quot;&quot;.

* Si elle n&#39;est pas interdite par [!DNL Input Condition], une ligne peut se vérifier si ses valeurs [!DNL Input Row Key Input] et [!DNL Output Row Key Input] sont identiques.

Si vous disposez de plusieurs valeurs de clé, vous pouvez les combiner en utilisant une transformation [!DNL Format] (voir [Format](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-format.md#concept-3de04869181e4694ab072b092186684b)) avant d&#39;appliquer une transformation [!DNL LookupRows].

Supposons que vous disposez d’un site Web qui comporte une page d’enregistrement des animaux de compagnie, où le nom et la race sont saisis, et une page &quot;acheter un jouet&quot; ultérieure où seul le nom de l’animal de compagnie est utilisé. Vous souhaitez être en mesure de lier le nom de l&#39;animal à la race de l&#39;animal de compagnie entrée sur la page d&#39;inscription. Pour ce faire, vous pouvez créer la transformation [!DNL LookupRows] suivante :

![](assets/cfg_TransformationType_LookupRows.png)

Analysons cet exemple à l&#39;aide de la présentation précédente :

* Pour chaque ligne de sortie correspondant à une valeur non vide de cs-uri-requête(petname) :

   * Recherchez la dernière ligne d’entrée de telle sorte que

      * la ligne d’entrée contient une valeur non vide de cs-uri-requête(petbreed), et
      * le x-trackingid de la ligne d’entrée est égal au x-trackingid de la ligne de sortie, et
      * la valeur de cs-uri-requête(petname) de la ligne d’entrée est égale à la valeur de cs-uri-requête(petname) de la ligne de sortie,

* et définissez la valeur de x-pet-breed de la ligne de sortie sur la valeur de cs-uri-requête(petbreed) de la ligne d’entrée.

La transformation [!DNL LookupRows] utilise le nom de l&#39;animal de compagnie (la clé) pour s&#39;assurer que la race de l&#39;animal de compagnie est liée à la fois à l&#39;enregistrement de l&#39;animal de compagnie et aux pages d&#39;achat des jouets afin que vous puissiez analyser les jouets achetés pour chaque race d&#39;animal de compagnie, même pour les visiteurs ayant plusieurs animaux de compagnie.
