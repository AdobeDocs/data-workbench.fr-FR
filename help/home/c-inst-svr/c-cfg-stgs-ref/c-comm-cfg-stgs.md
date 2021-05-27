---
description: Instructions de configuration des communications pour le serveur Insight ou le répéteur.
title: Paramètres de configuration des communications
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
exl-id: a35788d1-de36-4350-a107-eee392e44503
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---

# Paramètres de configuration des communications{#communications-configuration-settings}

Instructions de configuration des communications pour le serveur Insight ou le répéteur.

Renseignez les paramètres du fichier suivant :

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>Avant de modifier des paramètres qui ne sont pas répertoriés dans ce tableau, veuillez contacter Adobe.

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Fichier de contrôle d’accès </td> 
   <td colname="col2"> <p>Emplacement du fichier <span class="filepath"> Access Control.cfg </span>. L’emplacement par défaut est le dossier <span class="filepath"> Contrôle d’accès </span> dans le répertoire d’installation <span class="keyword"> Insight Server </span> ou <span class="wintitle"> Répéteur </span>. </p> <p>Exemple : <code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Répertoire du journal d’accès </td> 
   <td colname="col2"> <p>Dossier auquel vous souhaitez mapper les journaux d’audit. </p> <p>Exemple : <code>Access Log Directory = string: Audit\\</code> </p> <p> <p>Remarque :  Vous pouvez mapper les journaux d’audit à un autre lecteur local (par exemple : <span class="filepath"> chaîne : P:\\Audit\\ </span>), mais ne mappez pas les journaux d’audit à un lecteur réseau. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Accès au détail du journal </td> 
   <td colname="col2"> Ce paramètre peut être défini sur true ou false. Il est utilisé pour activer et désactiver le filtrage du journal d’audit. Pour vous assurer que chaque requête est enregistrée, définissez le paramètre sur True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Interface IP </td> 
   <td colname="col2"> <p>Adresse IP à utiliser lorsque deux cartes réseau sont disponibles pour accéder à deux réseaux différents. </p> <p>Exemple : <code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> <p>Port non sécurisé (HTTP) sur lequel le serveur Insight <span class="keyword"> </span> ou <span class="wintitle"> Répéteur </span> écoute. Le port par défaut est le port 80. La saisie d’une valeur de 0 désactive les connexions non sécurisées. </p> <p>Exemple : <code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chiffres SSL </td> 
   <td colname="col2"> Certains environnements nécessitent une sécurité de communication plus forte que d’autres. Si vous souhaitez utiliser une suite de chiffrement SSL spécifique, vous pouvez la spécifier avec ce paramètre. <p>Exemple : <code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port SSL </td> 
   <td colname="col2"> <p>Port sécurisé (via SSL) sur lequel le serveur d’aperçu <span class="keyword"> </span> ou <span class="wintitle"> Répéteur </span> écoute. Le port par défaut est le port 443. La saisie d’une valeur de 0 désactive les connexions sécurisées. </p> <p>Exemple : <span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer : </td> 
   <td colname="col2"> En-tête des paramètres du serveur de journalisation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom du client </td> 
   <td colname="col2"> <p>Nom du client à afficher pour les clients non spécifiés dans les alertes administratives, comme dans l’exemple suivant : </p> <p>"Aucune donnée reçue du capteur XYZ pour le client "Non spécifié" dans 15." </p> <p>Exemple : <code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>En reprenant l’exemple ci-dessus, les alertes administratives pour les clients non spécifiés se liraient désormais comme suit : </p> <p>"Aucune donnée reçue du capteur XYZ pour le client ‘CompanyAB’ dans 15." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer : </p> <p> Chemin local = chaîne : Logs\\ </p> </td> 
   <td colname="col2"> <p>Dossier dans lequel vous souhaitez stocker les fichiers journaux. </p> <p>Exemple : </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>Pour pouvoir accéder à ce dossier à partir du <span class="wintitle"> Gestionnaire de fichiers de serveur </span>, l’emplacement spécifié dans ce paramètre doit correspondre à l’emplacement que vous spécifiez dans le paramètre Chemins de journal dans le fichier <span class="filepath"> Log Processing.cfg </span> . Pour plus d’informations sur la modification du répertoire Logs dans le fichier <span class="filepath"> Log Processing.cfg </span>, voir le chapitre Log Processing Configuration File du <i>Guide de configuration du jeu de données</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer : </p> <p> Chemin local = chaîne : Audit\ </p> </td> 
   <td colname="col2"> <p>Dossier auquel vous souhaitez mapper les journaux d’audit. </p> <p>Exemple : </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>Remarque :  <p>Vous pouvez mapper les journaux d’audit à un autre lecteur local (par exemple : <span class="filepath"> chaîne : P:\\Audit\\ </span>), mais ne mappez pas les journaux d’audit à un lecteur réseau. </p> <p>Pour pouvoir accéder à ce dossier à partir du <span class="wintitle"> Gestionnaire de fichiers serveur </span>, l’emplacement spécifié dans ce paramètre doit correspondre à l’emplacement que vous avez défini dans le paramètre Répertoire du journal d’accès de ce fichier. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer : </td> 
   <td colname="col2"> <p>Ce paramètre s’applique uniquement à <span class="keyword"> Insight Server </span>. </p> <p>Pour plus d’informations sur la spécification du serveur de normalisation centralisé pour votre <span class="keyword"> grappe de serveurs Insight </span>, voir le chapitre Fichier de configuration de traitement du journal du <i>Guide de configuration des jeux de données</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer : </p> <p> URI = chaîne : /ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>Ce paramètre s’applique uniquement à <span class="keyword"> Insight Server </span>. </p> <p>Permet d’afficher le <span class="keyword"> statut du rapport </span> dans l’interface de statut détaillée de <span class="keyword"> serveur Insight </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
