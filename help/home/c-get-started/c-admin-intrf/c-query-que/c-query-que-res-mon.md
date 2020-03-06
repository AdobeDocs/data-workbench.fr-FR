---
description: Le vecteur du moniteur de ressources contient le moniteur du budget de la mémoire et le moniteur du nombre de requêtes.
solution: Analytics
title: Moniteurs de ressources de file d'attente de requête
topic: Data workbench
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Moniteurs de ressources de file d&#39;attente de requête{#query-queue-resource-monitors}

Le vecteur du moniteur de ressources contient le moniteur du budget de la mémoire et le moniteur du nombre de requêtes.

Le tableau suivant décrit les champs du moniteur de ressources utilisés pour la mise en file d’attente des requêtes.

<table id="table_9991EED2647A460FACA2DC80D4973A8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Moniteur du budget mémoire </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Surveille la mémoire de requête utilisée par le groupe d’utilisateurs actuel. Si l’utilisation actuelle se situe entre le seuil inférieur et le seuil supérieur, aucun nouveau lot n’est planifié tant que l’utilisation de la mémoire ne revient pas en dessous de la valeur du seuil inférieur, par exemple lorsque les utilisateurs ferment leurs espaces de travail. Les lots planifiés peuvent grandir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seuil élevé </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Le seuil élevé d’utilisation de la mémoire (octets). Si l’utilisation de la mémoire est supérieure à cette valeur, aucune planification n’est effectuée et les lots planifiés de priorité la plus faible ne sont pas planifiés un par un, sur une période, jusqu’à ce que l’utilisation de la mémoire soit inférieure à cette valeur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seuil faible </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Seuil faible d’utilisation de la mémoire (octets). Si la valeur <span class="wintitle"> Memory Budget Monitor</span> est inférieure à cette valeur, de nouveaux lots peuvent être planifiés et les lots planifiés peuvent grandir. Par exemple, les lots s’étendent lorsqu’un utilisateur ajoute une visualisation à un espace de travail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Temps de réaction </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Constante temporelle pour le lissage de l’estimation de l’utilisation de la mémoire. Les valeurs de lissage évitent de réagir aux pics d’utilisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Moniteur du nombre de requêtes </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Surveille le nombre total de requêtes actuellement planifiées pour le profil. Ce moniteur de ressources vous permet de planifier des lots si le nombre total de requêtes reste inférieur à la valeur du champ Seuil bas. Ce moniteur permet aux lots planifiés actuellement de s’agrandir si le nombre total de requêtes reste inférieur à la valeur du champ Seuil élevé. De plus, ce moniteur supprime les lots dont la priorité est faible afin de permettre la planification ou l’augmentation des lots de priorité plus élevée. Toutefois, ce paramètre n’empêche pas les lots dont la priorité est supérieure à celle spécifiée dans le champ Priorité intouchable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seuil élevé </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Le seuil élevé d’utilisation de la mémoire (octets). Si l’utilisation de la mémoire est supérieure à cette valeur, aucune planification n’est effectuée et les lots planifiés de priorité la plus faible ne sont pas planifiés un par un, sur une période donnée, jusqu’à ce que l’utilisation de la mémoire soit inférieure à cette valeur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seuil faible </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Seuil faible d’utilisation de la mémoire (octets). Si la valeur <span class="wintitle"> Memory Budget Monitor</span> est inférieure à cette valeur, de nouveaux lots peuvent être planifiés et les lots planifiés peuvent grandir. </p> </td> 
  </tr> 
 </tbody> 
</table>

