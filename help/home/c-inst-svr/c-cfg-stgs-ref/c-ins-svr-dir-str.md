---
description: Liste des fichiers installés avec Insight Server et des fichiers présents après son enregistrement, et exécutés pour la première fois.
title: Structure du répertoire du serveur Insight
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---

# Structure du répertoire du serveur Insight{#insight-server-directory-structure}

Liste des fichiers installés avec Insight Server et des fichiers présents après son enregistrement, et exécutés pour la première fois.

## Fichiers inclus dans le package d’installation {#section-daec17dab3e34c3c9e1ef65842cb91f1}

Les répertoires suivants sont inclus dans le package d’installation de [!DNL Insight Server] :

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Répertoire </th> 
   <th colname="col2" class="entry"> Description du contenu du répertoire </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Contrôle d’accès </td> 
   <td colname="col2"> <span class="keyword"> Fichier  </span> de configuration du serveur Insight qui spécifie une liste de groupes d’accès. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresses </td> 
   <td colname="col2"> Adresse(s) utilisée(s) pour la communication avec <span class="keyword"> le serveur Insight </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Audit </td> 
   <td colname="col2"> Journaux d’accès quotidiens contenant des détails sur toutes les tentatives de connexion à <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Fichiers de programme  </span> exécutables du serveur Insight. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificats </td> 
   <td colname="col2"> Certificats numériques SSL. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Composants </td> 
   <td colname="col2"> <span class="keyword"> Fichiers de configuration  </span> du composant Serveur Insight. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Composants des serveurs de traitement </td> 
   <td colname="col2"> <span class="keyword"> Fichiers de configuration  </span> du composant Insight Server pour le traitement des serveurs  <span class="keyword"> Insight  </span> dans une  <span class="keyword"> grappe  </span> Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événements </td> 
   <td colname="col2"> Journaux des événements quotidiens contenant des messages détaillés sur l’état des événements, y compris les messages d’erreur. Les événements capturés et consignés par <span class="keyword"> le serveur Insight </span> s’affichent également dans la visionneuse d’événements Windows. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Journaux </td> 
   <td colname="col2"> <p>Fichiers journaux générés par <span class="wintitle"> Capteur </span>(s). </p> <p>"Journaux" est le répertoire de journalisation par défaut, mais un autre répertoire peut avoir été spécifié dans le fichier <span class="filepath"> communications.cfg </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recherches </td> 
   <td colname="col2"> Les fichiers de recherche, tels que les listes de robots et de moteurs de recherche. <span class="keyword"> Insight Server  </span> doit charger tous les fichiers de recherche en mémoire. La taille totale de tous les fichiers de recherche référencés dans les fichiers de configuration de composant, plus la surcharge (par exemple, 12 octets par ligne pour les fichiers <span class="filepath"> FlatFileLookup </span>), ne doit pas dépasser la mémoire physique ou virtuelle disponible une fois toutes les autres applications logicielles chargées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profils </td> 
   <td colname="col2"> <p>Fichiers associés à chaque profil (fichiers de configuration, d’espace de travail et de visualisation). Les profils sont renseignés par les données d’un jeu de données. Les jeux de données incluent des données d’événement ("Données du journal") ; ces données peuvent être capturées par les capteurs <span class="wintitle"> installés </span>, transmis par les balises Web ou les balises de page, ou par l’entrée des entrepôts de données. <span class="keyword"> Les  </span> utilisateurs d’Insight ayant accès à un profil donné peuvent utiliser l’ensemble de données traitées pour ce profil, ainsi que les Espaces de travail et les visualisations définis dans ce profil. </p> <p>Les espaces de travail sont des zones de travail pour l’administration ou l’analyse du système. Un espace de travail peut contenir plusieurs interfaces présentant différents détails sur les performances du système. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Logiciels </td> 
   <td colname="col2"> <span class="keyword"> Mises à jour  </span> du logiciel Insight. Les mises à jour des logiciels de rapports sont également stockées ici. </td> 
  </tr> 
 </tbody> 
</table>

## Répertoires et fichiers créés après le démarrage {#section-ef7408e8fae64454b326ec07453d4628}

Les répertoires répertoriés ci-dessous sont créés après l’enregistrement de [!DNL Insight Server] et l’exécution pour la première fois :

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
   <td colname="col2"> Informations de traitement générées par <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p>Emplacement des fichiers temporaires utilisés par <span class="keyword"> le serveur Insight </span> lors du retraitement et du fonctionnement. Il existe généralement un fichier (nommé <span class="filepath"> temp.db </span> par défaut) par disque physique. </p> <p> <span class="keyword"> Insight Server  </span> doit être configuré pour écrire dans ce répertoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trace </td> 
   <td colname="col2"> Enregistrer les données d’événement et de journal sur <span class="keyword"> le serveur Insight </span>. Utile à la résolution des problèmes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utilisateurs </td> 
   <td colname="col2"> Utilisateurs nommés ( <span class="keyword"> Insight </span>) ayant accès aux profils sur le serveur. Un répertoire pour chaque utilisateur nommé autorisé est créé dans l’annuaire Users\ lorsque l’utilisateur accède pour la première fois à <span class="keyword"> Insight Server </span> via <span class="keyword"> Insight </span>. Le répertoire de chaque utilisateur nommé contient les répertoires correspondant à tous les profils auxquels l’utilisateur a accédé sur ce <span class="keyword"> serveur Insight </span> ainsi que leurs fichiers d’adresses locaux. </td> 
  </tr> 
 </tbody> 
</table>
