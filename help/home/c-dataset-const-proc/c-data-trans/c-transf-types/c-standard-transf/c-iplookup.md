---
description: La transformation IPLookup prend les données de géolocalisation ou de géointelligence IP de l’IP (fournies par n’importe quel fournisseur de ces données et converties en un format propriétaire par Adobe) et les transforme en informations géographiques qui peuvent être utilisées dans l’analyse.
title: IPLookup
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
exl-id: 3e9dba44-8d31-49af-8ce0-fecaf92edeb7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 4%

---

# IPLookup{#iplookup}

{{eol}}

La transformation IPLookup prend les données de géolocalisation ou de géointelligence IP de l’IP (fournies par n’importe quel fournisseur de ces données et converties en un format propriétaire par Adobe) et les transforme en informations géographiques qui peuvent être utilisées dans l’analyse.

Deux [!DNL IPLookup] Les transformations sont répertoriées dans le menu Ajouter > *Type de transformation* :

* [!DNL IPLookup] Quova pour [!DNL IP geo-location] data

* [!DNL IPLookup] Digital Envoy pour [!DNL IP geo-intelligence] data

Lors de la définition d’une [!DNL IPLookup] transformation, choisissez la transformation appropriée à votre [!DNL IP geo-location] ou [!DNL IP geo-intelligence] data.

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
   <td colname="col2"> Les conditions dans lesquelles cette transformation est appliquée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier </td> 
   <td colname="col2"> Chemin et nom de fichier du fichier de recherche. Les chemins d’accès relatifs concernent le répertoire d’installation du serveur Data Workbench. Ce fichier se trouve généralement dans le répertoire Recherches du répertoire d’installation du serveur Data Workbench. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse IP </td> 
   <td colname="col2"> Champ à partir duquel lire l’adresse IP. </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sorties </td> 
   <td colname="col2"> <p>Les noms des chaînes de sortie. </p> <p> Le <span class="wintitle"> IPLookup</span> Quova et <span class="wintitle"> IPLookup</span> Les transformations Digital Envoy ont des paramètres de sortie différents. Veillez à utiliser la transformation appropriée pour vos données de recherche IP. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Dans cet exemple, [!DNL IP geo-location] données (dans le fichier de recherche) [!DNL Quova.bin]) est utilisé pour créer les champs de sortie répertoriés. Les sorties (AOL, ASN, Code de zone, etc.) peuvent être utilisées pour créer des dimensions pour l’analyse géographique du trafic des visiteurs.

![](assets/cfg_TransformationType_IPLookup.png)
