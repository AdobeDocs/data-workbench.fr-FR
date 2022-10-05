---
description: Le vecteur de moniteur de ressources contient le moniteur de budget mémoire et le moniteur de nombre de requêtes.
title: Moniteurs de ressource de la file d’attente de la requête
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
exl-id: 6d445a4d-a415-41ce-9d45-1bdd0e726edd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 3%

---

# Moniteurs de ressource de la file d’attente de la requête{#query-queue-resource-monitors}

{{eol}}

Le vecteur de moniteur de ressources contient le moniteur de budget mémoire et le moniteur de nombre de requêtes.

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
   <td colname="col1"> <p>Surveillance du budget de la mémoire </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Surveille la mémoire de requête utilisée par le groupe d’utilisateurs actuel. Si l’utilisation actuelle se situe entre le seuil faible et le seuil élevé, aucun nouveau lot n’est planifié jusqu’à ce que l’utilisation de la mémoire revienne à une valeur inférieure au seuil faible, par exemple, en raison de la fermeture des espaces de travail par les utilisateurs. Les lots planifiés peuvent grandir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seuil élevé </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Seuil élevé d’utilisation de la mémoire (octets). Si l’utilisation de la mémoire est supérieure à cette valeur, aucune planification n’a lieu et les lots planifiés avec la priorité la plus faible ne sont pas planifiés un par un, sur une période donnée, jusqu’à ce que l’utilisation de la mémoire soit portée en dessous de cette valeur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seuil faible </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Seuil faible d’utilisation de la mémoire (octets). If <span class="wintitle"> Surveillance du budget de la mémoire</span> est inférieure à cette valeur, les nouveaux lots sont autorisés à être planifiés et les lots planifiés peuvent augmenter. Par exemple, des lots se développent lorsqu’un utilisateur ajoute une visualisation à un espace de travail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Temps de réaction </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Constante temporelle pour le lissage de l’estimation de l’utilisation de la mémoire. Les valeurs de lissage évitent de réagir aux pics d’utilisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre de requêtes Monitor </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Surveille le nombre total de requêtes actuellement planifiées pour le profil. Ce moniteur de ressources permet de planifier des lots si le nombre total de requêtes reste inférieur à la valeur du champ Seuil bas . Ce moniteur permet une croissance des lots actuellement planifiés si le nombre total de requêtes reste inférieur à la valeur du champ Seuil élevé . En outre, ce moniteur supprime les lots de priorité basse afin de permettre la planification ou la croissance des lots de priorité supérieure. Cependant, ce paramètre n’anticipe pas les lots dont la priorité est supérieure à celle spécifiée dans le champ Priorité intouchable . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seuil élevé </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Seuil élevé d’utilisation de la mémoire (octets). Si l’utilisation de la mémoire est supérieure à cette valeur, aucune planification n’a lieu et les lots planifiés de priorité la plus faible ne sont pas planifiés un par un, sur une période donnée, jusqu’à ce que l’utilisation de la mémoire soit portée en dessous de cette valeur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seuil faible </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Seuil faible d’utilisation de la mémoire (octets). If <span class="wintitle"> Surveillance du budget de la mémoire</span> est inférieure à cette valeur, de nouveaux lots peuvent être planifiés et les lots planifiés peuvent augmenter. </p> </td> 
  </tr> 
 </tbody> 
</table>
