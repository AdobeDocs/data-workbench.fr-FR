---
description: Informations sur les champs de données que le serveur Data Workbench peut traiter pour créer un jeu de données.
title: Champs d’enregistrement des données d’événement
uuid: b0232bfa-0a3b-4e3d-876e-6a15a3764eae
exl-id: 35433b87-991a-4fb9-ba6a-3217e89eb769
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 2%

---

# Champs d’enregistrement des données d’événement{#event-data-record-fields}

Informations sur les champs de données que le serveur Data Workbench peut traiter pour créer un jeu de données.

* [À propos des données d’événement](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-3a0705f8c1824017aa4effed9903efbe)
* [Champs d’enregistrement des données d’événement de la ligne de base](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-a882ed7aa6af41eeb45a55bf8c1ca3d7)
* [Champs dérivés](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-b6c57ee2aa31469fbd5dab90e52bc677)

## À propos des données d’événement {#section-3a0705f8c1824017aa4effed9903efbe}

Les données d’événement utilisées pour créer un jeu de données résident dans des fichiers appelés sources de journal. Les données disponibles dans les sources de journal sont appelées données d’événement, car chaque enregistrement de données représente un enregistrement de transaction ou une instance unique d’un événement avec un horodatage associé.

Les données d’événement d’une source de journal sont collectées en temps réel par [!DNL Sensors]. Les données d’événement collectées par [!DNL Sensors] à partir de serveurs HTTP et d’applications sont transmises aux serveurs Data Workbench, qui convertissent les données en fichiers journaux ( [!DNL .vsl]) compressés. Les données d’événement résidant dans un fichier plat, un fichier XML ou une source de données ODBC sont lues par le serveur Data Workbench, qui fournit des décodeurs que vous définissez pour extraire un ensemble commun de champs de données de ces différents formats.

Les sections suivantes apportent des informations sur les champs de données (appelés champs d’enregistrement de données d’événement ou champs de saisie de journal ) collectés par [!DNL Sensors] ou lus et mis à la disposition du serveur Data Workbench.

>[!NOTE]
>
>Les noms des champs respectent généralement la convention de dénomination du format de fichier journal étendu W3C. La plupart des champs comportent des préfixes qui indiquent la source des informations contenues dans le champ :

* cs indique la communication du client au serveur.
* sc indique la communication du serveur au client.
* s indique des informations provenant du serveur.
* c indique les informations provenant du client.
* x indique les informations créées par un produit logiciel Adobe.

## Champs d’enregistrement des données d’événement de la ligne de base {#section-a882ed7aa6af41eeb45a55bf8c1ca3d7}

Les fichiers journaux ( [!DNL .vsl]) contiennent les champs de données d’événement collectés à partir des serveurs par [!DNL Sensors] et utilisés par le serveur Data Workbench dans le processus de construction du jeu de données. Le tableau suivant répertorie les champs d’un enregistrement de données d’événement type enregistré par [!DNL Sensor] :

<table id="table_98E135FE4EAF44D6ADEB3C6C1C0BF6A4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> <p>Adresse IP du client, telle qu’elle est incluse dans la demande envoyée au serveur. </p> <p> Exemple : 207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>Les cookies envoyés par le client avec la demande. </p> <p> Exemple : v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDACQ=GPIBKEIBFBFIPLOJMKCAAEPM; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> <p>Chaîne de référent HTTP envoyée par le client au serveur avec la demande. </p> <p> Exemple : <span class="filepath"> http://www.mysite.net/cgi-bin/websearch?qry </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>Chaîne envoyée par le client avec sa requête au serveur qui indique le type d’agent utilisateur du client. </p> <p> Exemple : Mozilla/5.0 (Windows) U ; Windows NT 5.1 ; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>Type de méthode de la requête HTTP. </p> <p> Exemple : GET </p> <p> Référence : <span class="filepath"> http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>Partie de chaîne de requête de l’URI (tige + chaîne de requête = URI). Ceci est précédé d’un point d’interrogation (?) et peut contenir une ou plusieurs paires nom-valeur séparées par des esperluettes (&amp;). </p> <p> Exemple : page=homepage </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> <p>La partie racine de l’URI (tige + chaîne de requête = URI). La racine est le chemin d’accès réel ou logique à la ressource demandée sur le serveur. </p> <p> Exemple : <span class="filepath"> /index.asp </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>Type de contenu de la ressource demandée par le client comme indiqué par le serveur. </p> <p> Exemples : text/html, image/png, image/gif, video/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>Nombre d’octets de données envoyés du serveur au client en réponse à la demande. </p> <p> Exemple : 4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>Code d’état renvoyé au client par le serveur. </p> <p> Exemple : 200 </p> <p> Référence : <span class="filepath"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>Nom de domaine complet ou adresse IP de l’hôte de la ressource demandée. </p> <p> Exemple : <span class="filepath"> www.adobe.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-expérience </td> 
   <td colname="col2"> <p>Liste de tous les noms et groupes d’expériences contrôlés dont le client est membre au moment de la requête. </p> <p> Exemple : VSHome_Exp.Group_1,VSRegistration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>Date et heure (GMT) auxquelles la demande a été reçue par le serveur. Le temps est exprimé sous la forme du nombre de 100 nanosecondes écoulées depuis le 1er janvier 1600. </p> <p> Exemple : 127710989320000000 correspond à la valeur x-timestamp pour 11:28:52.0000000 le mardi 13 septembre 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>Valeur hexadécimale 64 bits de l’identifiant unique du navigateur trouvé dans un cookie persistant tel que défini par un Capteur <span class="wintitle"> </span> et fourni par le client avec une requête à un serveur. </p> <p> Exemple : 42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Champs dérivés {#section-b6c57ee2aa31469fbd5dab90e52bc677}

Le tableau ci-dessous répertorie des exemples de champs dérivés par le serveur Data Workbench des champs d’enregistrement de données d’événement de ligne de base :

<table id="table_3B008F1314804A69AE69E8F94908F497"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(cookie)(name) </td> 
   <td colname="col2"> La valeur d’une paire nom-valeur donnée dans un cookie. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-domain) </td> 
   <td colname="col2"> <p>Nom de domaine ou adresse IP de l’URI de référence HTTP. </p> <p> <p>Remarque :  Ce champ est en lecture seule. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-host) </td> 
   <td colname="col2"> <p>Nom d’hôte complet du référent. </p> <p> Exemple : Si cs(referrer) est <span class="filepath"> http://my.domain.com/my/page </span>, cs(referrer-host) est <span class="filepath"> my.domain.com </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-query)(name) </td> 
   <td colname="col2"> <p>La valeur d’une chaîne de requête de référent. </p> <p> <p>Remarque :  Vous ne pouvez pas accéder à une valeur de chaîne de requête de référent à l’aide du champ cs(referrer)(name) . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri </td> 
   <td colname="col2"> <p>L’URI complet (tige + chaîne de requête = URI entier). </p> <p> Exemple : <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query(name) </td> 
   <td colname="col2"> <p>La valeur associée au nom donné. S’il existe plusieurs valeurs pour le nom donné, ce champ renvoie la dernière de ces valeurs. </p> Exemples : 
    <ul id="ul_47BBB2E3076A46629BFCDB2A460F700B"> 
     <li id="li_AC9BB29505A54AE4AFF49438530C9EA4"> Pour l’URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span>, cs-uri-query(product3) renvoie cd. </li> 
     <li id="li_B036C1D0B25748E0A155DDC9B1B999CB"> Pour l’URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product1=casette </span>, <span class="wintitle"> cs-uri-query(product1) </span> renvoie une casette. </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ctime </td> 
   <td colname="col2"> x-timestamp exprimé en secondes depuis le 1er janvier 1970. Ce champ est également appelé x-unixtime. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> date </td> 
   <td colname="col2"> x-timestamp au format AAAA-MM-JJ. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> time </td> 
   <td colname="col2"> x-timestamp au format HH:MM:SS. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-local-timestring </td> 
   <td colname="col2"> <p>x-timestamp converti en fuseau horaire local spécifié dans le fichier <span class="filepath"> Transformation.cfg </span> du jeu de données. Le format est AAAA-MM-JJ HH:MM:SS.mmm. </p> <p> <p>Remarque :  Vous pouvez également définir des conversions temporelles telles que x-local-timestring dans le fichier <span class="filepath"> Log Processing.cfg </span> . Pour plus d’informations, voir <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Fichier de configuration de traitement du journal </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-log-source-id </td> 
   <td colname="col2"> <p>Identifiant correspondant à la source du journal pour une entrée de journal spécifique. Pour que l’identifiant soit enregistré, vous devez le spécifier dans le champ <span class="wintitle"> Identifiant de la source de journal </span> du fichier <span class="filepath"> Log Processing.cfg </span> lors de la définition de <span class="wintitle"> Capteur </span>, fichier journal ou sources de données ODBC. Pour plus d’informations, voir <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Fichier de configuration de traitement du journal </a>. </p> <p> Exemple : de VSensor01. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-mask </td> 
   <td colname="col2"> Modèle de masque des sources de données <span class="wintitle"> Capteur </span> (dérivé des noms de fichiers <span class="filepath"> .vsl </span> ). Pour un fichier dont le nom est au format <span class="filepath"> YYYMMDD-SENSORID.VSL </span>, x-mask est SENSORID. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestring </td> 
   <td colname="col2"> x-timestamp au format AAAA-MM-JJ HH:MM:SS.mmm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-unixtime </td> 
   <td colname="col2"> Heure UNIX décimale dérivée de l’horodatage x. </td> 
  </tr> 
 </tbody> 
</table>

[!DNL Sensor], lorsqu’il est utilisé sur un serveur, peut collecter des champs de données d’événement de n’importe quel en-tête ou variable HTTP valide disponible via l’API du serveur. Pour collecter ces champs de données, vous devez spécifier les champs d’en-tête ou les variables de votre choix dans le fichier de configuration [!DNL txlogd.conf]pour [!DNL Sensor]. Pour plus d’informations, voir le *Guide du Data Workbench [!DNL Sensor]*.
