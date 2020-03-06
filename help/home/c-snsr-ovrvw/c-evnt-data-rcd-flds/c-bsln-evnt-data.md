---
description: Informations sur les champs d’enregistrement de données d’événement de ligne de base tels qu’ils ont été enregistrés par Sensor.
solution: Insight
title: Champs d’enregistrement des données d’événement de ligne de base
uuid: aa36d332-089c-4ae2-98e2-a93d2fa023b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Champs d’enregistrement des données d’événement de ligne de base{#baseline-event-data-record-fields}

Informations sur les champs d’enregistrement de données d’événement de ligne de base tels qu’ils ont été enregistrés par Sensor.

<table id="table_E29606BB010E4DB48C463979B7BEC769"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> <p>Adresse IP du client telle qu’elle est incluse dans la requête envoyée au serveur. </p> <p>Exemple : 207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>Cookies envoyés par le client avec la requête. </p> <p>Exemple : v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAEPM; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> <p>Chaîne de référent HTTP envoyée par le client au serveur avec la requête. </p> <p>Exemple : http://www.mysite.net/cgi-bin/websearch?qry </p> <p>Si vous utilisez des balises de page, cs(referrer) est l’URL complète du document contenant l’image de la balise, y compris HTTP ou HTTP. </p> <p>Vous pouvez également configurer les capteurs Apache (1.3, 2.0 et 2.2) et IIS pour capturer le port utilisé pour la requête, qui peut identifier les requêtes HTTP et HTTPS. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>Chaîne envoyée par le client avec sa requête au serveur qui indique le type d’agent utilisateur du client. </p> <p>Exemple : Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>Type de méthode de la requête HTTP </p> <p>Exemple : GET </p> <p>Référence : http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>Partie de chaîne de requête de l'URI (racine + chaîne de requête = URI) </p> <p>Ce point est précédé d’un point d’interrogation (?) et peut contenir une ou plusieurs paires nom-valeur séparées par des esperluettes (&amp;). </p> <p>Exemple : page=page d’accueil </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> <p>Partie racine de l’URI (racine + chaîne de requête = URI) </p> <p>La racine est le chemin réel ou logique vers la ressource demandée sur le serveur. </p> <p>Exemple : /index.asp </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>Type de contenu de la ressource demandée par le client tel que rapporté par le serveur. </p> <p>Exemples : text/html, image/png, image/gif, vidéo/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>Nombre d’octets de données envoyés du serveur au client en réponse à la demande. </p> <p>Exemple : 4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>Code d’état renvoyé au client par le serveur. </p> <p>Exemple : 200 </p> <p>Référence : http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>Nom de domaine complet ou adresse IP de l’hôte de la ressource demandée. </p> <p>Exemple : www.omniture.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-experience </td> 
   <td colname="col2"> <p>Liste de tous les noms et groupes d’expériences contrôlés auxquels le client est membre au moment de la demande. </p> <p>Exemple : Home_Exp.Group_1,Registration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>Date et heure (GMT) auxquelles la demande a été reçue par le serveur. </p> <p>Le temps est exprimé sous la forme du nombre de 100 nanosecondes depuis le 1er janvier 1600. </p> <p>Exemple : Le mardi 13 septembre 2005, 127710989320000000 correspond à la valeur de l’horodatage X pour 11:28:52.0000000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>Valeur hexadécimale 64 bits de l’identificateur de navigateur unique détecté dans un cookie persistant tel qu’il est défini par un <span class="wintitle"> capteur </span> et fourni par le client avec une requête à un serveur. </p> <p>Exemple : 42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

Il [!DNL data workbench server] peut dériver un certain nombre de variables des champs d’enregistrement de données d’événement de ligne de base. For more information, see the *Dataset Configuration Guide*.
