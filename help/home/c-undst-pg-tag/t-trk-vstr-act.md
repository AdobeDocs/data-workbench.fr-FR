---
description: Les sites Web conçus à l'aide de Flash nécessitent une attention particulière en ce qui concerne la capture des actions effectuées dans le contenu multimédia enrichi.
solution: Analytics
title: Suivi   dans le contenu des médias enrichis Flash
topic: Data workbench
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
translation-type: tm+mt
source-git-commit: 48892b1b4fc9e9fdeacee8ca318025f43f2d0064

---


# Suivi   dans le contenu des médias enrichis Flash{#tracking-visitor-activity-within-flash-rich-media-content}

Les sites Web conçus à l&#39;aide de Flash nécessitent une attention particulière en ce qui concerne la capture des actions effectuées dans le contenu multimédia enrichi.

Grâce à [!DNL Flash] ActionScript, vous pouvez apporter des modifications simples à vos [!DNL Flash] films existants afin de permettre le suivi de toutes les interactions avec le film, telles que les clics sur les boutons ou les mouvements de la souris.

Pour faciliter le suivi des  de dans votre [!DNL Flash] film, suivez les étapes ci-dessous :

1. Ajouter le code ActionScript suivant dans votre film. Ce code représente une fonction qui peut être appelée par le  dans le [!DNL Flash] film dont vous souhaitez effectuer le suivi.

   ```
   // FLASH TAG CODE BEGIN 
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt"; 
   function tag(PAGENAME,VARIABLES) { 
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0); 
   } 
   // FLASH TAG CODE END
   ```

1. Créez un fichier vide nommé [!DNL flashtag.txt] et importez-le sur vos serveurs Web.
1. Dans la fonction de l’étape 1, remplacez l’espace réservé \[[!DNL PATH_TO_WEB_SERVER]\] par le chemin d’accès complet ou relatif à l’emplacement du [!DNL flashtag.txt] fichier. Par exemple :

   ```
   var FLASHTAGURI = http://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. Ajouter le code ActionScript suivant à tous les à suivre. Ce code représente un appel de fonction utilisé pour capturer des données sur le  du :

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Cet exemple illustre l’utilisation du  on(release) ; toutefois, la fonction tag() peut être référencée via n’importe quel dont vous souhaitez effectuer le suivi, tel qu’un on(press), on(rollover), on(rollout) ou on(keypress).

   L&#39;espace réservé \[[!DNL PUT_PAGE_NAME_HERE]\] doit être remplacé par une chaîne qui représente le nom de la page ou du sur lequel vous effectuez un suivi. La variable \[[!DNL PUT_PAGE_NAME_HERE]\]peut être modifiée manuellement ou par référence à une variable pour indiquer un nom unique pour la page ou le  du dans l’ [!DNL Flash] application. La valeur remplaçant l&#39;espace réservé \[[!DNL PUT_PAGE_NAME_HERE]\] peut être composée d&#39;un nom simple ou structurée de manière à représenter une structure hiérarchique similaire à un URI complet. Par exemple :

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe recommande que, avant le déploiement du code, vous compiliez une spécification écrite pour les noms de page et de  afin de faciliter l’alignement des besoins de l’entreprise et des de développement et de réduire le risque de cycles de développement supplémentaires.

1. Si vous le souhaitez, d’autres variables peuvent être collectées et associées aux pages ou aux  de dans le [!DNL Flash] film. Pour ce faire, remplacez l’espace réservé \[[!DNL PUT_ADDITIONAL_VAR_HERE]\] par un ensemble de paires nom=valeur séparées par une esperluette (&amp;). Par exemple :

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   Les variables peuvent être modifiées manuellement ou par référence à une variable afin de signaler les attributs supplémentaires à collecter et à associer à la page ou au . S&#39;il n&#39;existe aucune variable supplémentaire applicable à collecter, supprimez \[[!DNL PUT_ADDITIONAL_VAR_HERE]\].

   La configuration du suivi des dans le contenu [!DNL Flash] multimédia enrichi est maintenant terminée. Lorsque le  est appelé, la [!DNL (PAGENAME,VARIABLES)] fonction de balise est appelée, ce qui entraîne une demande HTTP pour le fichier suivant. Cette fonction sera appelée en plus des autres fonctions qui peuvent être déclenchées comme défini dans votre [!DNL Flash] animation :

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

La requête HTTP résultant de la fonction [!DNL Flash] Tag ActionScript génère la collecte des informations suivantes pour chaque de l’ [!DNL Flash] animation. La dernière ligne du tableau (nom W3C cs-uri-) représente les informations collectées pour les variables supplémentaires spécifiées dans votre appel de fonction.

<table id="table_A7ED9D38F36B4405947B2F48EA94D3C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom W3C </th> 
   <th colname="col2" class="entry"> Données collectées </th> 
   <th colname="col3" class="entry"> Explication </th> 
   <th colname="col4" class="entry"> Exemple </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> Identifiant de suivi (unique) </td> 
   <td colname="col3"> Identifiant lu à partir d’un cookie placé dans le navigateur de l’utilisateur par <span class="wintitle"> Sensor </span> sur la requête initiale du. </td> 
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date </p> <p>Heure </p> </td> 
   <td colname="col2"> Horodatage </td> 
   <td colname="col3"> Heure à laquelle la demande a été traitée par le serveur (avec une précision de 100 ns); la précision dépend de la  du serveur ( et NTP) </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-Type) </td> 
   <td colname="col2"> Type de contenu </td> 
   <td colname="col3"> Type d’objet renvoyé par le serveur </td> 
   <td colname="col4"> Texte/html </td> 
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
   <td colname="col2"> Adresse IP du client </td> 
   <td colname="col3"> Adresse IP du client demandeur </td> 
   <td colname="col4"> 127.0.0.1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> Nom de domaine du serveur </td> 
   <td colname="col3"> Nom de domaine du serveur Web qui traite la requête </td> 
   <td colname="col4"> www.mysite.com </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs() </td> 
   <td colname="col2"> URL de référence </td> 
   <td colname="col3"> Contenu du champ de  HTTP envoyé par le client </td> 
   <td colname="col4"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> Agent utilisateur </td> 
   <td colname="col3"> Périphérique utilisé pour envoyer une requête au serveur HTTP </td> 
   <td colname="col4"> Mozilla/4.0+(compatible;+MSIE+6.0; +Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Cookies client du domaine </td> 
   <td colname="col3"> Contenu de tous les cookies de l’utilisateur pour le site </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri- </td> 
   <td colname="col2"> Chaîne de  </td> 
   <td colname="col3"> La partie de chaîne de , le cas échéant, de l’URI demandée par le client </td> 
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td> 
  </tr> 
 </tbody> 
</table>

