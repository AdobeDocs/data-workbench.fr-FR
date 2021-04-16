---
description: Un filtre est une expression qui définit un sous-ensemble de données dans un jeu de données.
title: Syntaxe des expressions de filtre
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
exl-id: 515c1645-69c8-4990-a913-d2d505c6fe51
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 1%

---

# Syntaxe des expressions de filtre{#syntax-for-filter-expressions}

Un filtre est une expression qui définit un sous-ensemble de données dans un jeu de données.

Un filtre admet ou rejette chaque élément de chaque dimension en fonction des relations entre les dimensions.

Les filtres peuvent être modifiés à l&#39;aide de [!DNL Filter Editor]. Voir [Éditeurs de filtres](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

Dans le tableau suivant, chaque description de syntaxe comprend un exemple d’expression de mesure utilisant ce filtre. Par exemple, Sessions[True] est une mesure définie à l’aide du filtre &quot;True&quot;. La mesure Sessions[True] est identique à la mesure Sessions, car le filtre True admet chaque élément de la dimension Session.

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
   <td colname="col2"> <p>Admet les éléments rejetés par Filtre. </p> <p>Exemple : Sessions[ not Page="A" ] indique le nombre de sessions qui n’ont pas consulté la page A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FiltreA et FiltreB </p> </td> 
   <td colname="col2"> <p>Admet les éléments admis par FilterA et FilterB. </p> <p>Exemple : Sessions[ Page="A" et Page="B" ] indique le nombre de sessions qui ont visité les pages A et B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FiltreA ou FiltreB </p> </td> 
   <td colname="col2"> <p>Admet les éléments admis par FilterA ou FilterB. </p> <p>Exemple : Sessions[ Page="A" ou Page="B" ] indique le nombre de sessions qui ont visité la page A, la page B ou les deux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtrer par point </p> </td> 
   <td colname="col2"> <p>Admet le jeu d’éléments de la dimension Dim admis par Filtre. </p> <p>Exemple : Sessions[ Page="/accueil" par Visiteur ] est le nombre de sessions appartenant à un Visiteur qui a vu la page "/accueil". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identifiant </p> </td> 
   <td colname="col2"> <p>Filtres de référence définis autrement dans le profil. </p> <p>Exemple : Sessions[ Broken_Session_Filter ] est le nombre de sessions admises par le filtre de session rompue. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Value" </p> </td> 
   <td colname="col2"> <p>Admet l’élément donné de la dimension Dim. </p> <p>Exemple : Sessions[ Page="A" ] indique le nombre de sessions qui ont consulté la page A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; "Value" </p> <p>Dim != “Valeur” </p> </td> 
   <td colname="col2"> <p>Admet tous les autres éléments de la dimension Dim. </p> <p>Exemple : Sessions[ Page&lt;&gt;"A" ] est le nombre de sessions qui ont visité une page autre que A. </p> </td> 
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
   <td colname="col2"> <p>Admet les éléments de la dimension Dim correspondant à l’expression régulière donnée. Dim ne doit pas être une dimension dénominale ou dénombrable. </p> <p>Exemple : Sessions[ URI correspond à ".*/product/.*" ] est le nombre de sessions qui ont consulté une page dans un répertoire de produits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim ne correspond pas à "Expr" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim ne correspondant pas à l’expression régulière donnée. Dim ne doit pas être une dimension dénominale ou dénombrable. </p> <p>Exemple : Sessions[ URI non-correspond à ".*\.jsp" ] est le nombre de sessions qui ont visité une page qui n'était pas une page JSP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt; "Value" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim avec des valeurs ordinales inférieures à la valeur ordinale de l’élément "Value". Si "Valeur" n’est pas un élément de dimension, on suppose qu’il est plus grand que tout élément actif de la dimension. </p> <p>Exemple : Sessions[ Mois &lt; "Jul ‘04" ] est le nombre de sessions qui ont eu lieu avant juillet 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &gt; "Value" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim avec des valeurs ordinales supérieures à la valeur ordinale de l’élément "Value". Si "Valeur" n’est pas un élément de dimension, on suppose qu’il est plus grand que tout élément actif de la dimension. </p> <p>Exemple : Sessions[ Mois &gt; "Juil ‘04" ] est le nombre de sessions qui ont eu lieu après juillet 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim avec des valeurs ordinales inférieures ou égales à la valeur ordinale de l’élément "Valeur". Si "Valeur" n’est pas un élément de dimension, on suppose qu’il est plus grand que tout élément actif de la dimension. </p> <p>Exemple : Sessions[ Session_Number &lt;= "2" ] indique le nombre de sessions qui ont été la première ou la deuxième session pour un visiteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= "Value" </td> 
   <td colname="col2"> <p>Admet les éléments de la dimension Dim avec des valeurs ordinales supérieures ou égales à la valeur ordinale de l’élément "Valeur". Si "Valeur" n’est pas un élément de dimension, on suppose qu’il est plus grand que tout élément actif de la dimension. </p> <p>Exemple : Sessions[ Session_Number &gt;= "5" ] est le nombre de sessions qui étaient la cinquième session ou plus pour un visiteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>n’importe quel Dim </p> </td> 
   <td colname="col2"> <p>Admet tous les éléments de la dimension Dim. </p> <p>Exemple : Sessions[ n'importe quelle Vue de page ] est le nombre de sessions avec au moins une vue de page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>aucun point </p> </td> 
   <td colname="col2"> <p>Admet les éléments rejetés par tout Dim. </p> <p>Exemple : Sessions[ no Page_Vue ] correspond au nombre de sessions sans vue de page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(FILTRE) </p> </td> 
   <td colname="col2"> <p>identique à FILTER ; permet de grouper une partie d’une expression de filtrage. </p> </td> 
  </tr> 
 </tbody> 
</table>
