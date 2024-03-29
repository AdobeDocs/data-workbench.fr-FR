---
description: Les expressions de Dimension ne sont jamais utilisées seules, mais peuvent être utilisées partout où une dimension est appelée dans une mesure ou une expression de filtre.
title: Syntaxe des expressions de dimension
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
exl-id: 58609e31-8ad8-418b-9a9f-40462d6443f7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 0%

---

# Syntaxe des expressions de dimension{#syntax-for-dimension-expressions}

{{eol}}

Les expressions de Dimension ne sont jamais utilisées seules, mais peuvent être utilisées partout où une dimension est appelée dans une mesure ou une expression de filtre.

1. Les mots soulignés doivent être littéralement saisis dans le texte de l’expression.
1. Le formulaire `{TEXT}?` représente le texte facultatif.
1. Le formulaire `{TEXT}*` représente le texte qui peut se produire zéro ou plusieurs fois.
1. Le formulaire `{A | B | C |...}` représente le texte qui comprend exactement l’une des options données, comme A, B ou C....
1. Le formulaire `[A,B)` représente une plage de nombres, de A à B, mais pas.

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identifiant </p> </td> 
   <td colname="col2"> <p>Un identifiant fait référence à une dimension nommée. Pour connaître les règles régissant les identifiants légaux, voir <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Syntaxe des identificateurs </a>. </p> <p>Exemple : Sessions[ Session_Number = "1" ] est le nombre de sessions dont le numéro de session est "1". Le numéro de session est une dimension nommée référencée par l’identifiant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Dimension) </p> </td> 
   <td colname="col2"> <p>Le résultat de (Dimension) est le même que le résultat de la Dimension. Les parenthèses spécifient l’ordre des opérations dans une expression. </p> <p>Exemple : Sessions[ (Page) = "/home" ] est le nombre de sessions qui visitent la page "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim par niveau </p> </td> 
   <td colname="col2"> <p>Définit une dimension qui contient les mêmes éléments que la dimension Dim, mais qui est liée à d’autres dimensions au niveau de la dimension. </p> <p>En particulier, un élément de la nouvelle dimension se rapporte aux mêmes éléments de niveau que le même élément de dimension et se rapporte aux éléments de toute autre dimension qui se rapportent à l’un de ces éléments de niveau. </p> <p>Exemple : Sessions[ (Page par visiteur)="/home" ] est le nombre de sessions de visiteurs qui ont visité la page "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Définit une dimension qui contient les mêmes éléments que la dimension Dim. L’élément eth du niveau de dimension se rapporte au même élément de la nouvelle dimension que l’élément Dim associé à l’élément e+Nth du niveau, à condition que les éléments eth et e+Nth du niveau se rapportent au même élément du groupe de dimensions. </p> <p>Exemple : Page_Views[ shift(Page, Page_View, Session, 1)="/home" ] est le nombre de pages vues pour lesquelles la prochaine page vue dans la même session est "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Similaire à shift (Dim, Level, Group, N), sauf que si la dimension contient des valeurs vides, elles sont ignorées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> Définit une dimension qui classe les éléments du niveau d’après une liste de filtres. Les éléments de la nouvelle dimension sont les chaînes données en tant qu’arguments. Chaque élément du niveau correspond au premier élément de la dimension de segment dont le filtre admet l’élément du niveau. Ceci est similaire à la visualisation de segment. </p> <p>Exemple : segment(Visiteur, "Visiteurs uniques" -&gt; Visitor_Sessions = 1, "Visiteurs très fidèles" -&gt; Visitor_Sessions &gt; 10, "Tous les autres" -&gt; True) crée une dimension qui classe les visiteurs en trois groupes — Les visiteurs une fois sont ceux qui n’ont qu’une seule session, les visiteurs très fidèles sont ceux qui ont plus de dix sessions et tous les autres visiteurs ont une valeur "Tous les autres." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Start {, Size}? }?) </p> </td> 
   <td colname="col2"> <p>Définit une dimension dont les éléments sont des plages de nombres (de taille fixe, par exemple, [0-9], [10-19],...). Les éléments de niveau sont associés à l’élément de la plage dim du compartiment dont la plage contient la valeur de Mesure pour cet élément de niveau. Format est la chaîne de format printf utilisée pour formater les éléments de Mesure. </p> <p>Exemple : Si Page_Duration_Minutes est une dimension de niveau Page vue qui représente le nombre de minutes passées sur chaque page, alors bucket(Session, sum(Page_Duration_Minutes, Page_View), 100, "%0.0f minutes", 0, 5) est une dimension de niveau session qui représente le nombre de minutes passées dans chaque session ; ses éléments sont des intervalles de 5 minutes <code>{[0-5), [5-10),...,[495-500)}</code>. </p> <p>Start est la valeur de départ du premier intervalle (par défaut : 0) et Taille est la taille de l’intervalle (par défaut : 1). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prefix(Level {,ElementName-&gt;(Prefix{,Prefix}* )}* ) </p> </td> 
   <td colname="col2"> <p>Définit une dimension dont les éléments sont les chaînes ElementName données et sont associés aux jeux correspondants de chaînes Prefix. Les éléments de niveau sont associés à l’élément du préfixe dim, associé au préfixe le plus long associé au nom de l’élément de niveau donné. Les préfixes se terminant par le caractère spécial "$" doivent correspondre exactement. </p> <p>Par exemple, prefix(URI, "Products" -&gt; ("/products/"), "Services" -&gt; ("/services/", "/products/service/"), "Warranties" -&gt; ("/products/warranty.html$", "/services/warranty.html$", "All Else" -&gt; ("/") crée une dimension qui classe les URI dans les quatre catégories répertoriées. L’effet sur différentes pages est le suivant : </p> <p>/products/warranty.html entre dans la garantie, car elle correspond exactement au préfixe /products/warranty.html$. </p> <p>/products/cars/specialcar.html Va dans les produits, car il correspond au préfixe /products/ et ne correspond plus au préfixe </p> <p>/products/service/something.html accède à Services, car il correspond au préfixe /products/service/ qui est plus long que le préfixe /products/ . </p> <p>/companyinfo/aboutus.html entre dans la catégorie "Tous les autres", puisque le seul préfixe correspondant est "/". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>latence(Level, Clip, Dim, Filter, MaxBefore, MaxAfter, FormatString) </p> </td> 
   <td colname="col2"> <p>Voir <a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a"> Création de Dimensions de latence </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cartesian_product(Separator {,Dim}*) </p> </td> 
   <td colname="col2"> <p>Définit une dimension dont les éléments sont toutes les combinaisons ("le produit cartésien") des éléments des dimensions données. Le nom de chaque élément est constitué de la concaténation des éléments correspondants dans les dimensions d’entrée, séparés par la chaîne du Séparateur donnée. </p> <p>Par exemple, si la dimension D1 contient des éléments {"a", "b"} et que la dimension D2 contient les éléments {"x", "y"}, alors produit cartésien("-", D1, D2) contient les éléments {"a-x", "a-y", "b-x", "b-y"}. </p> <p>Notez que, en interne, chacune des dimensions d’entrée est traitée comme si le nombre de ses éléments était la puissance supérieure suivante de deux. Cela entraîne la présence d’éléments factices dans le produit cartésien. Lors de l’utilisation de l’API du Data Workbench, selon le format de sortie, ces éléments peuvent être omis ou affichés sous la forme "#nnn", où nn est l’ordinal de l’élément (et doit être ignoré par le client). </p> <p>Par exemple, dans l’exemple ci-dessus, si D2 avait les trois éléments {"x", "y", "z"}, il serait traité comme s’il avait quatre éléments, et le produit cartésien aurait les éléments {"a-x", "a-y", "a-z", "#3", "b-x", "b-y", "b-z", "#7"}. </p> <p>Si aucune dimension n’est donnée, le résultat est une dimension avec un élément, "#0", qui équivaut à la dimension Aucun . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>le plus proche_countable(Dim) </p> </td> 
   <td colname="col2"> <p>Fait référence à une dimension déjà existante : l’ancêtre dénombrable le plus proche de Dim dans le schéma. Par exemple, le compte à rebours le plus proche (URI) est identique à Page_View. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>normalized(Dim,Count) </p> </td> 
   <td colname="col2"> <p>Définit une dimension normalisée à partir de la dimension Denormal, avec jusqu’à des éléments Comptage . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>Définit une dimension qui comporte un sous-ensemble des éléments de la dimension Dim, dont les éléments représentent des tranches de temps, par exemple, jours, semaines ou années. </p> <p>Le sous-ensemble est une plage autour d’une heure spécifique, la valeur de la mesure constante TimeMetric, qui est interprétée comme une valeur temporelle en secondes depuis minuit UTC le 1er janvier 1970. La plage comporte des éléments Count, dont le dernier est des éléments Offset après l’élément de la dimension donnée dont le nom est le résultat du formatage de la valeur de la mesure avec la chaîne FormatString donnée. FormatString utilise les mêmes échappement % que la fonction de bibliothèque C standard strftime. </p> <p>Si la valeur de trimToData est true, tous les éléments situés au début de la dimension obtenue, qui se trouveraient avant le début de la dimension Dim, sont supprimés. S’il est défini sur false, le nombre exact d’éléments spécifié par le paramètre Count sera toujours présent. Notez qu’il peut toujours y avoir des éléments à la fin de la dimension résultante qui ne sont pas réellement dans Dim. </p> <p>Le WeekStart facultatif, s’il est spécifié, doit être un des { "Sun", "Lun", "Tue", "Wed", "Thu", "Fri", "Sat" }. Elle modifie TimeMetric en la faisant reculer à l’occurrence la plus récente de ce jour de semaine. </p> <p>Exemple : Si Semaine comporte les éléments { "10/03/10", "10/10/10", ..., "12/12/10" } et que la mesure intégrée En tant que de a la valeur 1292348109 (représentant une heure à la mi-décembre 14 décembre 2010), alors last n(Week, As_Of, "%m/%d/%y", 4, 0, false, "Sun") définit la dimension avec des éléments { "12/12/10", "12/19/10", ", "12/23/10", "12/30/10" }. </p> <p>Exemple 2 : Si la dimension Semaine ne contient que les éléments {"12/19/10", "12/26/10", ..., "01/30/11"} et que la mesure À partir de est comme ci-dessus, alors la dernière n(Semaine, As_Of, "%m/%d/%y", 4, 0, true, "Sun") donne une dimension avec des éléments {"12/19/10", "12/23/10", "12/30/10"}. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_previous_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Définit une dimension qui comporte un sous-ensemble des éléments de Dim, dont les éléments représentent des jours. Le sous-ensemble est une plage autour d’une heure spécifique, la valeur de la mesure constante TimeMetric, qui est interprétée comme une valeur temporelle en secondes depuis minuit UTC le 1er janvier 1970. La plage inclura les éléments correspondant à chaque jour dans les n mois précédant l'heure indiquée. Si includeThisMonth a la valeur true, la plage inclut également chaque jour du mois qui contient l’heure spécifiée. </p> <p>FormatString spécifie la mise en forme des éléments de Dim, en utilisant des échappement "%" comme dans la fonction de bibliothèque C standard strftime. </p> <p>Si la valeur de trimToData est true, tous les éléments situés au début de la dimension obtenue, qui se trouveraient avant le début de la dimension Dim, sont supprimés. S’il est défini sur false, le nombre exact d’éléments spécifié par le paramètre Count sera toujours présent. Notez qu’il peut toujours y avoir des éléments à la fin de la dimension résultante qui ne sont pas réellement dans Dim. </p> <p>Exemple : Si Day comporte les éléments { "01/01/10", "01/02/10", ..., "12/31/10" } et que la mesure intégrée "A partir de" a la valeur 1292348109 (représentant une heure à la mi-décembre 14 décembre 2010), alors les jours des mois précédents (Jour, Comme_de, "%m/%d/%y", 2, false, false) auront des éléments { "10/01/10", "10/02/10", . ., "11/30/10" }. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>Similaire aux jours des mois précédents, à la différence que les éléments ne correspondent qu’aux jours du même mois, à l’heure spécifiée par TimeMetric. Si allMonth est défini sur true, un élément sera présent pour chaque jour du mois approprié. sinon, seuls les jours à partir du premier du mois approprié jusqu’au jour contenant l’heure spécifiée font partie de la dimension. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_future_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Similaire aux jours des mois précédents, sauf que les éléments correspondent aux jours des mois qui suivent, plutôt qu’avant, le mois contenant l’heure spécifiée par la mesure Temps. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hours_of_day(Dim, Metric, TimeFormatString, nDaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>Définit une dimension qui comporte un sous-ensemble des éléments de Dim, dont les éléments représentent les heures. Le sous-ensemble est une plage autour d’une heure spécifique, la valeur de la mesure constante TimeMetric, qui est interprétée comme une valeur temporelle en secondes depuis minuit UTC le 1er janvier 1970. La plage inclut les éléments correspondant à chaque heure du jour nDaysForward après le jour contenant l’heure spécifiée par la mesure de temps. </p> <p>FormatString spécifie la mise en forme des éléments de Dim, en utilisant des échappement "%" comme dans la fonction de bibliothèque C standard strftime. La chaîne de format doit toujours générer une chaîne représentant minuit au début du jour de l’heure transmise. </p> <p>Si la valeur de trimToData est true, tous les éléments situés au début de la dimension obtenue, qui se trouveraient avant le début de la dimension Dim, sont supprimés. S’il est défini sur false, le nombre exact d’éléments spécifié par le paramètre Count sera toujours présent. Notez qu’il peut toujours y avoir des éléments à la fin de la dimension résultante qui ne sont pas réellement dans Dim. </p> <p>Exemple : Si l’heure comporte les éléments { "01/01/10 00:00", "01/01/10 01:00", ..., "12/31/10 23:00" }, et que la mesure intégrée "A partir de" a la valeur 1292348109 (représentant une heure à la mi-décembre 14 décembre 2010), alors heures de la journée (Heure, As_Of, "%x 00:0 0", 0, false) contient les éléments { "12/12/10 00:00", "12/12/10 01:00", ..., "12/12/10 23:00" }. </p> </td> 
  </tr> 
 </tbody> 
</table>
