---
description: Informations sur les autorisations de fichiers UNIX de Capteur, telles que le module collecteur, le processus d’émetteur, le fichier de configuration, etc.
title: Autorisations des fichiers UNIX dans Capteur
uuid: 04d159b5-6569-48b6-a2db-9a0b40118ffe
exl-id: 07cbc7df-c628-437d-9ca1-b006da8de242
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 6%

---

# Autorisations des fichiers UNIX dans Capteur{#sensor-unix-file-permissions}

{{eol}}

Informations sur les autorisations de fichiers UNIX de Capteur, telles que le module collecteur, le processus d’émetteur, le fichier de configuration, etc.

## Module Collector {#section-49c855baece24c4695184bfcbeeddebf}

<table id="table_0B972ABD2A5342CA8A6FE80EB666298A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualité </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nom du fichier </p> </td> 
   <td colname="col2"> <p>mod_visuel_sciences.so (sur les serveurs web Apache et les serveurs HTTP IBM) </p> <p>libVisual_sciences.so et J2EECollector.jar (sur les serveurs d’applications J2EE) </p> <p>aol_visuel_sciences.so (sur les serveurs web AOL) </p> <p>saf_visuel_sciences.so (sur les serveurs web Sun Java) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorisations par défaut </p> </td> 
   <td colname="col2"> <p>rwx r-x r-x (IBM HTTP et Apache 1.3.x) </p> <p>rwx rwx r-x (Apache 2.0.x) </p> <p>rwx —x —x (serveurs web J2EE, AOL et Sun Java) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lecture par </p> </td> 
   <td colname="col2"> <p>Le serveur web, qui s’exécute parfois en tant qu’utilisateur root, mais s’exécute le plus souvent sous un compte utilisateur spécifique. </p> <p>Si le serveur web s’exécute sous un compte non racine, les autorisations de ce fichier doivent autoriser ce compte à le lire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>S’exécute comme </p> </td> 
   <td colname="col2"> <p>Un processus enfant dans le serveur web </p> <p>Les processus enfants s’exécutent sous un compte utilisateur spécifié dans la configuration de votre serveur web. Sur de nombreux serveurs, il s’agit d’un compte spécial avec des privilèges très limités appelé "personne" — mais tous les serveurs web n’utilisent pas ce compte. Vérifiez le fichier de configuration du serveur web pour déterminer le compte d’utilisateur défini. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lectures à partir de </p> </td> 
   <td colname="col2"> <p>txlogd.conf </p> <p>Fichier diskQueue </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Écrit dans </td> 
   <td colname="col2"> Fichier diskQueue </td> 
  </tr> 
 </tbody> 
</table>

## Le processus d&#39;émission {#section-8af432472e9d4bd9a42270bf27adf33a}

<table id="table_3028CC9640D54016BD8CA7F9CAA34280"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualité </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom du fichier </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorisations par défaut </p> </td> 
   <td colname="col2"> <p>rw- r— r— (serveurs web IBM HTTP, AOL et Sun Java) </p> <p>rw- rw- r— (serveurs web Apache et serveurs applicatifs J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lecture par </td> 
   <td colname="col2"> Le programme d'émetteur </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Écrit par </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## Fichier de configuration {#section-341d85f2abf34a69970a0ff91b7e9123}

<table id="table_79AC614F5435443CB3CFB457B8375704"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualité </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom du fichier </td> 
   <td colname="col2"> txlogd.conf </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorisations par défaut </p> </td> 
   <td colname="col2"> <p>rw- r— r— (serveurs web IBM HTTP, AOL et Sun Java) </p> <p>rw- rw- r— (serveurs web Apache et serveurs applicatifs J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lecture par </td> 
   <td colname="col2"> <p>Module collecteur </p> <p>Le programme d'émetteur </p> <p>Administrateur responsable de l’installation, de la configuration et de la maintenance de Capteur </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Écrit par </td> 
   <td colname="col2"> Administrateur responsable de l’installation, de la configuration et de la maintenance de Capteur </td> 
  </tr> 
 </tbody> 
</table>

## Fichier de l’autorité de certification {#section-2818dff887b8456992bdc589fd8510f3}

<table id="table_ED8BEEEFA91245C3A6645D27B148A5A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualité </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom du fichier </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorisations par défaut </p> </td> 
   <td colname="col2"> <p>rw- r— r— (serveurs web IBM HTTP, AOL et Sun Java) </p> <p>rw- rw- r— (serveurs web Apache et serveurs applicatifs J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lecture par </td> 
   <td colname="col2"> Le programme d'émetteur </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Écrit par </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## File d’attente du disque {#section-0407c52744de41af867d0b7933a69256}

<table id="table_35DB32228E7443FF90BE24AB14CBE54B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualité </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom du fichier </td> 
   <td colname="col2"> Utilisateur défini </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Autorisations par défaut </td> 
   <td colname="col2"> rw- rw- rw- (tous types de serveur) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lecture par </p> </td> 
   <td colname="col2"> <p>Module collecteur </p> <p>Le programme d'émetteur </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Écrit par </p> </td> 
   <td colname="col2"> <p>Module collecteur </p> <p>Le programme d'émetteur </p> </td> 
  </tr> 
 </tbody> 
</table>
