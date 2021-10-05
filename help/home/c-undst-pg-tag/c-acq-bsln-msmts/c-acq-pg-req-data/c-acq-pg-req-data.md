---
description: Capteur acquiert toutes les données de mesure qui sont transmises lors des demandes de page (demandes de GET) effectuées sur les serveurs web sur lesquels il a été installé.
title: Acquisition des données de requête de page
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
exl-id: e42566a3-d5b4-4f1a-b8cd-1ea646041101
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 4%

---

# Acquisition des données de requête de page{#acquiring-page-request-data}

Capteur acquiert toutes les données de mesure qui sont transmises lors des demandes de page (demandes de GET) effectuées sur les serveurs web sur lesquels il a été installé.

[!DNL Sensor] acquiert ces données de mesure par le biais de l’interface de programmation d’applications du serveur web, directement à partir de l’instance ou des instances du logiciel du serveur web s’exécutant sur votre serveur web. [!DNL Sensor] n’accède pas aux fichiers journaux générés par le serveur web. En fait, une fois [!DNL Sensor] et le serveur Data Workbench installés et testés, la fonctionnalité de journalisation native du serveur web peut être désactivée sans affecter la collecte de données. Dans de nombreux cas, la désactivation de la journalisation des fichiers sur les disques locaux des machines de serveurs web améliore la capacité de diffusion des pages de ces serveurs web en raison de la quantité relativement importante d’E/S de disque fixe requise pour consigner ces informations sur le disque local de l’ordinateur du serveur web.

[!DNL Sensor] collecte les données de mesure et de demande web directement à partir de chaque processus de serveur web et de serveur web virtuel (le cas échéant) et écrit temporairement les données dans un fichier de file d’attente, une file d’attente de mémoire tolérant les pannes avec support de disque fixe, sur l’ordinateur du serveur web. Le service d’émetteur de Capteur (ou démon selon la plateforme) récupère les données du fichier de file d’attente, puis les compresse et les chiffre avant de les transmettre au serveur Data Workbench pour un stockage à long terme. Avec [!DNL Sensor], les données sont accumulées sur vos machines de serveur web dans le fichier de file d’attente uniquement si vous rencontrez un réseau ou un autre problème qui empêche sa transmission. Le fichier de file d’attente permet un stockage local efficace des heures à des jours de données de demande web afin de protéger les données si une défaillance du réseau ou du système ne permet pas la transmission des données au serveur Data Workbench en temps réel.

[!DNL Sensor] collecte les données de mesure de chaque processus de serveur web physique et logique, les filtre par type de contenu, les compresse, les chiffre et les diffuse sur le serveur Data Workbench.

Le tableau suivant contient les champs d’informations de journal acquises par [!DNL Sensor] pour chaque demande de GET qui n’est pas filtrée en fonction du fichier de configuration [!DNL Sensor’s] :

<table id="table_5F65474150EC41648B35D0B031FB9B15">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Nom du W3C </th>
   <th colname="col2" class="entry"> Données collectées </th>
   <th colname="col3" class="entry"> Description </th>
   <th colname="col4" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> Identifiant de suivi (visiteur unique) </td>
   <td colname="col3"> Identifiant lu à partir d’un cookie placé dans le navigateur de l’utilisateur par <span class="wintitle"> Capteur </span> sur la requête initiale du visiteur. </td>
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Date </p> <p>Heure </p> </td>
   <td colname="col2"> Horodatage </td>
   <td colname="col3"> Heure à laquelle la demande a été traitée par le serveur (avec une précision de 100 ns) ; la précision dépend de l’environnement du serveur et de NTP) </td>
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
   <td colname="col4"> 404 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> URI Stem </td>
   <td colname="col3"> Partie racine de l’URI demandée par le client </td>
   <td colname="col4"> <span class="filepath"> pagedir/page.asp  </span> </td>
  </tr>
  <tr>
   <td colname="col1"> c-ip </td>
   <td colname="col2"> IP du client </td>
   <td colname="col3"> Adresse IP du client demandeur </td>
   <td colname="col4"> 127.0.0.1 </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> Nom de domaine du serveur </td>
   <td colname="col3"> Nom de domaine du serveur web qui traite la demande. </td>
   <td colname="col4"> <span class="filepath"> www.domain.com  </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> URL de référence </td>
   <td colname="col3"> Contenu du champ de référent HTTP envoyé par le client </td>
   <td colname="col4"> <span class="filepath"> https://www.referringsite.com  </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> Agent utilisateur </td>
   <td colname="col3"> Appareil utilisé pour envoyer une requête au serveur HTTP </td>
   <td colname="col4"> Mozilla/4.0+(compatible ;+MSIE+6.0; +Windows+NT+5.1) </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> Cookies client à partir du domaine </td>
   <td colname="col3"> Contenu de tous les cookies de l’utilisateur pour le site </td>
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> Chaîne de requête </td>
   <td colname="col3"> La partie chaîne de requête, le cas échéant, de l’URI demandé par le client </td>
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td>
  </tr>
 </tbody>
</table>
