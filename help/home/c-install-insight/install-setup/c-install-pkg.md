---
description: Fichiers inclus dans le package d’installation du Data Workbench.
title: Fichiers inclus dans le package d’installation
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
exl-id: 086fb49c-d492-4670-938b-7ede70a7cd16
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 5%

---

# Fichiers inclus dans le package d’installation{#files-included-in-the-installation-package}

{{eol}}

Fichiers inclus dans le package d’installation du Data Workbench.

Les répertoires suivants sont inclus dans le package Insight.

## Fichiers de programme {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

Exécutable de la station de travail (**[!DNL Insight.exe]**) et les fichiers annexes sont installés par défaut dans ce dossier.

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
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span> </b> </td> 
   <td colname="col2"> Exécutable du client Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> insight.ini </span> </b> </td> 
   <td colname="col2"> Définissez la langue et le chemin d’accès pour le <span class="filepath"> Appdata </span> dossier. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span> </b> </td> 
   <td colname="col2"> <p>Data Workbench prend désormais en charge un éditeur de méthode d’entrée (IME) en tant que processus de saisie de texte secondaire qui vous permet de saisir des caractères internationaux à partir du clavier à l’aide d’une zone de texte flottante. Data Workbench prend en charge l’anglais par défaut, mais vous permet également de charger d’autres fichiers pour prendre en charge les langues internationales, telles qu’un clavier chinois virtuel (Pinyin IME). </p> <p>Un nouveau fichier de dictionnaire <span class="filepath"> (Insight.zbin </span>) est requis par l’application cliente pour prendre en charge l’IME. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> Exécutable pour désinstaller Workstation et supprimer des fichiers. </td> 
  </tr> 
 </tbody> 
</table>

## Fichiers AppData {#section-afddeedf8d29451f996fa46b2dfe932c}

Fichiers de données (**[!DNL Insight.cfg]**, Profils, certificats, journaux de suivi et fichiers utilisateur) sont enregistrés par défaut sur :

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
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span> </b> </td> 
   <td colname="col2"> Le fichier de configuration du Data Workbench. Définit les paramètres au sein desquels Data Workbench fonctionne. Voir <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> Configuration de la connexion à Insight Server </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Base </span> </b> </td> 
   <td colname="col2"> <p>Contient les fichiers de programme pour Data Workbench. </p> <p> <p>Remarque : Vous ne devez supprimer ni modifier aucun de ces fichiers. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Certificats </span> </b> </td> 
   <td colname="col2"> Contient le fichier de certificat, <span class="filepath"> trust_ca_cert.pem </span>et le certificat numérique de l’utilisateur nommé pour Data Workbench. Voir <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> Téléchargement et installation du certificat numérique </a>. </td> 
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
   <td colname="col1"> <b> <span class="filepath"> Trace </span></b> </td> 
   <td colname="col2"> Fichiers journaux générés à partir de la station de travail. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Profils </span></b> </td> 
   <td colname="col2"> <i>AdobeSC</i>, <i>Analyses prédictives</i> et d’autres fichiers de configuration de profil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> InsightSetup.exe </span></b> </td> 
   <td colname="col2"> Assistant de configuration pour installer des ordinateurs client supplémentaires dans <b> <span class="filepath"> Logiciel/Insight </span></b> dossier. </td> 
  </tr> 
 </tbody> 
</table>
