---
description: L’accès à votre portail de rapports et les autorisations y relatives sont contrôlés à l’aide de comptes d’utilisateurs et de groupes individuels.
solution: Analytics
title: Modification du fichier Email.asp
topic: Data workbench
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modification du fichier Email.asp{#edit-the-email-asp-file}

L’accès à votre portail de rapports et les autorisations y relatives sont contrôlés à l’aide de comptes d’utilisateurs et de groupes individuels.

Chaque fois que vous ajoutez un nouveau compte ou modifiez un compte existant, un courrier électronique de confirmation peut être envoyé à l’adresse électronique que vous spécifiez pour ce compte (voir [Utilisation de comptes](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)) et copié vers les adresses électroniques que vous spécifiez dans le [!DNL email.asp] fichier.

>[!NOTE]
>
>Les courriers électroniques de notification sont envoyés aux utilisateurs du compte uniquement lorsque vous avez spécifié une adresse électronique pour le compte et que le [!DNL email.asp] fichier est correctement configuré. Si vous ne souhaitez pas que des courriers électroniques de notification soient envoyés pour un compte, laissez vide le champ d’adresse électronique du compte.

Ce fichier réside dans le `\*PortalName*\PortalASP` dossier.

1. Sur l’ordinateur sur lequel IIS est en cours d’exécution, ouvrez le [!DNL email.asp] fichier dans un éditeur de texte tel que le Bloc-notes.
1. Définissez les variables suivantes :

<table id="table_44F52DA266364DF993C40678A28E0F0D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour cette variable. . . </th> 
   <th colname="col2" class="entry"> Fournissez ces informations . . . </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> smtpserver </td> 
   <td colname="col2"> <p>Nom DNS ou adresse IP du serveur SMTP par l’intermédiaire duquel les messages sont envoyés. </p> <p>Par exemple : <span class="filepath"> mail.hq.omniture.com</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpserverport </td> 
   <td colname="col2"> port sur lequel le serveur SMTP écoute les connexions. Il s'agit généralement du port 25. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sensuel </td> 
   <td colname="col2"> <p>Indique le mode d’envoi du message. Les valeurs sont les suivantes : </p> <p>1 - Envoyez des messages à l’aide du service SMTP installé localement. Utilisez cette valeur si le service SMTP est installé sur l’ordinateur sur lequel le script est exécuté. </p> <p>2 - Envoyez des messages à l'aide du service SMTP sur le réseau. Utilisez cette valeur si le service SMTP n’est pas installé sur l’ordinateur sur lequel le script est exécuté. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpconnectiontimeout </td> 
   <td colname="col2">Temps que <span class="wintitle"> Report</span> doit attendre pour obtenir une réponse du serveur SMTP avant d’interrompre la connexion. </td> 
  </tr> 
 </tbody> 
</table>

1. Pour les [!DNL NewUserEmail()] fonctions et [!DNL UpdateUserEmail()] les fonctions, définissez les variables suivantes :

   <table id="table_91C5E36B84A94C4097EE5993592BE587"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Pour cette variable. . . </th> 
      <th colname="col2" class="entry"> Fournissez ces informations . . . </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> De </td> 
      <td colname="col2">Texte à afficher dans la ligne d’en-tête De dans vos courriers électroniques de confirmation. Cette valeur peut être identique à la valeur <span class="wintitle"> CC</span> . </td> 
   </tr> 
   <tr> 
      <td colname="col1"> CC </td> 
      <td colname="col2"> <p>Facultatif. Adresse électronique valide de la personne ou de l’alias qui doit recevoir une copie de tous les messages concernant les comptes d’utilisateurs nouveaux et modifiés. Vous pouvez spécifier plusieurs adresses électroniques en les séparant par des virgules (sans espace). </p> <p>Par exemple : <span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>Remarque :  Les destinataires reçoivent des copies des courriers électroniques contenant des mots de passe utilisateur. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Sujet </td> 
      <td colname="col2"> Texte que vous souhaitez voir apparaître dans la ligne d’en-tête Objet de vos courriers électroniques de confirmation. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> WebPath </td> 
      <td colname="col2"> <p>Chemin d’accès réel à votre portail. </p> <p>Par exemple : <span class="filepath"> http://portal.omniture.com/Example</span></p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Corps </td> 
      <td colname="col2"> <p>Texte inclus dans les courriers électroniques générés automatiquement. </p> <p>Par exemple, voici le texte par défaut inclus dans les courriers électroniques envoyés pour fournir des informations de connexion : 
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">Les informations de connexion à votre portail Web sont fournies ci-dessous : </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>UserName : username </p><p>Nouveau mot de passe : password </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>Vous pouvez accéder au portail à l’aide de l’URL suivante : </p><p><span class="filepath"> http://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">Une fois connecté au portail, vous pouvez modifier votre mot de passe dans l’onglet <span class="wintitle"> Admin</span> . </li>
      </ul></p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Enregistrez et fermez le fichier.
