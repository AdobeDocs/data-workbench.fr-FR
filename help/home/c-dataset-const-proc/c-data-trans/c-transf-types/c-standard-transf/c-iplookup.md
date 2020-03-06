---
description: La transformation IPLookup utilise les données de géolocalisation IP ou de géointelligence IP (fournies par n’importe quel fournisseur de ces données et converties dans un format propriétaire par Adobe) et transforme les données en informations géographiques pouvant être utilisées dans l’analyse.
solution: Analytics
title: IPLookup
topic: Data workbench
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# IPLookup{#iplookup}

La transformation IPLookup utilise les données de géolocalisation IP ou de géointelligence IP (fournies par n’importe quel fournisseur de ces données et converties dans un format propriétaire par Adobe) et transforme les données en informations géographiques pouvant être utilisées dans l’analyse.

Deux [!DNL IPLookup] transformations sont répertoriées dans le menu Ajouter nouveau > *Type de transformation *:

* [!DNL IPLookup] Quova pour [!DNL IP geo-location] les données

* [!DNL IPLookup] Digital Envoy pour [!DNL IP geo-intelligence] les données

Lors de la définition d’une [!DNL IPLookup] transformation, choisissez la transformation appropriée pour vos [!DNL IP geo-location] données ou [!DNL IP geo-intelligence] données.

<table id="table_C438A30AB5E64160A5C486D6887B1D7E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions d’application de cette transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier </td> 
   <td colname="col2"> Chemin et nom de fichier du fichier de recherche. Les chemins relatifs concernent le répertoire d’installation du serveur de l’outil de données. Ce fichier se trouve généralement dans le répertoire de recherche du répertoire d’installation du serveur de l’outil de données. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse IP </td> 
   <td colname="col2"> Champ à partir duquel lire l’adresse IP. </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sorties </td> 
   <td colname="col2"> <p>Noms des chaînes de sortie. </p> <p> Les transformations <span class="wintitle"> IPLookup</span> Quova et <span class="wintitle"></span> IPLookup Digital Envoy ont des paramètres de sortie différents. Veillez à utiliser la transformation appropriée pour vos données de recherche IP. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Dans cet exemple, [!DNL IP geo-location] les données (dans le fichier de recherche [!DNL Quova.bin]) sont utilisées pour créer les champs de sortie répertoriés. Les sorties (AOL, ASN, Code de zone, etc.) peuvent être utilisées pour créer des dimensions pour l’analyse géographique du trafic des visiteurs.

![](assets/cfg_TransformationType_IPLookup.png)

