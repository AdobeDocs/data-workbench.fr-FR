---
description: Un filtre est une expression qui définit un sous-ensemble des données d’un jeu de données.
solution: Analytics
title: Syntaxe des expressions de filtre
topic: Data workbench
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Syntaxe des expressions de filtre{#syntax-for-filter-expressions}

Un filtre est une expression qui définit un sous-ensemble des données d’un jeu de données.

Un filtre admet ou rejette chaque élément de chaque dimension en fonction des relations entre les dimensions.

Les filtres peuvent être modifiés à l’aide du [!DNL Filter Editor]. Voir [Filtrage des éditeurs](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

Dans le tableau suivant, chaque description de syntaxe comprend un exemple d’expression de mesure utilisant ce filtre. Par exemple,[SessionsTrue] est une mesure définie à l’aide du filtre &quot;True&quot;. La mesure[SessionsTrue] est identique à la mesure Sessions, car le filtre True admet tous les éléments de la dimension Session.

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>Filtre permanent. Admet chaque élément de chaque dimension </p> <p>Exemple : Sessions[ True ] est identique à Sessions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False </p> </td> 
   <td colname="col2"> <p>Filtre permanent. Rejette chaque élément de chaque dimension. </p> <p>Exemple : Sessions[ False ] est toujours zéro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pas de filtre </p> </td> 
   <td colname="col2"> <p>Admet les éléments rejetés par le filtre. </p> <p>Exemple : Sessions[ not Page="A" ] correspond au nombre de sessions qui n’ont pas consulté la page A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA et FilterB </p> </td> 
   <td colname="col2"> <p>Admet les éléments admis par FilterA et FilterB. </p> <p>Exemple : Sessions[ Page="A" et Page="B" ] indique le nombre de sessions qui ont visité les pages A et B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA ou FilterB </p> </td> 
   <td colname="col2"> <p>Admet les éléments admis par FilterA ou FilterB. </p> <p>Exemple : Sessions[ Page="A" ou Page="B" ] indique le nombre de sessions qui ont consulté la page A, la page B ou les deux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtrer par défaut </p> </td> 
   <td colname="col2"> <p>Admet le jeu d’éléments de la dimension Dim admis par le filtre. </p> <p>Exemple : Sessions[ Page="/accueil" par le visiteur ] est le nombre de sessions appartenant à un visiteur qui a vu la page "/accueil". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identificateur </p> </td> 
   <td colname="col2"> <p>Filtres de référence définis autrement dans le profil. </p> <p>Exemple : Sessions[ Broken_Session_Filter ] correspond au nombre de sessions admises par le filtre de session rompue. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Value" </p> </td> 
   <td colname="col2"> <p>Admet l’élément donné de la dimension Dim. </p> <p>Exemple : Sessions[ Page="A" ] est le nombre de sessions qui ont consulté la page A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; "Value" </p> <p>Dim != “Valeur” </p> </td> 
   <td colname="col2"> <p>Admet tous les autres éléments de la dimension Dim. </p> <p>Exemple : Sessions[ Page&lt;&gt;"A" ] est le nombre de sessions qui ont consulté une page autre que A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim = #Ordinal </td> 
   <td colname="col2"> <p>Admet l’élément de la dimension Dim avec la valeur ordinale donnée. </p> <p>Exemple : Sessions[ Mois=#0 ] correspond au nombre de sessions du premier mois du jeu de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; #Ordinal </p> <p>Dim != #Ordinal </p> </td> 
   <td colname="col2"> <p>Admet tous les autres éléments de la dimension Dim. </p> <p>Exemple : Sessions[ Session_Value &lt;&gt; #0 ] correspond au nombre de sessions dont la valeur de session n’est pas nulle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim correspond à "Expr" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim correspondant à l’expression régulière donnée. Dim ne doit pas être une dimension Denormal ou dénombrable. </p> <p>Exemple : Sessions[ URI correspond à ".*/product/.*" ] est le nombre de sessions qui ont consulté une page du répertoire d’un produit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim ne correspond pas à "Expr" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim ne correspondant pas à l’expression régulière donnée. Dim ne doit pas être une dimension Denormal ou dénombrable. </p> <p>Exemple : Sessions[ L'URI ne correspond pas à ".*\.jsp" ] est le nombre de sessions qui ont consulté une page qui n'était pas une page JSP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt; "Value" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim avec des valeurs ordinales inférieures à la valeur ordinale de l’élément "Valeur". Si "Valeur" n’est pas un élément de dimension, il est supposé être plus grand que n’importe quel élément actuel de la dimension. </p> <p>Exemple : Sessions[ Mois &lt; "Jul ‘04’ ] est le nombre de sessions qui ont eu lieu avant juillet 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &gt; "Value" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim avec des valeurs ordinales supérieures à la valeur ordinale de l’élément "Valeur". Si "Valeur" n’est pas un élément de dimension, il est supposé être plus grand que n’importe quel élément actuel de la dimension. </p> <p>Exemple : Sessions[ Mois &gt; "Jul ‘04’ ] est le nombre de sessions qui ont eu lieu après juillet 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim avec des valeurs ordinales inférieures ou égales à la valeur ordinale de l’élément "Valeur". Si "Valeur" n’est pas un élément de dimension, il est supposé être plus grand que n’importe quel élément actuel de la dimension. </p> <p>Exemple : Sessions[ Session_Number &lt;= "2" ] correspond au nombre de sessions qui ont été la première ou la deuxième session d’un visiteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= "Value" </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim avec des valeurs ordinales supérieures ou égales à la valeur ordinale de l’élément "Valeur". Si "Valeur" n’est pas un élément de dimension, il est supposé être plus grand que n’importe quel élément actuel de la dimension. </p> <p>Exemple : Sessions[ Session_Number &gt;= "5" ] est le nombre de sessions qui étaient la cinquième session ou plus d’un visiteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>n’importe quel point </p> </td> 
   <td colname="col2"> <p>Admet tous les éléments de la dimension Dim. </p> <p>Exemple : Sessions[ n'importe quelle page vue ] est le nombre de sessions avec au moins une page vue. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>no Dim </p> </td> 
   <td colname="col2"> <p>Admet les éléments rejetés par tout Dim. </p> <p>Exemple : Sessions[ no Page_View ] est le nombre de sessions sans page vue. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(FILTRE) </p> </td> 
   <td colname="col2"> <p>identique à FILTER; permet de grouper une partie d’une expression de filtre. </p> </td> 
  </tr> 
 </tbody> 
</table>

