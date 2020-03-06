---
description: Les éléments d’une dimension dénombrable peuvent être comptés par le système.
solution: Analytics
title: Dimensions dénombrables
topic: Data workbench
uuid: 3312f5eb-69b9-43af-b32a-5c40e3050b29
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensions dénombrables{#countable-dimensions}

Les éléments d’une dimension dénombrable peuvent être comptés par le système.

Les dimensions dénombrables sont généralement utilisées pour créer des mesures de somme, qui renvoient le nombre, ou la somme, de tous les éléments de la dimension. Vous pouvez définir des dimensions dénombrables pour comptabiliser des instances telles que les réservations ou les commandes de produits. Par exemple, vous pouvez définir la dimension dénombrable Commandes dont les éléments (entrées de journal correspondant aux commandes de votre boutique en ligne) peuvent être comptabilisés. Si vous souhaitez afficher un nombre de commandes dans une visualisation, vous devez définir la mesure Somme des commandes, qui peut être évaluée sur une dimension ou à laquelle des filtres sont appliqués.

Les dimensions dénombrables peuvent entretenir des relations de type parents/enfants.

>[!NOTE]
>
>Si vous avez besoin d’une dimension qui ne fournit qu’un décompte de quelque chose, vous devez utiliser une dimension numérique avec une opération COUNT. Voir Dimensions [numériques](../../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed).

Les dimensions dénombrables sont définies par les paramètres suivants :

<table id="table_9F3F093F5B074EA68CA4DCE731161F6C"> 
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
   <td colname="col2"> Nom descriptif de la dimension tel qu’il apparaît à l’utilisateur dans les outils de données. Le nom de la dimension ne peut pas inclure de trait d’union (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la dimension étendue. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions dans lesquelles le champ d’entrée contribue à la création de la dimension dénombrable. Si elle est spécifiée, une condition limite le jeu d’entrées de journal visibles pour la dimension et tous ses enfants dans le schéma du jeu de données. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Masqué </td> 
   <td colname="col2"> Détermine si la dimension apparaît dans l’interface de l’outil de données. Par défaut, ce paramètre est défini sur false. Si, par exemple, la dimension doit être utilisée uniquement comme base d’une mesure, vous pouvez définir ce paramètre sur true pour masquer la dimension de l’affichage des outils de données. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clé </td> 
   <td colname="col2"> <p>Facultatif. Nom du champ à utiliser comme clé. Si vous définissez ce paramètre, un élément de la dimension dénombrable existe pour chaque combinaison d’un élément du parent de la dimension dénombrable et d’une valeur distincte du champ spécifié comme clé. </p> <p> Chaque élément de la dimension dénombrable doit être associé à un ensemble contigu d’entrées de journal. Par conséquent, si les entrées du journal ne sont pas triées par la clé, un élément de la dimension dénombrable est créé chaque fois que le champ clé change. Pour éviter cette situation, Adobe recommande d’utiliser une clé unique contiguë dans l’ordre du temps. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> <p>Nom de la dimension parent. Toute dimension dénombrable peut être une dimension parent. Pour faire d’une dimension la dimension de niveau supérieur dans le schéma du jeu de données, définissez le paramètre sur "root". La dimension définie devient la dimension dénombrable racine du jeu de données. Par exemple, si vous travaillez avec Site, la dimension Visiteur est la dimension dénombrable racine de votre jeu de données. </p> <p> <p>Remarque :  Bien que votre dimension dénombrable racine ne doive pas être associée aux ID de suivi dans les données, Adobe vous recommande de configurer la dimension dénombrable racine du jeu de données afin d’utiliser le champ d’ID de suivi (x-trackingid) comme clé. Par conséquent, chaque élément du décompte racine est associé à une valeur unique de x-trackingid et toutes les données de chaque élément sont regroupées. Si vous souhaitez configurer votre jeu de données différemment, contactez Adobe. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Cet exemple illustre la définition d’une dimension dénombrable à l’aide des données d’événement collectées à partir du trafic du site Web. La dimension dénombrable comptabilise les événements de campagne Web au cours d’une session donnée. L’hypothèse est que toutes les ressources de campagne par courrier électronique sont demandées au serveur Web avec &quot;email=&quot; dans le cadre de cs-uri-query. Dans cet exemple, le nombre de fois où le visiteur répond à une campagne par courrier électronique au cours d’une session donnée est intéressant, et non la valeur réelle du champ cs-uri-query(email).

![](assets/cfg_Transformation_Dim_Countable.png)

Cet exemple illustre également la définition d’une dimension dénombrable à l’aide des données d’événement collectées à partir du trafic sur le site Web, mais avec un paramètre Clé défini. La dimension dénombrable Session utilise le champ x-session-key comme clé. (Le champ x-session-key est la sortie de la [!DNL Sessionize] transformation et possède une valeur unique pour chaque session.) Chaque combinaison unique d’un élément de la dimension Visiteur (le parent) et du champ clé de session x est un élément de la dimension Session.

![](assets/cfg_Transformation_Dim_Countable2.png)

