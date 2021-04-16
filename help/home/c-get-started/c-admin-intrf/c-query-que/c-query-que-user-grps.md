---
description: Tableau qui définit les paramètres Groupe d’utilisateurs.
title: Groupes d’utilisateurs de la file d’attente de la requête
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
exl-id: e9586ad4-4c0b-48b7-b533-4d23a0f4a216
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# Groupes d’utilisateurs de la file d’attente de la requête{#query-queue-user-groups}

Tableau qui définit les paramètres Groupe d’utilisateurs.

<table id="table_670A47E25A7A43F0B599BD7ABB173E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nom </p> </td> 
   <td colname="col2"> <p>chaîne </p> </td> 
   <td colname="col3"> <p>Nom défini par l’utilisateur du groupe d’utilisateurs, tel qu’Analystes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stratégies </p> </td> 
   <td colname="col2"> <p>vecteur </p> </td> 
   <td colname="col3"> <p>Spécifie un type de stratégie. Cliquez avec le bouton droit de la souris pour choisir Stratégie standard ou Planification quotidienne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stratégie standard </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Une stratégie standard garantit que les utilisateurs dont la priorité est faible sont déplacés progressivement vers le haut de la file d’attente et planifiés, même si les utilisateurs dont la priorité est plus élevée entrent dans la file d’attente. Vous pouvez ajouter plusieurs stratégies du même type dans un groupe et leur effet est cumulatif. 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>Limite de priorité : </b> limite supérieure à laquelle la priorité n’est pas incrémentée. Valeur de priorité maximale. Vous pouvez utiliser cette valeur pour maintenir les priorités générées par cette stratégie dans une plage spécifique (par exemple, pour que les priorités d’un autre groupe d’utilisateurs soient toujours plus élevées, ou pour qu’elles ne dépassent pas la Priorité intouchable. </li> 
     </ul> </p> <p> <b>Incréments de stratégie standard</b> </p> <p>Les paramètres d’incrémentation de la stratégie standard augmentent la priorité d’un groupe de requêtes au fil du temps. Cela ne force pas la planification des lots, mais vous pouvez utiliser ces paramètres pour classer par priorité les utilisateurs qui attendent depuis longtemps. Les paramètres en file d’attente affectent les requêtes actuellement mises en file d’attente (par exemple, en attente en raison d’un manque de ressources pour les terminer). Les paramètres planifiés affectent les requêtes auxquelles une réponse est apportée. La priorité d’une requête augmente selon le nombre spécifié dans les champs d’incrément et d’intervalle d’incréments appropriés : 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>Incrément en file d’attente : </b> définit l’incrément de priorité par mise à jour en file d’attente. Ce paramètre garantit que les utilisateurs dont la priorité est faible sont déplacés vers le haut de la file d’attente de planification. </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>Intervalle d’incrémentation en file d’attente : </b> définit le nombre de secondes entre les mises à jour en file d’attente. </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>Incrément planifié : </b> définit l’incrément de priorité par mise à jour lors de la planification. </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>Intervalle des incréments planifiés : </b> définit le nombre de secondes entre les mises à jour planifiées. <p> <p>Remarque :  La définition des taux de mise à jour des incréments et des intervalles plus élevés pour les lots en file d'attente que pour les lots planifiés peut provoquer une oscillation. (Par exemple, supposons que vous définissiez la valeur Incrément en file d'attente sur 100 et l'Incrément planifié sur 0, et que vous définissez la valeur Intervalle d'incrément en file d'attente sur 1 et la valeur Priorité intouchable sur 0. Si deux lots de requêtes correspondent à une priorité de base de 0 et qu’il n’y a pas assez de ressources pour exécuter les deux requêtes en même temps, l’une d’elles est planifiée. Au bout d’une seconde, la requête qui n’a pas été planifiée a une priorité de 100 et prévient celle qui a été planifiée. Après deux secondes de plus, celle qui a été préemptée a maintenant une priorité de 200, et les deux commutateurs se place à nouveau. Aucune de ces requêtes ne se termine, car toutes les deux secondes, la requête en cours de calcul est préemptée afin que l’autre requête puisse s’exécuter.) </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stratégie de planification quotidienne </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Permet de modifier la priorité à des moments spécifiques de la journée. Cette planification est utile pour les clients automatisés, tels que <span class="wintitle"> Report Server</span>, et lorsque les utilisateurs du système vivent dans des fuseaux horaires différents. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifications </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Cliquez avec le bouton droit de la souris pour ajouter une modification de priorité planifiée. L’heure des modifications est l’heure de la journée à laquelle la modification a lieu. Le format est heure : minutes AM/PM. Si AM ou PM n'est pas entré, le système utilise le temps militaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de priorité </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Valeur de priorité maximale résultant d’une modification. Le changement de priorité est le montant ajouté à la priorité. Par exemple, une valeur de 0 revient à une priorité par défaut. Toute autre valeur donne une priorité de la priorité par défaut plus ce nombre. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilisateurs </p> </td> 
   <td colname="col2"> <p>vecteur </p> </td> 
   <td colname="col3"> <p>Liste les utilisateurs qui sont membres du groupe. </p> <p> <b>Nom : </b> nom de l’utilisateur tel qu’il apparaît dans le champ Nom commun du certificat de l’utilisateur. </p> <p> <b>Priorité supplémentaire : </b> fournit une priorité supplémentaire à la priorité de base du groupe d’utilisateurs afin de déterminer la priorité de départ de cet utilisateur. </p> </td> 
  </tr> 
 </tbody> 
</table>
