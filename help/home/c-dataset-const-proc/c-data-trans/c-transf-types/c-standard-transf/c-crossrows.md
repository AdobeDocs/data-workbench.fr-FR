---
description: Comme les autres transformations, la transformation CrossRows est appliquée aux lignes de données (entrées de journal) dans vos sources de journaux.
solution: Analytics
title: CrossRows
topic: Data workbench
uuid: 5910c150-6bec-4d98-b116-9b382fd54d3c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# CrossRows{#crossrows}

Comme les autres transformations, la transformation CrossRows est appliquée aux lignes de données (entrées de journal) dans vos sources de journaux.

Pour chaque ligne de données, la transformation prend la valeur du champ d’entrée spécifié, effectue un ensemble d’étapes de traitement et enregistre le résultat dans le champ de sortie que vous spécifiez. Cependant, lorsque la [!DNL CrossRows] transformation fonctionne sur une ligne de données (cette ligne est appelée ligne de sortie), elle prend en compte cette ligne plus une ou plusieurs autres lignes de données (ces lignes sont appelées lignes d’entrée) associées au même ID de suivi. Par conséquent, pour un ID de suivi donné, la valeur du champ de sortie pour chaque ligne de sortie est basée sur les valeurs du champ d’entrée pour une ou plusieurs lignes d’entrée.

La transformation fournit plusieurs conditions et contraintes qui vous permettent de limiter les lignes d’entrée pour la transformation. Vous pouvez exprimer ces limites en fonction des conditions du serveur de l’outil de données (voir [Conditions](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)), d’une plage de lignes d’entrée par rapport à la ligne de sortie ou d’une plage de fois par rapport à l’heure de la ligne de sortie. Pour les lignes d’entrée qui respectent les conditions et les contraintes de la transformation, vous pouvez appliquer une opération (telle que SUM) qui détermine la valeur du champ de sortie.

>[!NOTE]
>
>Pour fonctionner, la [!DNL CrossRows] transformation nécessite que les données soient classées dans le temps et regroupées par ID de suivi dans vos données source. Par conséquent, [!DNL CrossRows] fonctionne uniquement lorsqu’il est défini dans le [!DNL Transformation.cfg] fichier ou dans un [!DNL Transformation Dataset Include] fichier.

Lorsque vous passez en revue les descriptions des paramètres du tableau suivant, tenez compte des points suivants :

* La ligne de sortie est la ligne de données sur laquelle la transformation fonctionne à un moment donné.
* Les lignes d’entrée sont toutes les autres lignes de données (avant, après ou incluant la ligne de sortie) dont les valeurs du champ d’entrée servent d’entrées à la transformation. Les lignes d’entrée sont soumises aux paramètres Condition d’entrée, Clé, Début de la ligne, Fin de la ligne, Début du début et Fin du temps.

<table id="table_152851484AFF4C50AF736DC62FAA43E3"> 
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
   <td colname="col2"> Limite la sortie de la transformation à certaines entrées de journal. Si la condition n’est pas remplie pour une entrée de journal spécifique, le champ du paramètre Output reste inchangé. L'entrée peut toujours être utilisée pour affecter d'autres entrées du journal. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> Nom du champ de la ligne d’entrée à utiliser comme entrée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition d’entrée </td> 
   <td colname="col2"> Accepte les entrées pour la transformation à partir de certaines lignes d’entrée uniquement. Si la condition d’entrée n’est pas remplie pour une ligne d’entrée spécifique, le champ d’entrée de cette ligne est ignoré et n’affecte pas les autres lignes de sortie. Cependant, le champ de sortie de cette ligne est toujours modifié selon la condition spécifiée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clé </td> 
   <td colname="col2"> <p>Facultatif. Nom du champ à utiliser comme clé. </p> <p> Si une clé est spécifiée, les lignes d’entrée d’une ligne de sortie donnée sont limitées au bloc contigu de lignes ayant la même valeur de clé que la ligne de sortie. Cette restriction vient s’ajouter à toutes les autres limites imposées aux lignes d’entrée par d’autres paramètres de la transformation <span class="wintitle"> Lignes</span> croisées. </p> <p> Par exemple, si vous travaillez avec des données Web et que vous définissez le champ x-session-key (qui a une valeur unique pour chaque session) comme clé, les lignes d’entrée de la transformation sont limitées aux lignes ayant la même valeur x-session-key que la ligne de sortie. Par conséquent, vous ne tenez compte que des lignes d’entrée représentant les pages vues qui se produisent au cours de la même session que la ligne de sortie. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opération </td> 
   <td colname="col2"> <p>Opération qui, pour chaque ligne de sortie, est appliquée à toutes les lignes d’entrée satisfaisant à toutes les conditions définies par les paramètres Condition d’entrée, Clé, Début de ligne, Fin de ligne, Début de la durée et Fin de temps pour produire une sortie : 
     <ul id="ul_C01CCF73A9544BCFB7B1105042FEF2DD"> 
      <li id="li_2D1A192970904499AB9F4431D51106D7"> ALL prend toutes les valeurs du champ d’entrée des lignes d’entrée et les génère sous forme de vecteur. </li> 
      <li id="li_B8863724AD924DE5BDBC987143548257"> SUM interprète les valeurs du champ d’entrée des lignes d’entrée comme des nombres et les additionne. </li> 
      <li id="li_BF930069DCEA4E0B80893C3C06CAE100"> PREMIÈRE LIGNE génère la valeur du champ d’entrée à partir de la première ligne d’entrée. </li> 
      <li id="li_04B9E2D88C0847E28101FC830C18D8E2"> LAST ROW génère la valeur du champ d’entrée à partir de la dernière ligne d’entrée. </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sortie </td> 
   <td colname="col2"> Nom du champ de sortie. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Début de ligne/Fin de ligne </td> 
   <td colname="col2"> <p>Facultatif. Spécifie une plage de lignes d’entrée par rapport à la ligne de sortie. Par exemple, une valeur de début de ligne de "0" exclut toutes les lignes précédant la ligne de sortie. La valeur de début de ligne "1" exclut également la ligne de sortie. Les plages courantes sont les suivantes : 
     <ul id="ul_B030F32A5146430BA50DD4FAB4A527B0"> 
      <li id="li_30DFB8C0265349C295943A1CB8077B86"> Début 0 : Cette ligne et toutes les suivantes. </li> 
      <li id="li_9090C2E94E394351867BC5B78F27B41C"> Début 1 : Toutes les lignes suivantes. </li> 
      <li id="li_F870DC913E3F45BA94EE2EC04D344DE0"> Fin 0 : Cette ligne et toutes les précédentes. </li> 
      <li id="li_B8A576E419744D84AB1298E5155B583E"> Fin -1 : Toutes les lignes précédentes. </li> 
      <li id="li_CD2307A262D34542A2860FF07005CAD7"> Début -1, Fin -1 : Ligne précédente. </li> 
      <li id="li_6BF30B7BB7CC40A68B2332A3C11DD3B5"> Début 1, Fin 1 : Ligne suivante. </li> 
     </ul> </p> </td> 
   <td colname="col3"> Toutes les lignes </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de début/Heure de fin </td> 
   <td colname="col2"> <p>Facultatif. Spécifie une plage de temps par rapport à l’heure de la ligne de sortie. Par exemple, une fin de temps de 30 minutes comprend toutes les lignes qui se produisent dans les 30 minutes suivant la ligne de sortie. Un début de durée de -30 minutes comprend toutes les lignes qui se produisent dans les 30 minutes précédant la ligne de sortie. </p> <p> Les unités de temps disponibles sont les jours, les semaines, les heures, les minutes, les ms (millisecondes), les ticks (100 nanosecondes) et les ns (nanosecondes). </p> </td> 
   <td colname="col3"> Toutes les heures </td> 
  </tr> 
 </tbody> 
</table>

La [!DNL CrossRows] transformation de cet exemple est appliquée aux lignes de données Web afin de rechercher pour chaque page vue l’heure de la prochaine page vue. Comme nous savons que [!DNL CrossRows] n’est appliquée que pendant la phase de transformation du processus de construction du jeu de données, les lignes de données sont triées par visiteur (chaque visiteur a un identifiant de suivi unique) et par temps.

Le champ d’entrée, X-timestamp, n’est pris en compte que pour les lignes d’entrée dans lesquelles le champ x-is-page-view est renseigné (indiquant que la ligne de données représente une page vue). Le champ x-session-key (qui a une valeur unique pour chaque session) est spécifié pour le paramètre Key. Par conséquent, les lignes d’entrée (entrées de journal) pour la transformation sont limitées au bloc contigu de lignes ayant la même valeur de x-session-key que la ligne de sortie. En d’autres termes, pour que la transformation soit prise en compte, une ligne d’entrée doit représenter une page vue qui se produit au cours de la même session que la page vue de la ligne de sortie. La première opération de ligne prend la valeur du champ de sortie de la première ligne d’entrée correspondant à la condition [!DNL Input] et ayant la même valeur de clé x-session que la ligne de sortie.

![](assets/cfg_TransformationType_CrossRows.png)

[!DNL CrossRows] s’exécute dans un laps de temps proportionnel à la taille de ses entrées plus la taille de ses sorties. Cela signifie que pour les opérations SUM, PREMIÈRE RANGÉE et DERNIÈRE RANGÉE, elle n&#39;est pas moins efficace que les autres transformations. Pour ALL, la situation est plus complexe, car il est possible de configurer [!DNL CrossRows] pour générer une quantité de données pour chaque ligne de données (entrée de journal) proportionnelle au nombre total de lignes (entrées de journal) pour un ID de suivi donné.
