---
description: Instructions de configuration des communications pour Insight Server ou Repeater.
solution: Insight
title: Paramètres de configuration des communications
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Paramètres de configuration des communications{#communications-configuration-settings}

Instructions de configuration des communications pour Insight Server ou Repeater.

Renseignez les paramètres dans le fichier suivant :

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>Avant de modifier des paramètres ne figurant pas dans ce tableau, contactez Adobe.

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Fichier de contrôle d'accès </td> 
   <td colname="col2"> <p>Emplacement du fichier <span class="filepath"> Access Control.cfg </span> . L’emplacement par défaut est le <span class="filepath"> dossier Access Control </span> dans le répertoire <span class="keyword"> Insight Server </span> ou le répertoire d’installation de Repeater <span class="wintitle"> </span> . </p> <p>Exemple : <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Répertoire du journal d'accès </td> 
   <td colname="col2"> <p>Dossier auquel vous souhaitez mapper les journaux d’audit. </p> <p>Exemple : <filepath></filepath> </p> <p> <p>Remarque :  Vous pouvez mapper les journaux de contrôle à un autre lecteur local (par exemple : <span class="filepath"> string : P:\\Audit\\ </span>), mais ne mettez pas en correspondance les journaux d’audit avec un lecteur réseau. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exposé du journal d'accès </td> 
   <td colname="col2"> Ce paramètre peut être défini sur true ou false. Il est utilisé pour activer et désactiver le filtrage du journal d’audit. Pour vous assurer que chaque requête est enregistrée, définissez le paramètre sur True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Interface IP </td> 
   <td colname="col2"> <p>Adresse IP à utiliser lorsque deux cartes réseau sont disponibles pour accéder à deux réseaux différents. </p> <p>Exemple : I <filepath></filepath><i>&lt; <span class="filepath"> Adresse IP </span>&gt;</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> <p>Port non sécurisé (HTTP) sur lequel le serveur <span class="keyword"> Insight </span> ou <span class="wintitle"> Repeater écoute </span> . Le port par défaut est le port 80. La saisie d’une valeur de 0 désactive les connexions non sécurisées. </p> <p>Exemple : <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chiffres SSL </td> 
   <td colname="col2"> Certains environnements nécessitent une sécurité de communication plus forte que d'autres. Si vous souhaitez utiliser une suite de chiffrement SSL spécifique, vous pouvez la spécifier avec ce paramètre. <p>Exemple : <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port SSL </td> 
   <td colname="col2"> <p>Port sécurisé (via SSL) sur lequel le serveur <span class="keyword"> Insight </span> ou <span class="wintitle"> Repeater écoute </span> . Le port par défaut est le port 443. La saisie d’une valeur de 0 désactive les connexions sécurisées. </p> <p>Exemple : <span class="filepath"></span> </p> <filepath></filepath> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer : </td> 
   <td colname="col2"> En-tête des paramètres du serveur de journalisation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom du client </td> 
   <td colname="col2"> <p>Nom de client à afficher pour les clients non spécifiés dans les alertes d’administration, comme dans l’exemple suivant : </p> <p>"Aucune donnée reçue du capteur XYZ pour le client "Non spécifié" dans 15." </p> <p>Exemple : <code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>À l’aide de l’exemple ci-dessus, les alertes administratives pour les clients non spécifiés se liraient désormais comme suit : </p> <p>"Aucune donnée reçue du capteur XYZ pour le client "CompanyAB" dans 15." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer : </p> <p> Chemin local = chaîne : Journaux\\ </p> </td> 
   <td colname="col2"> <p>Dossier dans lequel vous souhaitez stocker les fichiers journaux. </p> <p>Exemple : </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>Pour pouvoir accéder à ce dossier à partir du Gestionnaire de fichiers du <span class="wintitle"> serveur </span>, l’emplacement spécifié dans ce paramètre doit correspondre à l’emplacement spécifié dans le paramètre Chemins du journal dans le <span class="filepath"> fichier </span> Log Processing.cfg. Pour plus d'informations sur la modification du répertoire Logs dans le <span class="filepath"> fichier Log Processing.cfg </span> , consultez le chapitre Log Processing Configuration File (Fichier de configuration de traitement des journaux) du Guide <i>de configuration des jeux de</i>données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer : </p> <p> Chemin local = chaîne : Audit\ </p> </td> 
   <td colname="col2"> <p>Dossier auquel vous souhaitez mapper les journaux d’audit. </p> <p>Exemple : </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>Remarque :  <p>Vous pouvez mapper les journaux de contrôle à un autre lecteur local (par exemple : <span class="filepath"> string : P:\\Audit\\ </span>), mais ne mettez pas en correspondance les journaux d’audit avec un lecteur réseau. </p> <p>Pour pouvoir accéder à ce dossier à partir du Gestionnaire de fichiers du <span class="wintitle"> serveur </span>, l’emplacement spécifié dans ce paramètre doit correspondre à celui du paramètre Répertoire du journal d’accès dans ce fichier. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer : </td> 
   <td colname="col2"> <p>Ce paramètre s’applique uniquement à <span class="keyword"> Insight Server </span>. </p> <p>Pour plus d’informations sur la spécification du serveur de normalisation centralisée pour votre <span class="keyword"> grappe de serveurs </span> Insight, voir le chapitre Fichier de configuration de traitement des journaux du Guide <i>de configuration des jeux de</i>données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer : </p> <p> URI = chaîne : /ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>Ce paramètre s’applique uniquement à <span class="keyword"> Insight Server </span>. </p> <p>Permet d’afficher l’ <span class="keyword"> état du </span> rapport dans l’interface d’état détaillé du serveur <span class="keyword"> Insight </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

