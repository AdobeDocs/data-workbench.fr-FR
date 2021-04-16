---
description: Le profil de trafic contient les dimensions suivantes pour aider à identifier les actions des visiteurs.
title: Dimensions du profil de trafic
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
exl-id: 1e7d2904-aa5d-4848-a398-5d4669953be9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 8%

---

# Dimensions du profil de trafic{#traffic-profile-dimensions}

Le profil de trafic contient les dimensions suivantes pour aider à identifier les actions des visiteurs.

Les dimensions du tableau suivant sont définies dans le jeu de données de transformation et comprennent des fichiers dans le dossier Traffic\Dataset\Transformation directory.

| Nom | Type | Niveau | Description |
|---|---|---|---|
| Jour | Simple | Session | Jour de la première entrée de journal de la session. |
| Jour de la semaine | Simple | Session | Jour de la semaine de la première entrée de journal d&#39;une session. |
| Durée exacte de la page (masquée) | Numérique | Page vue | Durée, en millisecondes, de la vue de page telle que mesurée en soustrayant l’heure de la vue de page suivante de l’heure de cette vue de page. La durée exacte de la dernière vue de page d’une session est toujours de 0. |
| Heure | Simple | Session | Heure de la première entrée de journal d&#39;une session. |
| Heure de la journée | Simple | Session | Heure du jour de la première entrée de journal d&#39;une session. |
| Mois | Simple | Session | Mois de la première entrée de journal d&#39;une session. |
| Page vue | Comptable | Session | Entrée de journal ou &quot;enregistrement de données de Événement&quot; correspondant à la condition de Vue de page. |
| Référent | Simple | Session | Domaine de deuxième niveau du parrain de la première entrée de journal de la session (ou Aucun s’il s’agit d’un domaine de parrain interne). |
| Session | Comptable | Visiteur | Période d’activité contiguë connexe par un Visiteur. Il est délimité par une période d’inactivité de 30 minutes et un domaine de parrain externe ou une durée de session maximale de 48 heures. Ces expirations de délai et l&#39;ensemble de domaines considérés comme internes peuvent être configurés dans le fichier [!DNL Transformation.cfg]. |
| URI | Simple | Page vue | La racine URI d’une vue de page. La dimension URI peut être redéfinie à l’aide des transformations ReplaceURI, PrependURI et AppendURI. |
| Visiteur | Comptable | S.O. | Valeur unique de x-trackingid. Correspond généralement à un navigateur unique si des cookies persistants sont utilisés. x-trackingid peut être autrement basé sur le numéro d&#39;IP ou un autre identifiant unique tel que x.509 common name. |
| Semaine | Simple | Session | Semaine de la première entrée de journal d&#39;une session. |

Les dimensions du tableau suivant sont définies dans le répertoire des Dimensions du profil de trafic :

<table id="table_02AC8DAD1B62443A96FABCB75C37F23A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col03" class="entry"> Niveau </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Navigateur </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Visiteur </td> 
   <td colname="col3"> Type d’agent utilisateur utilisé par le visiteur, y compris le numéro de version (par exemple, MSIE 6.0). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Type de navigateur </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Visiteur </td> 
   <td colname="col3"> Type d’agent utilisateur utilisé par le visiteur (MSIE, par exemple). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Moteur de recherche </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03">Session <p>PREMIÈRE LIGNE </p></td> 
   <td colname="col3"> Premier moteur de recherche de la session d’un visiteur lorsqu’un visiteur a effectué une recherche à partir d’un moteur de recherche nommé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI suivant </td> 
   <td colname="col2"> Dérivé (ShiftDim basé sur la dimension URI) </td> 
   <td colname="col03"> Page vue </td> 
   <td colname="col3"> URI de l’URI suivant après l’URI actuellement sélectionné. Cette dimension dérivée est utilisée pour effectuer des analyses sur ce que font les visiteurs après une URI donnée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure unique ou Répéter </td> 
   <td colname="col2"> Dérivé (SegmentDim sur la base des mesures Visiteurs répétés et Visiteurs uniques) </td> 
   <td colname="col03"> Visiteur </td> 
   <td colname="col3"> Type de visiteur : unique ou répétée. Les visiteurs uniques n'ont eu qu'une seule session sur le site, tandis que les visiteurs récurrents ont eu plus d'une session. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page </td> 
   <td colname="col2"> Dérivé (RenameDim basé sur la dimension URI) </td> 
   <td colname="col03"> Page vue </td> 
   <td colname="col3"> Nom de chaque page visitée au cours d’une session. Au départ, le nom de chaque page est identique à celui de l’URI, mais il peut être modifié pour en faciliter l’interprétation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Référent </td> 
   <td colname="col2"> Hérité de la dimension de Parrain intégrée </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Nom de domaine de deuxième niveau du site Web qui a référencé une session pour la première fois sur le site (tel qu’il est fourni par le navigateur du visiteur). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expression de recherche </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03">Session <p>PREMIÈRE LIGNE </p></td> 
   <td colname="col3"> Première phrase de recherche dans la session d’un visiteur telle qu’elle est transmise par un moteur de recherche lorsqu’un visiteur a effectué une recherche à partir d’un moteur de recherche nommé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Terme de recherche </td> 
   <td colname="col2"> De plusieurs à plusieurs </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Chaque terme de recherche transmis par un moteur de recherche lorsqu'un visiteur dispose d'un clic publicitaire de parrain de recherche à partir d'un moteur de recherche nommé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée de la session </td> 
   <td colname="col2"> Dérivé (MetricDim basé sur la mesure Durée exacte de la page) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Durée d’une session par incréments de 30 secondes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numéro de session </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Nombre de fois où un visiteur a visité le site. Par exemple, les visiteurs pour la première fois ont un numéro de session "1", les visiteurs pour la deuxième fois un numéro de session "2", etc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vues de page de session </td> 
   <td colname="col2"> Dérivé (MetricDim basé sur la mesure Vues de page) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Nombre de vues de page dans une session. Par exemple, si vous sélectionnez "3" dans la dimension Vues de page de session, toutes les sessions comportant exactement 3 vues de page seront sélectionnées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Moteur de recherche </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Nom de domaine de deuxième niveau du premier site Web qui est un moteur de recherche nommé qui a référencé un visiteur sur le site au cours d’une session (tel que fourni par le navigateur du visiteur). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensions Heure </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Heure, jour, heure du jour, semaine, jour de la semaine, mois, trimestre ou année au cours desquels une session a commencé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensions de Rapports de temps </td> 
   <td colname="col2"> Dérivé (dimensions LastN et Renommer basées sur des dimensions temporelles intégrées) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Dimensions, y compris Jours du mois dernier, Jours de la semaine dernière, Jours de ce mois, Jours de cette semaine, Heures d'aujourd'hui, Heures d'hier, 12 derniers mois, 2 derniers mois, 2 dernières semaines, 2 dernières heures, 3 derniers mois, 4 dernières semaines, 6 derniers mois, 7 derniers jours, 7 derniers jours et aujourd'hui, 8 derniers mois, 9 dernières semaines, 9 dernières ceci, le mois dernier, la semaine dernière, les mois précédents, ce mois, cette semaine, ces 14 derniers jours, ces 6 derniers mois, ces 8 dernières semaines, aujourd'hui, le Rapports d'aujourd'hui, aujourd'hui et les 30 derniers jours, les semaines précédentes et hier constituent un moyen pratique de créer un espace de travail ou un rapport qui affiche toujours une partie des données dans le jeu de données. Chacun d’eux dépend du moment où a commencé une session. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> Hérité de l’URI de Dimension intégrée </td> 
   <td colname="col03"> Page vue </td> 
   <td colname="col3"> URI de chaque page consultée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vues de page visiteur </td> 
   <td colname="col2"> Dérivé (MetricDim basé sur la mesure Vues de page) </td> 
   <td colname="col03"> Visiteur </td> 
   <td colname="col3"> Nombre de vues de page à ce jour pour un visiteur. Par exemple, si vous sélectionnez "3" dans la dimension Vues de page du Visiteur, tous les visiteurs avec exactement 3 vues de page seront sélectionnés pour toutes leurs sessions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Référent du visiteur </td> 
   <td colname="col2"> Hérité du Parrain de dimensions intégré </td> 
   <td colname="col03"> Visiteur </td> 
   <td colname="col3"> Nom de domaine de deuxième niveau du site Web qui a d’abord renvoyé un Visiteur sur le site pour sa première session (tel que fourni par le navigateur du visiteur). </td> 
  </tr> 
 </tbody> 
</table>
