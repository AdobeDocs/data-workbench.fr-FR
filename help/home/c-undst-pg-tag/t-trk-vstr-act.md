---
description: Les sites Web conçus à l'aide du Flash nécessitent une attention particulière en ce qui concerne la capture des actions visiteuses effectuées dans le contenu multimédia enrichi.
title: Suivi de l’activité visiteur dans du contenu multimédia Flash
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
exl-id: f51c7034-a7fd-4575-80e1-18fc6513ca2b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 5%

---

# Suivi de l’activité visiteur dans du contenu multimédia Flash{#tracking-visitor-activity-within-flash-rich-media-content}

Les sites Web conçus à l&#39;aide du Flash nécessitent une attention particulière en ce qui concerne la capture des actions visiteuses effectuées dans le contenu multimédia enrichi.

Grâce à l&#39;ActionScript [!DNL Flash], vous pouvez apporter des modifications simples à vos séquences vidéo [!DNL Flash] existantes afin de permettre le suivi de toutes les interactions des visiteurs avec la séquence, telles que les clics sur les boutons ou les mouvements de la souris.

Pour faciliter le suivi des activités Visiteurs dans votre séquence [!DNL Flash], suivez les étapes ci-dessous :

1. Ajoutez le code d&#39;ActionScript suivant dans votre film. Ce code représente une fonction qui peut être appelée par des événements dans l&#39;animation [!DNL Flash] dont vous souhaitez effectuer le suivi.

   ```
   // FLASH TAG CODE BEGIN 
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt"; 
   function tag(PAGENAME,VARIABLES) { 
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0); 
   } 
   // FLASH TAG CODE END
   ```

1. Créez un fichier vierge nommé [!DNL flashtag.txt] et importez-le sur vos serveurs Web.
1. Dans la fonction de l’étape 1, remplacez l’espace réservé \[[!DNL PATH_TO_WEB_SERVER]\] par le chemin d’accès complet ou relatif à l’emplacement du fichier [!DNL flashtag.txt]. Par exemple :

   ```
   var FLASHTAGURI = http://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. Ajoutez le code d&#39;ActionScript suivant à tous les événements à suivre. Ce code représente un appel de fonction utilisé pour capturer des données sur le événement :

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Cet exemple illustre l&#39;utilisation du événement on(release); toutefois, la fonction tag() peut être référencée par n’importe quel événement dont vous souhaitez effectuer le suivi, tel qu’un événement on(press), on(rollover), on(rollout) ou on(keypress).

   L&#39;espace réservé \[[!DNL PUT_PAGE_NAME_HERE]\] doit être remplacé par une chaîne qui représente le nom de la page ou du événement sur lequel vous effectuez un suivi. La variable \[[!DNL PUT_PAGE_NAME_HERE]\]peut être modifiée manuellement ou par référence à une variable pour indiquer un nom unique pour la page ou le événement dans l&#39;application [!DNL Flash]. La valeur remplaçant l&#39;espace réservé \[[!DNL PUT_PAGE_NAME_HERE]\] peut être constituée d&#39;un nom simple ou peut être structurée de manière à représenter une structure hiérarchique similaire à une URI complète. Par exemple :

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe recommande que, avant le déploiement du code, vous compiliez une spécification écrite pour les noms de page et de événement afin de faciliter l&#39;alignement des besoins commerciaux et des tâches de développement et de réduire le risque de cycles de développement supplémentaires.

1. Si vous le souhaitez, d&#39;autres variables peuvent être collectées et associées à des pages ou à des événements dans l&#39;animation [!DNL Flash]. Pour ce faire, remplacez l’espace réservé \[[!DNL PUT_ADDITIONAL_VAR_HERE]\] par un ensemble de paires nom=valeur séparées par une esperluette (&amp;). Par exemple :

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   Les variables peuvent être modifiées manuellement ou par référence à une variable pour indiquer les attributs supplémentaires à collecter et à associer à la page ou au événement. S&#39;il n&#39;existe aucune variable supplémentaire applicable à collecter, supprimez \[[!DNL PUT_ADDITIONAL_VAR_HERE]\].

   La configuration du suivi des visiteurs dans le contenu multimédia enrichi [!DNL Flash] est maintenant terminée. Lorsque le événement est appelé, la fonction de balise [!DNL (PAGENAME,VARIABLES)] est appelée, ce qui provoque une demande HTTP pour le fichier suivant. Cette fonction sera appelée en plus des autres fonctions qui peuvent être déclenchées comme défini dans votre animation [!DNL Flash] :

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

La requête HTTP résultant de la fonction d&#39;ActionScript de balise [!DNL Flash] entraîne la collecte des informations suivantes pour chaque événement de l&#39;animation [!DNL Flash]. La dernière ligne du tableau (nom W3C cs-uri-requête) représente les informations collectées pour les variables supplémentaires spécifiées dans votre appel de fonction.

<table id="table_A7ED9D38F36B4405947B2F48EA94D3C4"> 
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
   <td colname="col3"> Identifiant lu à partir d’un cookie placé dans le navigateur de l’utilisateur par <span class="wintitle"> Capteur </span> sur la demande initiale du Visiteur. </td> 
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date </p> <p>Heure </p> </td> 
   <td colname="col2"> Horodatage </td> 
   <td colname="col3"> Heure à laquelle la demande a été traitée par le serveur (avec une précision de 100 ns); la précision dépend de l'environnement du serveur et du protocole NTP) </td> 
   <td colname="col4"> 21-11-2002 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-Type) </td> 
   <td colname="col2"> Type de contenu </td> 
   <td colname="col3"> Type d’objet renvoyé par le serveur </td> 
   <td colname="col4"> Texte/html </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> Code d'état de réponse HTTP </td> 
   <td colname="col3"> Code numérique généré par le serveur qui indique l’état de la réponse du serveur HTTP </td> 
   <td colname="col4"> 200 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URI Stem </td> 
   <td colname="col3"> Partie racine de l'URI demandée par le client </td> 
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
   <td colname="col3"> Nom de domaine du serveur Web qui traite la demande </td> 
   <td colname="col4"> www.mysite.com </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(parrain) </td> 
   <td colname="col2"> URL de référence </td> 
   <td colname="col3"> Contenu du champ parrain HTTP envoyé par le client </td> 
   <td colname="col4"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> Agent utilisateur </td> 
   <td colname="col3"> Périphérique utilisé pour envoyer une requête au serveur HTTP </td> 
   <td colname="col4"> Mozilla/4.0+(compatible ;+MSIE+6.0 ; +Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Cookies client du domaine </td> 
   <td colname="col3"> Contenu de tous les cookies de l’utilisateur pour le site </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-requête </td> 
   <td colname="col2"> Chaîne de requête </td> 
   <td colname="col3"> Partie de la chaîne de requête, le cas échéant, de l’URI demandée par le client. </td> 
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td> 
  </tr> 
 </tbody> 
</table>
