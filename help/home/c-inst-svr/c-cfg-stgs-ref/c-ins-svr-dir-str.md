---
description: Liste des fichiers installés avec Insight Server et des fichiers présents après son enregistrement, et exécutés pour la première fois.
title: Structure du répertoire du serveur Insight
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# Structure du répertoire du serveur Insight{#insight-server-directory-structure}

{{eol}}

Liste des fichiers installés avec Insight Server et des fichiers présents après son enregistrement, et exécutés pour la première fois.

## Fichiers inclus dans le package d’installation {#section-daec17dab3e34c3c9e1ef65842cb91f1}

Les répertoires suivants sont inclus dans la variable [!DNL Insight Server] package d’installation :

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
   <td colname="col2"> <span class="keyword"> Serveur Insight </span> fichier de configuration qui spécifie une liste de groupes d’accès. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresses </td> 
   <td colname="col2"> Adresse(s) utilisée(s) pour la communication avec <span class="keyword"> Serveur Insight </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Audit </td> 
   <td colname="col2"> Journaux d’accès quotidiens contenant des détails sur toutes les tentatives de connexion à <span class="keyword"> Serveur Insight </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Serveur Insight </span> fichiers de programme exécutables. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificats </td> 
   <td colname="col2"> Certificats numériques SSL. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Composants </td> 
   <td colname="col2"> <span class="keyword"> Serveur Insight </span> fichiers de configuration des composants. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Composants des serveurs de traitement </td> 
   <td colname="col2"> <span class="keyword"> Serveur Insight </span> fichiers de configuration de composant pour le traitement <span class="keyword"> Serveurs Insight </span> dans <span class="keyword"> Serveur Insight </span> grappe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événements </td> 
   <td colname="col2"> Journaux des événements quotidiens contenant des messages détaillés sur l’état des événements, y compris les messages d’erreur. Événements capturés et consignés <span class="keyword"> Serveur Insight </span> s’affichent également dans la visionneuse d’événements Windows. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Journaux </td> 
   <td colname="col2"> <p>Fichiers journaux générés par <span class="wintitle"> Sensor </span>(s). </p> <p>"Journaux" est le répertoire de journalisation par défaut, mais un autre répertoire peut avoir été spécifié dans la variable <span class="filepath"> communications.cfg </span> fichier . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recherches </td> 
   <td colname="col2"> Les fichiers de recherche, tels que les listes de robots et de moteurs de recherche. <span class="keyword"> Serveur Insight </span> doit charger tous les fichiers de recherche en mémoire. Taille totale de tous les fichiers de recherche référencés dans les fichiers de configuration de composant, plus la surcharge (par exemple, 12 octets par ligne pour <span class="filepath"> FlatFileLookup </span> ) ne doit pas excéder la mémoire physique ou virtuelle disponible après le chargement de toutes les autres applications logicielles. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profils </td> 
   <td colname="col2"> <p>Fichiers associés à chaque profil (fichiers de configuration, d’espace de travail et de visualisation). Les profils sont renseignés par les données d’un jeu de données. Les jeux de données incluent des données d’événement ("Données du journal") ; ces données peuvent être capturées par installé <span class="wintitle"> Capteurs </span>, transmis par les balises Web ou de page, ou par la saisie depuis les entrepôts de données. <span class="keyword"> Insight </span> les utilisateurs ayant accès à un profil donné peuvent utiliser l’ensemble de données traitées pour ce profil, ainsi que les Espaces de travail et les visualisations définis dans ce profil. </p> <p>Les espaces de travail sont des zones de travail pour l’administration ou l’analyse du système. Un espace de travail peut contenir plusieurs interfaces présentant différents détails sur les performances du système. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Logiciels </td> 
   <td colname="col2"> <span class="keyword"> Insight </span> mises à jour des logiciels. Les mises à jour des logiciels de rapports sont également stockées ici. </td> 
  </tr> 
 </tbody> 
</table>

## Répertoires et fichiers créés après le démarrage {#section-ef7408e8fae64454b326ec07453d4628}

Les répertoires répertoriés ci-dessous sont créés après [!DNL Insight Server] est enregistré et exécuté pour la première fois :

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
   <td colname="col2"> Informations de traitement générées par <span class="keyword"> Serveur Insight </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p>Emplacement des fichiers temporaires utilisés par <span class="keyword"> Serveur Insight </span> pendant le retraitement et l’opération. Il existe généralement un fichier (nommé <span class="filepath"> temp.db </span> par défaut) par lecteur physique. </p> <p> <span class="keyword"> Serveur Insight </span> doit être configuré pour écrire dans ce répertoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trace </td> 
   <td colname="col2"> Données de journal et d’événement relatives à <span class="keyword"> Serveur Insight </span>. Utile à la résolution des problèmes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utilisateurs </td> 
   <td colname="col2"> Nommé ( <span class="keyword"> Insight </span>) les utilisateurs ayant accès aux profils sur le serveur. Un répertoire pour chaque utilisateur nommé autorisé est créé dans l’annuaire Users\ lorsque l’utilisateur accède pour la première fois à <span class="keyword"> Serveur Insight </span> via <span class="keyword"> Insight </span>. Le répertoire de chaque utilisateur nommé contient les répertoires correspondant à tous les profils auxquels l’utilisateur a accédé. <span class="keyword"> Serveur Insight </span> ainsi que leurs fichiers d’adresse locaux. </td> 
  </tr> 
 </tbody> 
</table>
