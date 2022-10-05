---
description: Le profil Trafic contient les dimensions suivantes pour identifier les actions des visiteurs.
title: Dimensions du profil de trafic
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
exl-id: 1e7d2904-aa5d-4848-a398-5d4669953be9
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 8%

---

# Dimensions du profil de trafic{#traffic-profile-dimensions}

{{eol}}

Le profil Trafic contient les dimensions suivantes pour identifier les actions des visiteurs.

Les dimensions du tableau suivant sont définies dans le jeu de données de transformation ; elles incluent des fichiers dans le répertoire Trafic\Jeu de données\Transformation .

| Nom | Type | Niveau | Description |
|---|---|---|---|
| Jour | Simple | Session | Jour de la première entrée de journal de la session. |
| Jour de la semaine | Simple | Session | Jour de la semaine de la première entrée de journal d’une session. |
| Durée exacte de la page (masquée) | Numérique | Page vue | Durée en millisecondes de page vue telle que mesurée en soustrayant l’heure de la page vue suivante de l’heure de cette page vue. La durée exacte de la dernière page vue d’une session est toujours 0. |
| Heure  | Simple | Session | Heure de la première entrée de journal d’une session. |
| Heure de la journée | Simple | Session | Heure de la journée de la première entrée de journal d’une session. |
| Mois | Simple | Session | Mois de la première entrée de journal d’une session. |
| Page vue | dénombrable | Session | Une entrée de journal ou un &quot;enregistrement de données d’événement&quot; satisfaisant la condition de page vue. |
| Référent | Simple | Session | Domaine de deuxième niveau du référent de la première entrée de journal de la session (ou Aucun s’il s’agit d’un domaine de référent interne). |
| Session | dénombrable | Visiteur | Période d’activité contiguë associée par un visiteur. Elle est délimitée par une période d’inactivité de 30 minutes et un domaine référent externe ou une durée de session de 48 heures au maximum. Ces deux expirations et l’ensemble des domaines considérés comme internes peuvent être configurés dans la variable [!DNL Transformation.cfg] fichier . |
| URI | Simple | Page vue | La racine URI d’une page vue. La dimension URI peut être redéfinie à l’aide des transformations ReplaceURI, PrependURI et AppendURI. |
| Visiteur | dénombrable | S.O. | Valeur unique de x-trackingid. Correspond généralement à un navigateur unique si des cookies persistants sont utilisés. Le x-trackingid peut être sinon basé sur le numéro IP ou un autre identifiant unique tel que le nom commun x.509. |
| Semaine | Simple | Session | La semaine de la première entrée de journal d’une session. |

Les dimensions du tableau suivant sont définies dans le répertoire des Dimensions du profil Trafic :

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
   <td colname="col3"> Type d’agent utilisateur utilisé par le visiteur (par exemple, MSIE). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Moteur de recherche  </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03">Session <p>PREMIÈRE LIGNE </p></td> 
   <td colname="col3"> Premier moteur de recherche de la session d’un visiteur lorsqu’un visiteur a effectué une recherche à partir d’un moteur de recherche nommé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI suivant </td> 
   <td colname="col2"> Dérivé (ShiftDim selon la dimension URI) </td> 
   <td colname="col03"> Page vue </td> 
   <td colname="col3"> URI de l’URI suivant après l’URI actuellement sélectionné. Cette dimension dérivée est utilisée pour effectuer une analyse sur les actions des visiteurs après un URI donné. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure d’ouverture et Répétition </td> 
   <td colname="col2"> Dérivés (SegmentDim basé sur les mesures Visiteurs récurrents et Visiteurs uniques) </td> 
   <td colname="col03"> Visiteur </td> 
   <td colname="col3"> Type de visiteur : une ou une répétition. Les visiteurs uniques n’ont eu qu’une seule session sur le site, tandis que les visiteurs réguliers ont eu plusieurs sessions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page </td> 
   <td colname="col2"> Dérivé (RenameDim selon la dimension URI) </td> 
   <td colname="col03"> Page vue </td> 
   <td colname="col3"> Nom de chaque page visitée au cours d’une session. Au départ, le nom de chaque page est identique à l’URI, mais il peut être modifié pour en faciliter l’interprétation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Référent </td> 
   <td colname="col2"> Hérité de la dimension Référent intégrée </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Nom de domaine de deuxième niveau du site web qui a d’abord référé une session au site (tel qu’il est fourni par le navigateur du visiteur). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expression de recherche </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03">Session <p>PREMIÈRE LIGNE </p></td> 
   <td colname="col3"> Première expression de recherche dans la session d’un visiteur telle qu’elle est transmise par un moteur de recherche lorsqu’un visiteur a effectué une recherche à partir d’un moteur de recherche nommé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Terme de recherche </td> 
   <td colname="col2"> Multiple-à-multiple </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Chaque terme de recherche transmis par un moteur de recherche lorsqu’un visiteur a un clic publicitaire sur un référent de recherche à partir d’un moteur de recherche nommé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée de la session </td> 
   <td colname="col2"> Dérivés (MetricDim selon la mesure Durée exacte de la page) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Durée d’une session par incréments de 30 secondes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numéro de session </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Nombre de visites d’un visiteur sur le site. Par exemple, les nouveaux visiteurs ont un numéro de session "1", les nouveaux visiteurs ont un numéro de session "2", etc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pages vues de session </td> 
   <td colname="col2"> Dérivés (MetricDim selon la mesure Pages vues) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Nombre de pages vues dans une session. Par exemple, si vous sélectionnez "3" dans la dimension Pages vues de session, toutes les sessions avec exactement 3 pages vues sont sélectionnées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Moteur de recherche  </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Nom de domaine de deuxième niveau du premier site web qui est un moteur de recherche nommé qui a renvoyé un visiteur sur le site au cours d’une session (tel qu’il est fourni par le navigateur du visiteur). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensions Heure </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Heure, jour, heure du jour, semaine, jour de la semaine, du mois, du trimestre ou de l’année au cours duquel une session a commencé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensions de création de rapports sur le temps </td> 
   <td colname="col2"> Dimensions dérivées (Dernière heure et Renommer selon des dimensions temporelles intégrées) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Dimensions incluant : Jours il y a, Jours du mois dernier, Jours de la semaine dernière, Jours de ce mois, Jours de cette semaine, Heures d’aujourd’hui, Heures d’hier, 12 derniers mois, 2 derniers mois, 2 dernières semaines, 24 dernières heures, 3 derniers mois, 4 dernières semaines, 6 derniers mois, 7 derniers jours, 7 derniers jours et aujourd’hui, 8 dernières semaines, 9 dernières ceci, le mois dernier, la semaine dernière, les mois précédents, ce mois, cette semaine, ces 14 derniers jours, ces et ces 6 derniers mois, ces et 8 dernières semaines, aujourd’hui, les rapports d’aujourd’hui, aujourd’hui et les 30 derniers jours, les semaines précédentes et hier fournissent un moyen pratique de créer un espace de travail ou un rapport qui affiche toujours une partie des données dans le jeu de données. Chacun d’eux dépend du moment où a commencé une session. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> Hérité de l’URI de Dimension intégré </td> 
   <td colname="col03"> Page vue </td> 
   <td colname="col3"> L’URI de chaque page affichée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pages vues du visiteur </td> 
   <td colname="col2"> Dérivés (MetricDim selon la mesure Pages vues) </td> 
   <td colname="col03"> Visiteur </td> 
   <td colname="col3"> Nombre de pages vues à ce jour pour un visiteur. Par exemple, si vous sélectionnez "3" dans la dimension Pages vues du visiteur, tous les visiteurs avec exactement 3 pages vues au cours de toutes leurs sessions seront sélectionnés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Référent du visiteur </td> 
   <td colname="col2"> Hérité du référent de dimension intégré </td> 
   <td colname="col03"> Visiteur </td> 
   <td colname="col3"> Nom de domaine de deuxième niveau du site web qui a d’abord renvoyé un visiteur sur le site pour sa première session (tel qu’il est fourni par le navigateur du visiteur). </td> 
  </tr> 
 </tbody> 
</table>
