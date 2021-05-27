---
description: Tableau qui définit les paramètres du groupe d’utilisateurs.
title: Groupes d’utilisateurs de la file d’attente de la requête
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
exl-id: e9586ad4-4c0b-48b7-b533-4d23a0f4a216
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# Groupes d’utilisateurs de la file d’attente de la requête{#query-queue-user-groups}

Tableau qui définit les paramètres du groupe d’utilisateurs.

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
   <td colname="col2"> <p>vectoriel </p> </td> 
   <td colname="col3"> <p>Spécifie un type de stratégie. Cliquez avec le bouton droit de la souris pour sélectionner Stratégie standard ou Planification quotidienne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stratégie standard </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Une stratégie standard garantit que les utilisateurs ayant une priorité basse sont déplacés de manière progressive vers le haut de la file d’attente et programmés, même si les utilisateurs ayant une priorité plus élevée entrent dans la file d’attente. Vous pouvez ajouter plusieurs stratégies du même type dans un groupe et leur effet est cumulatif. 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>Limite de priorité : </b> limite au-delà de laquelle la priorité n’est pas incrémentée. Valeur de priorité maximale. Vous pouvez utiliser cette valeur pour conserver les priorités générées par cette stratégie dans une plage spécifique (par exemple, pour que les priorités d’un autre groupe d’utilisateurs soient toujours plus élevées, ou pour qu’elles ne dépassent pas la Priorité intouchable). </li> 
     </ul> </p> <p> <b>Incréments de stratégie standard</b> </p> <p>Les paramètres d’incrément de la stratégie standard augmentent la priorité d’un groupe de requêtes au fil du temps. Cela ne force pas la planification des lots, mais vous pouvez utiliser ces paramètres pour classer par priorité les utilisateurs qui attendent depuis longtemps. Les paramètres placés dans la file d’attente affectent les requêtes qui sont actuellement mises en file d’attente (telles qu’elles sont en attente en raison de ressources insuffisantes pour les terminer). Les paramètres planifiés affectent les requêtes auxquelles une réponse est donnée. La priorité d'une requête est augmentée par le nombre spécifié dans les champs d'incrément et d'intervalle d'incréments appropriés : 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>Incrément en file d’attente : </b> définit l’incrément de priorité par mise à jour lors de la mise en file d’attente. Ce paramètre garantit que les utilisateurs à faible priorité sont déplacés vers le haut de la file d’attente de planification. </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>Intervalle d’incrémentation en file d’attente : </b> définit le nombre de secondes entre les mises à jour en file d’attente. </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>Incrément planifié : </b> définit l’incrément de priorité par mise à jour lors de la planification. </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>Intervalle d’incrémentation planifié : </b> définit le nombre de secondes entre les mises à jour planifiées. <p> <p>Remarque :  La définition des taux de mise à jour d’incrément et d’intervalle plus élevés pour les lots en file d’attente que pour les lots planifiés peut provoquer une oscillation. (Supposons, par exemple, que vous définissiez la valeur Incrément en file d’attente sur 100 et l’Incrément planifié sur 0, et que la valeur Intervalle d’incrémentation en file d’attente soit 1 et que la priorité Intouchable soit élevée. Si deux groupes de requêtes sont fournis avec une priorité de base de 0 et qu’il n’y a pas assez de ressources pour exécuter les deux requêtes en même temps, l’une d’entre elles est planifiée. Au bout d’une seconde, la requête qui n’a pas été planifiée a une priorité de 100, et prévient celle qui a été planifiée. Après deux secondes supplémentaires, celle qui a été anticipée a maintenant une priorité de 200, et les deux interrupteurs se place à nouveau. Aucune requête ne se termine, car toutes les deux secondes la requête en cours de calcul est préemptée afin que l’autre requête puisse s’exécuter.) </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stratégie de planification quotidienne </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Permet de modifier la priorité à des moments spécifiques de la journée. Cette planification est utile pour les clients automatisés, tels que <span class="wintitle"> Report Server</span>, et lorsque les utilisateurs du système vivent dans différents fuseaux horaires. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifications </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Cliquez avec le bouton droit de la souris pour ajouter une modification de priorité planifiée. Le changement d’heure correspond à l’heure de la journée à laquelle le changement se produit. Le format est heure : minutes après le matin/après-midi. Si le matin ou le soir n'est pas entré, le système utilise le temps militaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de priorité </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Valeur de priorité maximale résultant d’une modification. Le changement de priorité est le montant ajouté à la priorité. Par exemple, une valeur de 0 renvoie une priorité par défaut. Toute autre valeur donne une priorité de la priorité par défaut plus ce nombre. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilisateurs </p> </td> 
   <td colname="col2"> <p>vectoriel </p> </td> 
   <td colname="col3"> <p>Répertorie les utilisateurs qui sont membres du groupe. </p> <p> <b>Nom : </b> nom de l’utilisateur tel qu’il apparaît dans le champ Nom commun du certificat de l’utilisateur. </p> <p> <b>Priorité supplémentaire : </b> fournit une priorité supplémentaire à la priorité de base du groupe d’utilisateurs afin de déterminer la priorité de départ de cet utilisateur. </p> </td> 
  </tr> 
 </tbody> 
</table>
