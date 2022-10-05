---
description: Un filtre est une expression qui définit un sous-ensemble des données d’un jeu de données.
title: Syntaxe des expressions de filtre
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
exl-id: 515c1645-69c8-4990-a913-d2d505c6fe51
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 1%

---

# Syntaxe des expressions de filtre{#syntax-for-filter-expressions}

{{eol}}

Un filtre est une expression qui définit un sous-ensemble des données d’un jeu de données.

Un filtre admet ou refuse chaque élément de chaque dimension en fonction des relations entre les dimensions.

Les filtres peuvent être modifiés à l’aide du [!DNL Filter Editor]. Voir [Éditeurs de filtre](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

Dans le tableau suivant, chaque description de syntaxe comprend un exemple d’expression de mesure utilisant ce filtre. Par exemple, sessions[True] est une mesure définie à l’aide du filtre &quot;True&quot;. Sessions[True] est identique à la mesure Sessions , car le filtre True admet chaque élément de la dimension Session .

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>Filtre constant. Admet chaque élément de chaque dimension </p> <p>Exemple : Sessions[ True ] est identique aux sessions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False </p> </td> 
   <td colname="col2"> <p>Filtre constant. Rejette chaque élément de chaque dimension. </p> <p>Exemple : Sessions[ False ] est toujours zéro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ne pas filtrer </p> </td> 
   <td colname="col2"> <p>Admet les éléments rejetés par Filtre. </p> <p>Exemple : Sessions[ not Page="A" ] est le nombre de sessions qui n’ont pas consulté la page A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA et FilterB </p> </td> 
   <td colname="col2"> <p>Admet les éléments admis par FilterA et FilterB. </p> <p>Exemple : Sessions[ Page="A" et Page="B" ] est le nombre de sessions qui ont consulté les pages A et B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA ou FilterB </p> </td> 
   <td colname="col2"> <p>Admet les éléments admis par FilterA ou FilterB. </p> <p>Exemple : Sessions[ Page="A" ou Page="B" ] est le nombre de sessions qui ont consulté la page A, la page B ou les deux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtrage par dimension </p> </td> 
   <td colname="col2"> <p>Admet l’ensemble des éléments de la dimension Dim admis par le filtre. </p> <p>Exemple : Sessions[ Page="/home" par Visiteur ] est le nombre de sessions appartenant à un visiteur qui a vu la page "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identifiant </p> </td> 
   <td colname="col2"> <p>Filtres de référence définis autrement dans le profil. </p> <p>Exemple : Sessions[ Broken_Session_Filter ] est le nombre de sessions admises par le filtre de session rompu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Value" </p> </td> 
   <td colname="col2"> <p>Admet l’élément donné de la dimension Dim. </p> <p>Exemple : Sessions[ Page="A" ] est le nombre de sessions qui ont consulté la page A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; "Value" </p> <p>Dim != “Valeur” </p> </td> 
   <td colname="col2"> <p>Admet tous les autres éléments de la dimension Dim. </p> <p>Exemple : Sessions[ Page&lt;&gt;"A" ] est le nombre de sessions qui ont consulté n’importe quelle page autre que A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim = #Ordinal </td> 
   <td colname="col2"> <p>Admet l’élément de la dimension Dim avec la valeur ordinale donnée. </p> <p>Exemple : Sessions[ Month=#0 ] est le nombre de sessions du premier mois du jeu de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; #Ordinal </p> <p>Dim != #Ordinal </p> </td> 
   <td colname="col2"> <p>Admet tous les autres éléments de la dimension Dim. </p> <p>Exemple : Sessions[ Session_Value &lt;&gt; #0 ] est le nombre de sessions avec une valeur de session non nulle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim correspond à "Expr" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim correspondant à l’expression régulière donnée. Dim ne doit pas être une dimension dénormalisée ou dénombrable. </p> <p>Exemple : Sessions[ URI correspond à ".*/product/.*" ] est le nombre de sessions qui ont consulté n’importe quelle page dans un répertoire de produits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim ne correspond pas à "Expr" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim ne correspondant pas à l’expression régulière donnée. Dim ne doit pas être une dimension dénormalisée ou dénombrable. </p> <p>Exemple : Sessions[ URI ne correspond pas à ".*\.jsp" ] est le nombre de sessions qui ont consulté une page qui n’était pas une page JSP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt; "Value" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim avec des valeurs ordinales inférieures à la valeur ordinale de l’élément "Valeur". Si "Valeur" n’est pas un élément de dimension, on suppose qu’il est plus grand que tout élément actif de la dimension. </p> <p>Exemple : Sessions[ Month &lt; "Jul ‘04" ] est le nombre de sessions qui ont eu lieu avant juillet 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &gt; "Value" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim avec des valeurs ordinales supérieures à la valeur ordinale de l’élément "Valeur". Si "Valeur" n’est pas un élément de dimension, on suppose qu’il est plus grand que tout élément actif de la dimension. </p> <p>Exemple : Sessions[ Mois &gt; "Juil ‘04" ] est le nombre de sessions qui ont eu lieu après juillet 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim avec des valeurs ordinales inférieures ou égales à la valeur ordinale de l’élément "Valeur". Si "Valeur" n’est pas un élément de dimension, on suppose qu’il est plus grand que tout élément actif de la dimension. </p> <p>Exemple : Sessions[ Session_Number &lt;= "2" ] est le nombre de sessions qui étaient la première ou la deuxième session d’un visiteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= "Value" </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim avec des valeurs ordinales supérieures ou égales à la valeur ordinale de l’élément "Valeur". Si "Valeur" n’est pas un élément de dimension, on suppose qu’il est plus grand que tout élément actif de la dimension. </p> <p>Exemple : Sessions[ Session_Number &gt;= "5" ] est le nombre de sessions qui étaient la cinquième session ou plus d’un visiteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>n’importe quel Dim </p> </td> 
   <td colname="col2"> <p>Admet tous les éléments de la dimension Dim. </p> <p>Exemple : Sessions[ any Page_View ] est le nombre de sessions avec au moins une page vue. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>no Dim </p> </td> 
   <td colname="col2"> <p>Admet les éléments que tout Dim rejette. </p> <p>Exemple : Sessions[ no Page_View ] est le nombre de sessions sans page vue. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(FILTRE) </p> </td> 
   <td colname="col2"> <p>Identique au FILTRE ; utilisé pour regrouper une partie d’une expression de filtre. </p> </td> 
  </tr> 
 </tbody> 
</table>
