---
description: Liste des fichiers installés avec Insight Server et des fichiers présents après son enregistrement, et exécutés pour la première fois.
solution: Insight
title: Structure du répertoire du serveur Insight
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Structure du répertoire du serveur Insight{#insight-server-directory-structure}

Liste des fichiers installés avec Insight Server et des fichiers présents après son enregistrement, et exécutés pour la première fois.

## Fichiers inclus dans le package d’installation {#section-daec17dab3e34c3c9e1ef65842cb91f1}

Les répertoires suivants sont inclus dans le package [!DNL Insight Server] d’installation :

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Répertoire </th> 
   <th colname="col2" class="entry"> Description du contenu du répertoire </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Contrôle d'accès </td> 
   <td colname="col2"> <span class="keyword"> Fichier </span> de configuration du serveur Insight qui spécifie une liste de groupes d’accès. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresses </td> 
   <td colname="col2"> Adresse(s) utilisée(s) pour la communication avec <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Audit </td> 
   <td colname="col2"> Journaux d’accès quotidiens contenant des détails sur toutes les tentatives de connexion à <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Fichiers programme </span> exécutables du serveur Insight. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificats </td> 
   <td colname="col2"> Certificats numériques SSL. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Composants </td> 
   <td colname="col2"> <span class="keyword"> Fichiers de configuration </span> du composant Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Composants pour les serveurs de traitement </td> 
   <td colname="col2"> <span class="keyword"> Fichiers de configuration du </span> composant Insight Server pour le traitement des serveurs <span class="keyword"> Insight </span> dans une <span class="keyword"> grappe de serveurs </span> Insight. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événements </td> 
   <td colname="col2"> Journaux d’événements quotidiens contenant des messages détaillés sur l’état des événements, y compris des messages d’erreur. Les événements capturés et consignés par <span class="keyword"> Insight Server </span> s’affichent également dans l’Observateur d’événements Windows. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Journaux </td> 
   <td colname="col2"> <p>Fichiers journaux produits par <span class="wintitle"> Sensor </span>(s). </p> <p>"Journaux" est le répertoire de journalisation par défaut, mais un autre répertoire a peut-être été spécifié dans le fichier <span class="filepath"> .cfg </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recherches </td> 
   <td colname="col2"> Fichiers de recherche, tels que les listes de robots et de moteurs de recherche. <span class="keyword"> Insight Server </span> doit charger tous les fichiers de recherche en mémoire. La taille totale de tous les fichiers de recherche référencés dans les fichiers de configuration des composants, plus la surcharge (par exemple, 12 octets par ligne pour les <span class="filepath"> fichiers FlatFileLookup </span> ), ne doit pas dépasser la mémoire physique ou virtuelle disponible une fois toutes les autres applications logicielles chargées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profils </td> 
   <td colname="col2"> <p>Fichiers associés à chaque profil (fichiers de configuration, d’espace de travail et de visualisation). Les profils sont renseignés par les données d’un jeu de données. Les jeux de données comprennent des données d'événement ("données de journal"); ces données peuvent être capturées par <span class="wintitle"> des capteurs installés </span>, transmises par des balises Web ou des balises de page, ou saisies à partir d’entrepôts de données. <span class="keyword"> Les </span> utilisateurs d’Insight ayant accès à un profil donné peuvent utiliser l’ensemble de données traitées pour ce profil, ainsi que les espaces de travail et les visualisations définis dans ce profil. </p> <p>Les espaces de travail sont des zones de travail pour l’administration ou l’analyse du système. Un espace de travail peut contenir plusieurs interfaces présentant différents détails sur les performances du système. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Logiciel </td> 
   <td colname="col2"> <span class="keyword"> Mises à jour </span> du logiciel Insight. Les mises à jour des logiciels de rapports sont également stockées ici. </td> 
  </tr> 
 </tbody> 
</table>

## Répertoires et fichiers créés après le démarrage {#section-ef7408e8fae64454b326ec07453d4628}

Les répertoires répertoriés ci-dessous sont créés après [!DNL Insight Server] l’enregistrement et l’exécution initiale :

<table id="table_89CC9F3E568044C8A0072BF0A6EDCCEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Répertoire </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> État </td> 
   <td colname="col2"> Traitement des informations générées par <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Température </td> 
   <td colname="col2"> <p>Emplacement des fichiers temporaires utilisés par <span class="keyword"> Insight Server </span> pendant le retraitement et le fonctionnement. Il existe généralement un fichier (nommé <span class="filepath"> temp.db </span> par défaut) par lecteur physique. </p> <p> <span class="keyword"> Insight Server </span> doit être configuré pour écrire dans ce répertoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tracé </td> 
   <td colname="col2"> Données de journal et d’événement sur <span class="keyword"> Insight Server </span>. Utile pour le dépannage. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utilisateurs </td> 
   <td colname="col2"> Utilisateurs nommés ( <span class="keyword"> Insight </span>) ayant accès aux profils sur le serveur. Un répertoire pour chaque utilisateur nommé autorisé est créé dans le répertoire Utilisateurs\ lorsque l’utilisateur accède pour la première fois au serveur <span class="keyword"> Insight </span> via <span class="keyword"> Insight </span>. Le répertoire de chaque utilisateur nommé contient des répertoires correspondant à tous les profils auxquels l’utilisateur a accédé sur ce serveur <span class="keyword"> Insight </span> ainsi que leurs fichiers d’adresse locaux. </td> 
  </tr> 
 </tbody> 
</table>

