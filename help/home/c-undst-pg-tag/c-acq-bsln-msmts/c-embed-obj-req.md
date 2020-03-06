---
description: Une fois que le code HTML d’une page est demandé par un navigateur, celui-ci demande aux objets incorporés référencés dans le code HTML de cette page de remplir la page affichée par le navigateur.
solution: Analytics
title: Acquisition de requêtes d’objet incorporées (balises de page)
topic: Data workbench
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Acquisition de requêtes d’objet incorporées (balises de page){#acquiring-embedded-object-requests-page-tags}

Une fois que le code HTML d’une page est demandé par un navigateur, celui-ci demande aux objets incorporés référencés dans le code HTML de cette page de remplir la page affichée par le navigateur.

Ces requêtes d’objets incorporés sont généralement des requêtes de fichiers d’image ou de fichiers JavaScript, bien qu’il existe aujourd’hui des centaines, voire des milliers de types d’objets incorporés utilisés sur Internet. La plupart de ces demandes d&#39;objets incorporés ne sont généralement pas utiles pour analyser l&#39;activité commerciale d&#39;un site Internet ou pour créer des rapports à ce sujet; de nombreuses demandes de ce type ne sont donc pas souhaitables pour l&#39;acquisition à moins qu&#39;elles n&#39;aient un objectif commercial spécifique, comme la présentation d&#39;une publicité ou la prise d&#39;une autre mesure de l&#39;activité du site.

Par exemple, une image peut être une annonce publicitaire et vous souhaitez peut-être savoir que la publicité a été impressionnée par un visiteur. Un extrait de code JavaScript peut être utilisé pour prendre une mesure indiquant que le navigateur particulier possède une certaine caractéristique et la transmettre à un [!DNL Sensor] pour acquisition. Chaque page d’un site peut comporter 10 ou 100 requêtes d’objet incorporées. Si un site stocke les informations du journal pour chacune de ces requêtes, la quantité de stockage de données nécessaire pour conserver les données du journal disponibles pour une analyse ultérieure est multipliée par le nombre de requêtes d’objet incorporées pour chaque page demandée. C’est pourquoi [!DNL Site] vous permet de conserver les requêtes importantes pour l’analyse et d’en ignorer d’autres avant d’engager des coûts de stockage inutiles.

En utilisant la fonction de remplacement fournie dans les fonctionnalités de filtrage de type de contenu de [!DNL Sensor] (en ajoutant &quot;Log=1&quot; à la chaîne de requête d’une URL de requête d’objet incorporé), cette requête d’objet incorporé spécifique et les données de mesure associées peuvent être acquises sans que le gestionnaire de site ne stocke toutes les requêtes de ce type (par exemple, toutes les requêtes de ce type). <image> ).

[!DNL Sensor] collecte les données de mesure dans le tableau suivant pour chaque requête d’objet incorporée effectuée à partir du serveur Web, en supposant que [!DNL Sensor] n’est pas configuré pour le filtrer ou que le filtre a été remplacé. Les informations collectées sont liées au visiteur et à la session, ainsi qu’aux sessions suivantes, par le biais des entrées de champ de journal x-trackingid ou cs(cookie).

<table id="table_11BE08A798E743EC8E76F738F0CE5884"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom W3C </th> 
   <th colname="col2" class="entry"> Données collectées </th> 
   <th colname="col3" class="entry"> Description </th> 
   <th colname="col4" class="entry"> Exemple </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> Identifiant de suivi (visiteur unique) </td> 
   <td colname="col3"> Identifiant lu à partir d’un cookie placé dans le navigateur de l’utilisateur par <span class="wintitle"> Sensor </span> sur demande initiale. </td> 
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date </p> <p>Heure </p> </td> 
   <td colname="col2"> Horodatage </td> 
   <td colname="col3"> Heure à laquelle la demande a été traitée par le serveur (avec une précision de 100 ns); la précision dépend de l'environnement du serveur et du NTP) </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-Type) </td> 
   <td colname="col2"> Type de contenu </td> 
   <td colname="col3"> Type d’objet renvoyé par le serveur </td> 
   <td colname="col4"> text/html </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> Code d’état de réponse HTTP </td> 
   <td colname="col3"> Code numérique généré par le serveur qui indique l’état de la réponse du serveur HTTP </td> 
   <td colname="col4"> 200 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URI Stem </td> 
   <td colname="col3"> Partie "racine" de l’URI demandée par le client </td> 
   <td colname="col4"> pagedir/page.asp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> Adresse IP du client </td> 
   <td colname="col3"> Adresse IP du client demandeur </td> 
   <td colname="col4"> 127.0.0.1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> Nom de domaine du serveur </td> 
   <td colname="col3"> Nom de domaine du serveur Web qui traite la requête </td> 
   <td colname="col4"> <span class="filepath"> www.domain.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> URL de référence </td> 
   <td colname="col3"> Contenu du champ du référent HTTP envoyé par le client </td> 
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> Agent utilisateur </td> 
   <td colname="col3"> Périphérique utilisé pour envoyer une requête au serveur HTTP </td> 
   <td colname="col4"> <p>Mozilla/4.0+(compatible;+MSIE+6.0; </p> <p>+Windows+NT+5.1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Cookies client du domaine </td> 
   <td colname="col3"> Contenu de tous les cookies de l’utilisateur pour le site </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972 x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> Chaîne de requête </td> 
   <td colname="col3"> La partie de chaîne de requête, le cas échéant, de l’URI demandée par le client </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>

