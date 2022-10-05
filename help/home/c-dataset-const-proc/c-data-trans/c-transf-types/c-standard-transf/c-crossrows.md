---
description: Comme les autres transformations, la transformation CrossRows est appliquée aux lignes de données (entrées de journal) dans vos sources de journaux.
title: CrossRows
uuid: 5910c150-6bec-4d98-b116-9b382fd54d3c
exl-id: 321f986e-44a9-454c-9311-0ae37a11a088
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 1%

---

# CrossRows{#crossrows}

{{eol}}

Comme les autres transformations, la transformation CrossRows est appliquée aux lignes de données (entrées de journal) dans vos sources de journaux.

Pour chaque ligne de données, la transformation prend la valeur du champ d’entrée spécifié, effectue un ensemble d’étapes de traitement et enregistre le résultat dans le champ de sortie que vous spécifiez. Cependant, lorsque la variable [!DNL CrossRows] la transformation fonctionne sur une ligne de données (cette ligne est appelée la ligne de sortie), elle prend en compte cette ligne plus une ou plusieurs autres lignes de données (ces lignes sont appelées lignes d’entrée) associées au même ID de suivi. Par conséquent, pour un identifiant de suivi donné, la valeur du champ de sortie pour chaque ligne de sortie est basée sur les valeurs du champ d’entrée pour une ou plusieurs lignes d’entrée.

La transformation fournit plusieurs conditions et contraintes qui vous permettent de limiter les lignes d’entrée pour la transformation. Vous pouvez exprimer ces limites en fonction des conditions du serveur Data Workbench (voir [Conditions](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)), une plage de lignes d’entrée par rapport à la ligne de sortie ou une plage de temps par rapport à l’heure de la ligne de sortie. Pour les lignes d’entrée qui répondent aux conditions et contraintes de la transformation, vous pouvez appliquer une opération (telle que SUM) qui détermine la valeur du champ de sortie.

>[!NOTE]
>
>Pour travailler, la variable [!DNL CrossRows] La transformation nécessite que les données soient classées dans l’heure et regroupées par identifiant de suivi dans vos données source. Par conséquent, [!DNL CrossRows] fonctionne uniquement lorsqu’il est défini dans la variable [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include] fichier .

Lorsque vous passez en revue les descriptions des paramètres dans le tableau suivant, pensez à ce qui suit :

* La ligne de sortie correspond à la ligne de données sur laquelle la transformation fonctionne à un moment donné.
* Les lignes d’entrée sont toutes les autres lignes de données (avant, après ou incluant la ligne de sortie) dont les valeurs du champ d’entrée servent d’entrées à la transformation. Les lignes d’entrée sont soumises aux paramètres Condition d’entrée, Clé, Début de la ligne, Fin de la ligne, Début de l’heure et Fin de l’heure.

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
   <td colname="col2"> Limite la sortie de la transformation à certaines entrées de journal. Si la condition n’est pas remplie pour une entrée de journal spécifique, le champ du paramètre Output reste inchangé. L’entrée peut toujours être utilisée pour affecter d’autres entrées de journal. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> Nom du champ de la ligne de saisie à utiliser comme entrée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition d’entrée </td> 
   <td colname="col2"> Accepte les entrées pour la transformation à partir de certaines lignes d’entrée seulement. Si la condition d’entrée n’est pas remplie pour une ligne d’entrée spécifique, le champ d’entrée de cette ligne est ignoré et n’affecte pas les autres lignes de sortie. Cependant, le champ de sortie de cette ligne est toujours modifié selon la condition spécifiée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clé </td> 
   <td colname="col2"> <p>Facultatif. Nom du champ à utiliser comme clé. </p> <p> Si une clé est spécifiée, les lignes d’entrée d’une ligne de sortie donnée sont limitées au bloc contigu de lignes ayant la même valeur de clé que la ligne de sortie. Cette restriction s’ajoute à toutes les autres limitations placées sur les lignes d’entrée par d’autres paramètres de la variable <span class="wintitle"> CrossRows</span> transformation. </p> <p> Par exemple, si vous utilisez des données web et que vous définissez le champ x-session-key (qui a une valeur unique pour chaque session) comme clé, les lignes d’entrée pour la transformation sont limitées aux lignes ayant la même valeur x-session-key que la ligne de sortie. Par conséquent, vous ne tenez compte que des lignes d’entrée représentant les pages vues qui se produisent au cours de la même session que la ligne de sortie. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opération </td> 
   <td colname="col2"> <p>Opération qui, pour chaque ligne de sortie, est appliquée à toutes les lignes d’entrée satisfaisant toutes les conditions définies par les paramètres Condition d’entrée, Clé, Début de ligne, Fin de ligne, Début de temps et Fin de temps pour produire une sortie : 
     <ul id="ul_C01CCF73A9544BCFB7B1105042FEF2DD"> 
      <li id="li_2D1A192970904499AB9F4431D51106D7"> ALL prend toutes les valeurs du champ de saisie des lignes de saisie et les génère comme vecteur. </li> 
      <li id="li_B8863724AD924DE5BDBC987143548257"> SUM interprète les valeurs du champ de saisie des lignes de saisie comme des nombres et des sommes. </li> 
      <li id="li_BF930069DCEA4E0B80893C3C06CAE100"> PREMIÈRE LIGNE génère la valeur du champ de saisie à partir de la première ligne de saisie. </li> 
      <li id="li_04B9E2D88C0847E28101FC830C18D8E2"> LAST ROW génère la valeur du champ de saisie à partir de la dernière ligne de saisie. </li> 
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
   <td colname="col2"> <p>Facultatif. Spécifie une plage de lignes d’entrée par rapport à la ligne de sortie. Par exemple, une valeur de début de ligne de "0" exclut toutes les lignes situées avant la ligne de sortie. Une valeur de début de ligne "1" exclut également la ligne de sortie. Les plages courantes sont les suivantes : 
     <ul id="ul_B030F32A5146430BA50DD4FAB4A527B0"> 
      <li id="li_30DFB8C0265349C295943A1CB8077B86"> Début 0 : Cette ligne et toutes les suivantes. </li> 
      <li id="li_9090C2E94E394351867BC5B78F27B41C"> Début 1 : Toutes les lignes suivantes. </li> 
      <li id="li_F870DC913E3F45BA94EE2EC04D344DE0"> Fin 0 : Cette ligne et toutes les lignes précédentes. </li> 
      <li id="li_B8A576E419744D84AB1298E5155B583E"> Fin -1 : Toutes les lignes précédentes. </li> 
      <li id="li_CD2307A262D34542A2860FF07005CAD7"> Début -1, Fin -1 : Ligne précédente. </li> 
      <li id="li_6BF30B7BB7CC40A68B2332A3C11DD3B5"> Début 1, Fin 1 : Ligne suivante. </li> 
     </ul> </p> </td> 
   <td colname="col3"> Toutes les lignes </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Début/Fin de l’heure </td> 
   <td colname="col2"> <p>Facultatif. Indique une plage de temps par rapport à l’heure de la ligne de sortie. Par exemple, une fin de temps de 30 minutes inclut toutes les lignes qui ont lieu dans les 30 minutes suivant la ligne de sortie. Une valeur de -30 minutes au début inclut toutes les lignes qui se produisent dans les 30 minutes précédant la ligne de sortie. </p> <p> Les unités de temps disponibles sont les jours, les semaines, les heures, les minutes, les ms (millisecondes), les tiques (100 nanosecondes) et les ns (nanosecondes). </p> </td> 
   <td colname="col3"> Toutes les heures </td> 
  </tr> 
 </tbody> 
</table>

Le [!DNL CrossRows] dans cet exemple, la transformation est appliquée aux lignes de données web pour rechercher pour chaque page vue l’heure de la prochaine page vue. Parce que nous savons que [!DNL CrossRows] n’est appliquée que pendant la phase de transformation du processus de construction du jeu de données, les lignes de données sont triées par visiteur (chaque visiteur possède un ID de suivi unique) et par heure.

Le champ d’entrée, horodatage x, est pris en compte uniquement pour les lignes d’entrée dans lesquelles le champ x-is-page-view est renseigné (indiquant que la ligne de données représente une page vue). Le champ x-session-key (qui a une valeur unique pour chaque session) est spécifié pour le paramètre Key (Clé). Par conséquent, les lignes d’entrée (entrées de journal) pour la transformation sont limitées au bloc contigu de lignes ayant la même valeur de x-session-key que la ligne de sortie. En d’autres termes, pour que la transformation soit prise en compte, une ligne d’entrée doit représenter une page vue qui se produit au cours de la même session que la page vue de la ligne de sortie. La première opération de ligne prend la valeur du champ de sortie de la première ligne d’entrée satisfaisant la variable [!DNL Input] Condition et avec la même valeur x-session-key que la ligne de sortie.

![](assets/cfg_TransformationType_CrossRows.png)

[!DNL CrossRows] s’exécute dans un laps de temps proportionnel à la taille de ses entrées plus la taille de ses sorties. Cela signifie que, pour les opérations SUM, PREMIÈRE LIGNE et DERNIÈRE LIGNE, elle n’est pas moins efficace que les autres transformations. Pour ALL, la situation est plus complexe car il est possible de configurer [!DNL CrossRows] pour générer une quantité de données pour chaque ligne de données (entrée de journal) proportionnelle au nombre total de lignes (entrées de journal) pour un identifiant de suivi donné.
