---
description: Informations sur les autorisations de fichiers UNIX Sensor, telles que le module collecteur, le processus d’émetteur, le fichier de configuration, etc.
title: Autorisations de fichier UNIX Sensor
uuid: 04d159b5-6569-48b6-a2db-9a0b40118ffe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Autorisations de fichier UNIX Sensor{#sensor-unix-file-permissions}

Informations sur les autorisations de fichiers UNIX Sensor, telles que le module collecteur, le processus d’émetteur, le fichier de configuration, etc.

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
   <td colname="col2"> <p>mod_Visual_sciences.so (sur les serveurs Web Apache et IBM HTTP) </p> <p>libVisual_sciences.so et J2EECollector.jar (sur les serveurs d’applications J2EE) </p> <p>aol_Visual_sciences.so (sur les serveurs Web AOL) </p> <p>saf_Visual_sciences.so (sur les serveurs Web Java Sun) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorisations par défaut </p> </td> 
   <td colname="col2"> <p>rwx r-x r-x (IBM HTTP et Apache 1.3.x) </p> <p>rwx rwx r-x (Apache 2.0.x) </p> <p>rwx —x —x (serveurs Web J2EE, AOL et Sun Java) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lu par </p> </td> 
   <td colname="col2"> <p>Le serveur Web, qui s’exécute parfois en tant qu’utilisateur root, mais s’exécute plus souvent sous un compte utilisateur spécifique. </p> <p>Si le serveur Web s’exécute sous un compte non racine, les autorisations sur ce fichier doivent permettre à ce compte de le lire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>S’exécute comme </p> </td> 
   <td colname="col2"> <p>Processus enfant dans le serveur Web </p> <p>Les processus enfants s’exécutent sous un compte utilisateur spécifié dans la configuration du serveur Web. Sur de nombreux serveurs, il s'agit d'un compte spécial avec des privilèges très limités appelé "personne" — mais tous les serveurs Web n’utilisent pas ce compte. Vérifiez le fichier de configuration de votre serveur Web pour déterminer le compte utilisateur défini. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lectures de </p> </td> 
   <td colname="col2"> <p>txlogd.conf </p> <p>Fichier diskQueue </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Écrit sur </td> 
   <td colname="col2"> Fichier diskQueue </td> 
  </tr> 
 </tbody> 
</table>

## Le processus des émetteurs {#section-8af432472e9d4bd9a42270bf27adf33a}

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
   <td colname="col2"> <p>rw- r— r— (serveurs Web IBM HTTP, AOL et Sun Java) </p> <p>rw- rw- r— (serveurs Web Apache et serveurs d’applications J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lu par </td> 
   <td colname="col2"> Le programme transmetteur </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Écrit par </td> 
   <td colname="col2"> -- </td> 
  </tr> 
 </tbody> 
</table>

## Le fichier de configuration {#section-341d85f2abf34a69970a0ff91b7e9123}

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
   <td colname="col2"> <p>rw- r— r— (serveurs Web IBM HTTP, AOL et Sun Java) </p> <p>rw- rw- r— (serveurs Web Apache et serveurs d’applications J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lu par </td> 
   <td colname="col2"> <p>Module Collecteur </p> <p>Le programme transmetteur </p> <p>Administrateur responsable de l’installation, de la configuration et de la maintenance de Sensor </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Écrit par </td> 
   <td colname="col2"> Administrateur responsable de l’installation, de la configuration et de la maintenance de Sensor </td> 
  </tr> 
 </tbody> 
</table>

## Fichier d&#39;autorité de certification {#section-2818dff887b8456992bdc589fd8510f3}

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
   <td colname="col2"> <p>rw- r— r— (serveurs Web IBM HTTP, AOL et Sun Java) </p> <p>rw- rw- r— (serveurs Web Apache et serveurs d’applications J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lu par </td> 
   <td colname="col2"> Le programme transmetteur </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Écrit par </td> 
   <td colname="col2"> -- </td> 
  </tr> 
 </tbody> 
</table>

## File d&#39;attente du disque {#section-0407c52744de41af867d0b7933a69256}

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
   <td colname="col2"> rw- rw- rw- (Tous les types de serveur) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lu par </p> </td> 
   <td colname="col2"> <p>Module Collecteur </p> <p>Le programme transmetteur </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Écrit par </p> </td> 
   <td colname="col2"> <p>Module Collecteur </p> <p>Le programme transmetteur </p> </td> 
  </tr> 
 </tbody> 
</table>

