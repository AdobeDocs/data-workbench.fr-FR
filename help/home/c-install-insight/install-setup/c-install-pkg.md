---
description: Fichiers inclus dans le package d’installation des outils de données.
title: Fichiers inclus dans le package d’installation
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Fichiers inclus dans le package d’installation{#files-included-in-the-installation-package}

Fichiers inclus dans le package d’installation des outils de données.

Les répertoires suivants sont inclus dans le package Insight.

## Fichiers programme {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

Le fichier exécutable (**[!DNL Insight.exe]**) de station de travail et les fichiers de support sont installés par défaut dans ce dossier.

```
C:\Program Files\Adobe\Adobe Analytics\Data Workbench
```

<table id="table_56BAC85184A04E7680FBB4B36DE73285"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Répertoire </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span></b> </td> 
   <td colname="col2"> Fichier exécutable du client Outils de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> insight.ini </span></b> </td> 
   <td colname="col2"> Définissez la langue et le chemin d’accès du <span class="filepath"> dossier Appdata </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span></b> </td> 
   <td colname="col2"> <p>Les outils de données prennent désormais en charge un éditeur de méthode d’entrée (IME) en tant que processus secondaire de saisie de texte qui vous permet de saisir des caractères internationaux à partir du clavier à l’aide d’une zone de texte flottante. Les outils de données prennent en charge l’anglais par défaut, mais vous permettent également de charger d’autres fichiers pour prendre en charge des langues internationales, comme un clavier chinois virtuel (Pinyin IME). </p> <p>Un nouveau fichier de dictionnaire <span class="filepath"> (Insight.zbin </span>) est requis par l’application cliente pour prendre en charge l’IME. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> Exécutable pour désinstaller Workstation et supprimer des fichiers. </td> 
  </tr> 
 </tbody> 
</table>

## Fichiers AppData {#section-afddeedf8d29451f996fa46b2dfe932c}

Les fichiers de données (**[!DNL Insight.cfg]**, profils, certificats, journaux de suivi et fichiers utilisateur) sont enregistrés par défaut dans :

```
<filepath>
  C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
</filepath>
```

<table id="table_DBA4DBB54C57409C8EC116C686A08560"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Répertoire </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span></b> </td> 
   <td colname="col2"> Fichier de configuration des outils de données. Définit les paramètres dans lesquels les outils de données fonctionnent. Voir <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> Configuration de la connexion au serveur Insight </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Base </span></b> </td> 
   <td colname="col2"> <p>Contient les fichiers de programme pour les outils de données. </p> <p> <p>Remarque :  Vous ne devez ni supprimer ni modifier aucun de ces fichiers. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Certificats </span></b> </td> 
   <td colname="col2"> Contient le fichier de certificat, <span class="filepath"> trust_ca_cert.pem </span>, et le certificat numérique utilisateur nommé pour les outils de données. Voir <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> Téléchargement et installation du certificat numérique </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Configuration </span> </b> </td> 
   <td colname="col2"> Contient les fichiers utilisés pour la configuration de Workstation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Géographie </span></b> </td> 
   <td colname="col2"> Fichiers pour le rendu graphique des visualisations géographiques. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Tracé </span></b> </td> 
   <td colname="col2"> Fichiers journaux générés à partir de Workstation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Profils </span></b> </td> 
   <td colname="col2"> <i>AdobeSC</i>, <i>Predictive Analytics</i> et d’autres fichiers de configuration de profil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> InsightSetup.exe </span></b> </td> 
   <td colname="col2"> Assistant Installation pour installer des ordinateurs client supplémentaires dans le dossier <b> Software/Insight <span class="filepath"> </span></b> . </td> 
  </tr> 
 </tbody> 
</table>

