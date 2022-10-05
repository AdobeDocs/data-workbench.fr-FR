---
description: La dimension Campagne est définie dans le profil Marketing du site afin de fournir des fonctionnalités d’analyse de campagne.
title: Dimensions du profil marketing
uuid: 034b4318-58e6-4638-9b13-fac83ff9f826
exl-id: 93804fba-a44b-4cdc-8d67-d4ec0656e742
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 5%

---

# Dimensions du profil marketing{#marketing-profile-dimensions}

{{eol}}

La dimension Campagne est définie dans le profil Marketing du site afin de fournir des fonctionnalités d’analyse de campagne.

<table id="table_27A4B8247F6D4E18BD61041CED7D8805"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Niveau </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Campagne </td> 
   <td colname="col2"> Renommé simple </td> 
   <td colname="col3">Session <p>Opération PRERST ROW </p></td> 
   <td colname="col4"> Identifiant de campagne extrait d’une valeur dans la première requête du visiteur. </td> 
  </tr> 
 </tbody> 
</table>

**Exemples de Dimensions de profil marketing personnalisé**

Vous pouvez incorporer d’autres dimensions de données pour une analyse plus approfondie. Ces dimensions sont ajoutées en incorporant des informations supplémentaires dans le flux de données collectées à des fins d’analyse. Par exemple, le tableau suivant contient certaines des dimensions marketing personnalisées qui ont été ajoutées dans les déploiements pour des clients de différents secteurs d’activité :

| Dimension (personnalisé) | Description |
|---|---|
| Date de campagne par e-mail | Analyse la date de la campagne (première valeur) à partir des chaînes de requête de campagne par e-mail. |
| Détails de la campagne par e-mail | Collecte la chaîne de valeur associée à la variable de chaîne de requête de campagne par e-mail. |
| Segment de campagne par e-mail | Analyse le segment de campagne (troisième valeur) à partir des chaînes de requête de campagne par e-mail. |
| Type de campagne par e-mail | Analyse le type de campagne (seconde valeur) à partir des chaînes de requête de campagne par e-mail. |
| Détails de la campagne marketing | Collecte la chaîne de valeur associée aux variables de chaîne de requête de campagne marketing. |
| Propriétaire de la campagne marketing | Analyse le propriétaire de la campagne (quatrième valeur) à partir des chaînes de requête de campagne marketing. |
| Source de campagne marketing | Analyse la source de la campagne (première valeur) à partir des chaînes de requête de la campagne marketing. |
| Type de campagne marketing | Analyse le type de campagne (seconde valeur) à partir des chaînes de requête de campagne marketing. |
| Détails des campagnes PPC | Collecte la chaîne de valeur associée à la variable de chaîne de requête ppc. |
