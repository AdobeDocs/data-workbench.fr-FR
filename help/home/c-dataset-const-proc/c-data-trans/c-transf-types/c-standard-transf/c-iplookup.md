---
description: La transformation IPLookup utilise les données de géolocalisation IP ou de géointelligence IP (fournies par tout fournisseur de ces données et converties en format propriétaire par Adobe) et transforme les données en informations géographiques pouvant être utilisées en analyse.
title: IPLookup
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
exl-id: 3e9dba44-8d31-49af-8ce0-fecaf92edeb7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 4%

---

# IPLookup{#iplookup}

La transformation IPLookup utilise les données de géolocalisation IP ou de géointelligence IP (fournies par tout fournisseur de ces données et converties en format propriétaire par Adobe) et transforme les données en informations géographiques pouvant être utilisées en analyse.

Deux transformations [!DNL IPLookup] sont répertoriées dans le menu Ajouter > *Type de transformation *:

* [!DNL IPLookup] Quova pour  [!DNL IP geo-location] les données

* [!DNL IPLookup] Digital Envoy pour  [!DNL IP geo-intelligence] les données

Lors de la définition d&#39;une transformation [!DNL IPLookup], choisissez la transformation appropriée pour vos données [!DNL IP geo-location] ou [!DNL IP geo-intelligence].

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
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez entrer n'importe quel nom ici. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions d'application de cette transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier </td> 
   <td colname="col2"> Chemin d’accès et nom de fichier du fichier de recherche. Les chemins relatifs concernent le répertoire d’installation du serveur de l’outil de données. Ce fichier se trouve généralement dans le répertoire Lookups du répertoire d’installation du serveur de l’outil de données. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse IP </td> 
   <td colname="col2"> Champ à partir duquel lire l’adresse IP. </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sorties </td> 
   <td colname="col2"> <p>Noms des chaînes de sortie. </p> <p> Les transformations <span class="wintitle"> IPLookup</span> Quova et <span class="wintitle"> IPLookup</span> Digital Envoy ont des paramètres de sortie différents. Veillez à utiliser la transformation appropriée pour vos données de recherche IP. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Dans cet exemple, les données [!DNL IP geo-location] (dans le fichier de recherche [!DNL Quova.bin]) sont utilisées pour créer les champs de sortie répertoriés. Les sorties (AOL, ASN, Code de zone, etc.) peuvent être utilisées pour créer des dimensions pour l’analyse géographique du trafic visiteur.

![](assets/cfg_TransformationType_IPLookup.png)
