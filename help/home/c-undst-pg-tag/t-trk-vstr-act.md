---
description: Les sites web conçus à l’aide de Flashs nécessitent une attention particulière en ce qui concerne la capture des actions des visiteurs effectuées dans le contenu multimédia.
title: Suivi de l’activité visiteur dans du contenu multimédia Flash
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
exl-id: f51c7034-a7fd-4575-80e1-18fc6513ca2b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 5%

---

# Suivi de l’activité visiteur dans du contenu multimédia Flash{#tracking-visitor-activity-within-flash-rich-media-content}

{{eol}}

Les sites web conçus à l’aide de Flashs nécessitent une attention particulière en ce qui concerne la capture des actions des visiteurs effectuées dans le contenu multimédia.

Utilisation [!DNL Flash] ActionScript, vous pouvez apporter des modifications simples à votre [!DNL Flash] films pour permettre le suivi de toutes les interactions des visiteurs avec le film, telles que les clics sur les boutons ou les mouvements de la souris.

Pour faciliter le suivi des activités des visiteurs dans votre [!DNL Flash] , veuillez suivre les étapes ci-dessous :

1. Ajoutez le code d’ActionScript suivant à votre film. Ce code représente une fonction qui peut être appelée par des événements dans la variable [!DNL Flash] film dont vous souhaitez effectuer le suivi.

   ```
   // FLASH TAG CODE BEGIN
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt";
   function tag(PAGENAME,VARIABLES) {
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0);
   }
   // FLASH TAG CODE END
   ```

1. Créez un fichier vierge nommé [!DNL flashtag.txt] et placez le fichier sur vos serveurs web.
1. Dans la fonction de l’étape 1, remplacez le \[[!DNL PATH_TO_WEB_SERVER]\] espace réservé avec le chemin d’accès complet ou relatif à l’emplacement de la variable [!DNL flashtag.txt] fichier . Par exemple :

   ```
   var FLASHTAGURI = https://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. Ajoutez le code d’ActionScript suivant à tous les événements à suivre. Ce code représente un appel de fonction utilisé pour capturer des données sur l’événement :

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Cet exemple illustre l’utilisation de l’événement on(release) ; toutefois, la fonction tag() peut être référencée par tout événement dont vous souhaitez peut-être effectuer le suivi, par exemple un événement on(press), on(rollover), on(rollout) ou on(keypress).

   Le \[[!DNL PUT_PAGE_NAME_HERE]\] l’espace réservé doit être remplacé par une chaîne qui représente le nom de la page ou de l’événement dont vous effectuez le suivi. Le \[[!DNL PUT_PAGE_NAME_HERE]La variable \]peut être modifiée manuellement ou par l’intermédiaire d’une référence de variable afin de représenter un nom unique pour la page ou l’événement dans la variable [!DNL Flash] application. La valeur remplaçant le \[[!DNL PUT_PAGE_NAME_HERE]\] l’espace réservé peut être constitué d’un nom simple ou peut être structuré pour représenter une structure hiérarchique similaire à un URI complet. Par exemple :

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe recommande, avant le déploiement du code, de compiler une spécification écrite pour les noms de page et d’événement afin de faciliter l’alignement des exigences de l’entreprise et des tâches de développement et de réduire le potentiel de cycles de développement supplémentaires.

1. Si vous le souhaitez, des variables supplémentaires peuvent être collectées et associées à des pages ou à des événements dans la variable [!DNL Flash] film. Pour ce faire, remplacez le \[[!DNL PUT_ADDITIONAL_VAR_HERE]\] espace réservé avec un ensemble de paires nom=valeur séparées par une esperluette (&amp;). Par exemple :

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   Les variables peuvent être modifiées manuellement ou par référence à une variable afin de représenter les attributs supplémentaires à collecter et à associer à la page ou à l’événement. S’il n’existe aucune variable supplémentaire applicable à collecter, supprimez \[[!DNL PUT_ADDITIONAL_VAR_HERE]\].

   Votre configuration du suivi des visiteurs dans [!DNL Flash] le contenu multimédia est maintenant terminé. Lorsque l’événement est appelé, la balise [!DNL (PAGENAME,VARIABLES)] est appelée, ce qui entraîne l’exécution d’une requête HTTP pour le fichier suivant. Cette fonction sera appelée en plus des autres fonctions qui peuvent être déclenchées telles que définies dans votre [!DNL Flash] film :

   ```
   https://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

La requête HTTP issue du [!DNL Flash] La fonction d’ActionScript de balises génère la collecte des informations suivantes pour chaque événement dans la variable [!DNL Flash] film. La dernière ligne du tableau (nom W3C cs-uri-query) représente les informations collectées pour les variables supplémentaires spécifiées dans votre appel de fonction.

<table id="table_A7ED9D38F36B4405947B2F48EA94D3C4">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Nom du W3C </th>
   <th colname="col2" class="entry"> Données collectées </th>
   <th colname="col3" class="entry"> Description </th>
   <th colname="col4" class="entry"> Exemple </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> Identifiant de suivi (visiteur unique) </td>
   <td colname="col3"> Identifiant lu à partir d’un cookie placé dans le navigateur de l’utilisateur par <span class="wintitle"> Sensor </span> sur la requête initiale du visiteur </td>
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Date </p> <p>Heure </p> </td>
   <td colname="col2"> Horodatage </td>
   <td colname="col3"> Heure à laquelle la demande a été traitée par le serveur (avec une précision de 100 ns) ; la précision dépend de l’environnement du serveur et de NTP) </td>
   <td colname="col4"> 2002-11-21 17:21:45,123 </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-Type) </td>
   <td colname="col2"> Type de contenu </td>
   <td colname="col3"> Type d’objet renvoyé par le serveur </td>
   <td colname="col4"> Text/html </td>
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
   <td colname="col3"> Partie racine de l’URI demandée par le client </td>
   <td colname="col4"> /flashtag/flashtag.txt </td>
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
   <td colname="col4"> www.mysite.com </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> URL de référence </td>
   <td colname="col3"> Contenu du champ de référent HTTP envoyé par le client </td>
   <td colname="col4"></td>
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
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td>
  </tr>
 </tbody>
</table>
