---
description: Le vecteur moniteur de ressources contient le moniteur de budget mémoire et le moniteur de nombre de Requêtes.
title: Moniteurs de ressource de la file d’attente de la requête
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
exl-id: 6d445a4d-a415-41ce-9d45-1bdd0e726edd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 3%

---

# Moniteurs de ressource de la file d’attente de la requête{#query-queue-resource-monitors}

Le vecteur moniteur de ressources contient le moniteur de budget mémoire et le moniteur de nombre de Requêtes.

Le tableau suivant décrit les champs du moniteur de ressources utilisés pour la mise en file d&#39;attente des requêtes.

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
   <td colname="col1"> <p>Moniteur budgétaire mémoire </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Contrôle la mémoire de requête utilisée par le groupe d’utilisateurs actuel. Si l’utilisation actuelle se situe entre le seuil inférieur et le seuil supérieur, aucun nouveau lot n’est planifié jusqu’à ce que l’utilisation de la mémoire revienne à une valeur inférieure au seuil inférieur, par exemple, en raison de la fermeture des espaces de travail par les utilisateurs. Les lots planifiés sont autorisés à grandir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seuil élevé </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Seuil élevé d’utilisation de la mémoire (octets). Si l’utilisation de la mémoire est supérieure à cette valeur, aucune planification n’est effectuée et les lots planifiés de priorité la plus faible ne sont pas planifiés un par un, sur une période, jusqu’à ce que l’utilisation de la mémoire soit portée en dessous de cette valeur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seuil faible </p> </td> 
   <td colname="col2"> <p>doublon </p> </td> 
   <td colname="col3"> <p>Seuil faible d’utilisation de la mémoire (octets). Si la valeur <span class="wintitle"> Memory Budget Monitor</span> est inférieure à cette valeur, de nouveaux lots sont autorisés à être planifiés et les lots planifiés peuvent augmenter. Par exemple, les lots s’agrandissent lorsqu’un utilisateur ajoute une visualisation à un espace de travail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Temps de réaction </p> </td> 
   <td colname="col2"> <p>doublon </p> </td> 
   <td colname="col3"> <p>Constante temporelle pour le lissage de l’estimation de l’utilisation de la mémoire. Les valeurs de lissage évitent les réactions aux pics d’utilisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Moniteur du nombre de Requêtes </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Contrôle le nombre total de requêtes actuellement planifiées pour le profil. Ce moniteur de ressources vous permet de planifier des lots si le nombre total de requêtes reste inférieur à la valeur du champ Seuil bas. Ce moniteur permet aux lots actuellement planifiés de croître si le nombre total de requêtes reste inférieur à la valeur du champ Seuil élevé. De plus, ce moniteur supprime les lots dont la priorité est faible afin de permettre la planification ou l'agrandissement des lots de priorité plus élevée. Cependant, ce paramètre n’anticipe pas les lots dont la priorité est supérieure à celle spécifiée dans le champ Priorité intouchable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seuil élevé </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Seuil élevé d’utilisation de la mémoire (octets). Si l'utilisation de la mémoire est supérieure à cette valeur, aucune planification n'est effectuée et les lots planifiés de priorité la plus faible ne sont pas planifiés un par un, sur une période, jusqu'à ce que l'utilisation de la mémoire soit portée en dessous de cette valeur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seuil faible </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Seuil faible d’utilisation de la mémoire (octets). Si la valeur <span class="wintitle"> Memory Budget Monitor</span> est inférieure à cette valeur, de nouveaux lots peuvent être planifiés et les lots planifiés peuvent augmenter. </p> </td> 
  </tr> 
 </tbody> 
</table>
