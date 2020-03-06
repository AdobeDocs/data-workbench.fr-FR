---
description: Le profil Trafic contient les dimensions suivantes pour aider à identifier les actions des visiteurs.
solution: Analytics
title: Dimensions du profil de trafic
topic: Data workbench
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensions du profil de trafic{#traffic-profile-dimensions}

Le profil Trafic contient les dimensions suivantes pour aider à identifier les actions des visiteurs.

Les dimensions du tableau suivant sont définies dans le jeu de données de transformation et comprennent des fichiers dans le dossier Traffic\Dataset\Transformation directory.

| Nom | Type | Niveau | Description |
|---|---|---|---|
| Jour | Simple | Session | Jour de la première entrée de journal de la session. |
| Jour de la semaine | Simple | Session | Jour de la semaine de la première entrée de journal d’une session. |
| Durée exacte de la page (masquée) | Numérique | Page vue | Durée, en millisecondes, de la page vue, mesurée en soustrayant le temps de la page vue suivante du temps de cette page vue. La durée exacte de la dernière page vue d’une session est toujours 0. |
| Heure | Simple | Session | Heure de la première entrée de journal d’une session. |
| Heure du jour | Simple | Session | Heure du jour de la première entrée de journal d&#39;une session. |
| Mois | Simple | Session | Mois de la première entrée de journal d’une session. |
| Page vue | Comptable | Session | Entrée de journal ou &quot;Enregistrement de données d’événement&quot; satisfaisant à la condition Page vue. |
| Référent | Simple | Session | Domaine de second niveau du référent de la première entrée de journal de la session (ou Aucun s’il s’agit d’un domaine référent interne). |
| Session | Comptable | Visitor | Période d’activité contiguë associée par un visiteur. Elle est délimitée par une période d’inactivité de 30 minutes et un domaine référent externe ou une durée de session maximale de 48 heures. Ces expirations de délai et le jeu de domaines considérés comme internes peuvent être configurés dans le [!DNL Transformation.cfg] fichier. |
| URI | Simple | Page vue | La racine URI d’une page vue. La dimension URI peut être redéfinie à l’aide des transformations ReplaceURI, PrependURI et AppendURI. |
| Visitor | Comptable | S.O. | Valeur unique de x-trackingid. Correspond généralement à un navigateur unique si des cookies persistants sont utilisés. x-trackingid peut être basé sur le numéro d&#39;IP ou un autre identifiant unique, tel que le nom commun x.509. |
| Semaine | Simple | Session | Semaine de la première entrée de journal d’une session. |

Les dimensions du tableau suivant sont définies dans le répertoire Dimension du profil Trafic :

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
   <td colname="col03"> Visitor </td> 
   <td colname="col3"> Type d’agent utilisateur utilisé par le visiteur, y compris le numéro de version (par exemple, MSIE 6.0). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Type de navigateur </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Visitor </td> 
   <td colname="col3"> Type d’agent utilisateur utilisé par le visiteur (MSIE, par exemple). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Moteur de recherche </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03">Session <p>PREMIÈRE LIGNE </p></td> 
   <td colname="col3"> Premier moteur de recherche de la session d’un visiteur lorsqu’il a effectué une recherche à partir d’un moteur de recherche nommé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI suivant </td> 
   <td colname="col2"> Dérivé (ShiftDim basé sur la dimension URI) </td> 
   <td colname="col03"> Page vue </td> 
   <td colname="col3"> URI de l’URI suivant après l’URI actuellement sélectionné. Cette dimension dérivée est utilisée pour effectuer une analyse sur ce que les visiteurs font après un URI donné. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure unique ou Répéter </td> 
   <td colname="col2"> Dérivé (SegmentDim basé sur les mesures Visiteurs récurrents et Visiteurs uniques) </td> 
   <td colname="col03"> Visitor </td> 
   <td colname="col3"> Type de visiteur : une fois ou une fois. Les visiteurs uniques n’ont eu qu’une seule session sur le site, tandis que les visiteurs de retour ont eu plusieurs sessions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> Dérivé (RenameDim basé sur la dimension URI) </td> 
   <td colname="col03"> Page vue </td> 
   <td colname="col3"> Nom de chaque page visitée au cours d’une session. Au départ, le nom de chaque page est identique à celui de l’URI, mais il est possible de le modifier pour faciliter l’interprétation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Référent </td> 
   <td colname="col2"> Hérité de la dimension Référent intégrée </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Nom de domaine de second niveau du site Web qui a d’abord référé une session au site (tel qu’il est fourni par le navigateur du visiteur). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expression de recherche </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03">Session <p>PREMIÈRE LIGNE </p></td> 
   <td colname="col3"> Première phrase de recherche dans la session d’un visiteur telle qu’elle est transmise par un moteur de recherche lorsqu’un visiteur a effectué une recherche à partir d’un moteur de recherche nommé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Terme de recherche </td> 
   <td colname="col2"> Plusieurs à plusieurs </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Chaque terme de recherche transmis par un moteur de recherche lorsqu'un visiteur a un clic publicitaire à partir d'un moteur de recherche nommé. </td> 
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
   <td colname="col3"> Nombre de visites d’un visiteur sur le site. Par exemple, les nouveaux visiteurs ont un numéro de session "1", les nouveaux visiteurs ont un numéro de session "2", etc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pages vues de la session </td> 
   <td colname="col2"> Dérivé (MetricDim basé sur la mesure Pages vues) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Nombre de pages vues dans une session. Par exemple, la sélection de "3" dans la dimension Pages vues de la session sélectionnerait toutes les sessions avec exactement 3 pages vues. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Moteur de recherche </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Nom de domaine de deuxième niveau du premier site Web qui est un moteur de recherche nommé qui a renvoyé un visiteur sur le site au cours d’une session (tel qu’il est fourni par le navigateur du visiteur). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensions Heure </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Heure, jour, heure du jour, semaine, jour de la semaine, mois, trimestre ou année au cours desquels une session a commencé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensions des rapports de temps </td> 
   <td colname="col2"> Dérivé (dimensions LastN et Renommer en fonction des dimensions temporelles intégrées) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Dimensions, y compris Jours auparavant, Jours du mois dernier, Jours de la semaine dernière, Jours de ce mois, Jours de cette semaine, Heures d'aujourd'hui, Heures d'hier, 12 derniers mois, 2 derniers mois, 2 dernières semaines, 24 dernières heures, 3 derniers mois, 4 dernières semaines, 6 derniers mois, 7 derniers jours, 7 derniers jours et aujourd'hui, 8 dernières semaines, 9 dernières semaines, Les mois, le mois dernier, la semaine dernière, les mois précédents, ce mois, cette semaine, ces 14 derniers jours, ces 6 derniers mois, ces 8 dernières semaines, aujourd’hui, les rapports d’aujourd’hui, aujourd’hui et les 30 derniers jours, les semaines précédentes et hier constituent un moyen pratique de créer un espace de travail ou un rapport qui affiche toujours une partie des données dans le jeu de données. Chacun d’eux est basé sur le moment où une session a commencé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> Hérité de l’URI de dimension intégré </td> 
   <td colname="col03"> Page vue </td> 
   <td colname="col3"> URI de chaque page affichée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pages vues des visiteurs </td> 
   <td colname="col2"> Dérivé (MetricDim basé sur la mesure Pages vues) </td> 
   <td colname="col03"> Visitor </td> 
   <td colname="col3"> Nombre de pages vues à ce jour pour un visiteur. Par exemple, la sélection de "3" dans la dimension Pages vues des visiteurs sélectionnerait tous les visiteurs avec exactement 3 pages vues sur l’ensemble de leurs sessions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Référent du visiteur </td> 
   <td colname="col2"> Hérité du référent de dimension intégré </td> 
   <td colname="col03"> Visitor </td> 
   <td colname="col3"> Nom de domaine de deuxième niveau du site Web qui a d’abord renvoyé un visiteur sur le site pour sa première session (tel qu’il est fourni par le navigateur du visiteur). </td> 
  </tr> 
 </tbody> 
</table>

