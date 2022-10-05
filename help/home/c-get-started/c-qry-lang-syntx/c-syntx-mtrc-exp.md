---
description: Les mesures peuvent être modifiées à l’aide de l’éditeur de mesures et enregistrées dans le répertoire Mesures d’un profil.
title: Syntaxe des expressions de mesure
uuid: 801e265d-d7e4-4f0f-9698-d0b50dd00995
exl-id: 27d86fea-6500-4608-aadb-f39058fd3a6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---

# Syntaxe des expressions de mesure{#syntax-for-metric-expressions}

{{eol}}

Les mesures peuvent être modifiées à l’aide de l’éditeur de mesures et enregistrées dans le répertoire Mesures d’un profil.

Pour plus d’informations, voir [Création et modification de mesures dérivées](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40). Les expressions de mesure peuvent également être utilisées dans des feuilles de calcul. Pour plus d’informations, voir [Feuilles de calcul](../../../home/c-get-started/c-analysis-vis/c-wksts/c-wksts.md#concept-45b50aafc4d84709841f14aee8022581). La syntaxe suivante est utilisée pour définir des expressions de mesure.

Remarques :

1. Les mots soulignés doivent être littéralement saisis dans le texte de l’expression.
1. Le formulaire `{TEXT}?` représente le texte facultatif.
1. Le formulaire `{TEXT}*` représente le texte qui peut se produire zéro ou plusieurs fois.
1. Le formulaire `{A | B | C |...}` représente le texte qui comprend exactement l’une des options données, comme A, B ou C....
1. Le formulaire `[A,B)` représente une plage de nombres, de A à B, mais pas.

<table id="table_A6CA9C9F396448209398AA2A369E63FA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identifiant </p> </td> 
   <td colname="col2"> <p>Un identifiant fait référence à une mesure nommée. Pour connaître les règles régissant les identifiants légaux, voir <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Syntaxe des identificateurs </a>. </p> <p>Exemple : Recettes = Total_Price </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Mesure) </p> </td> 
   <td colname="col2"> <p>Le résultat de (Mesure) est le même que celui de la Mesure. Les parenthèses spécifient l’ordre des opérations dans une expression. </p> <p>Exemple : Moyenne = (A + B) / 2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A + B </p> </td> 
   <td colname="col2"> <p>Somme des résultats des mesures A et B. </p> <p>Exemple : Valeur = Recettes + Coût_Savages </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A - B </p> </td> 
   <td colname="col2"> <p>Différence entre les résultats de la mesure A et de la mesure B. </p> <p>Exemple : Profit = Recettes - Coût </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A * B </p> </td> 
   <td colname="col2"> <p>Produit des résultats de la mesure A et de la mesure B. </p> <p>Exemple : Dollars = Cents * 0,01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A / B </p> </td> 
   <td colname="col2"> <p>Ratio des résultats des mesures A et B. </p> <p>Exemple : Revenue_per_Session = Recettes / Sessions </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Un ^ B </p> </td> 
   <td colname="col2"> <p>Résultat de la mesure A élevé à la puissance du résultat de la mesure B. </p> <p>Exemple : Zone = Largeur^2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trust(metric) </p> </td> 
   <td colname="col2"> <p>Une estimation de l’écart type de la mesure. Cette méthode est calculée à l’aide d’une technique d’échantillonnage appelée "jackwing". </p> <p>Cette mesure consomme beaucoup de mémoire et ne doit pas être utilisée dans les tables volumineuses. </p> <p>Pour utiliser cette syntaxe, vous devez disposer d’une dimension "jackknife" (appelée "jackknife") avec les propriétés appropriées. Pour plus d’informations, contactez les Services de conseil Adobe. </p> <p>Exemple : trust(Average_Score) </p> <p> <p>Remarque : Les types de mesures de confiance, y compris le degré de confiance (mesure) et le degré de confiance (mesure, jacknife), sont particulièrement utiles lors de l’utilisation de la fonctionnalité d’expérimentation contrôlée d’Adobe. Si une mesure est passée de 12 % à 16 % au cours d’une expérience contrôlée, vous pouvez utiliser une légende de confiance pour calculer les probabilités que le saut soit dû à une variation aléatoire. Cela peut vous aider à éviter de tirer de mauvaises conclusions à partir de preuves limitées, et, inversement, fournir l'assurance qu'un changement discutable est réellement réel. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>fiabilité (mesure, couteau à main) </p> </td> 
   <td colname="col2"> <p>Une estimation de l’écart type de la mesure. Cette méthode est calculée à l’aide d’une technique d’échantillonnage appelée "jackwing". Cette syntaxe vous permet de déterminer le degré de confiance d’une mesure à l’aide d’une dimension "jackknife" nommée autre chose que "jackknife". </p> <p>Cette mesure consomme beaucoup de mémoire et ne doit pas être utilisée dans les tables volumineuses. </p> <p>Pour utiliser cette syntaxe, vous devez disposer d’une dimension de couteau de chasse (nommée autre que "couteau de chasse") avec les propriétés appropriées. Pour plus d’informations, contactez les Services de conseil Adobe. </p> <p>Exemple : trust(Average_Score,SubSamples) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eval(CellReference) </p> </td> 
   <td colname="col2"> <p>Traite le contenu de la cellule que vous référencez comme une expression de mesure. Cette syntaxe ne peut être utilisée que dans une visualisation de feuille de calcul. </p> <p>Exemple : eval(B1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>log (B, X) </p> </td> 
   <td colname="col2"> <p>La fonction logarithme mathématique : La mesure X est le paramètre et la mesure B est la base. </p> <p>Exemple : dB = 20*log(Amplitude,10) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mesure[Filtre] </p> </td> 
   <td colname="col2"> <p>"Mesure où filtrer" : Une nouvelle mesure filtrée selon le filtre donné. </p> <p>Exemple : Jan_Sessions = Sessions[ Month="Jan" ] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mesure par Dimension </p> </td> 
   <td colname="col2"> <p>Mesure évaluée au "niveau" de la dimension. Le résultat de (M par X)[F] (le résultat de la mesure "M par X" évaluée avec le filtre "F") est le résultat de M[F par X] (le résultat de la mesure "M" évaluée avec le filtre "F par X"). </p> <p>Exemple : AB_Visitors = </p> <p>(Visiteurs par session)[Page="A" et Page="B"] = </p> <p>Visiteurs[(Page="A" et Page="B") par Session] = </p> <p>Nombre de visiteurs qui ont consulté les pages A et B au cours de la même session. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nombre </p> </td> 
   <td colname="col2"> <p>Mesure avec une valeur fixe. </p> <p>Exemple : Pi = 3,1415 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(Mesure) </p> </td> 
   <td colname="col2"> <p>Ignore toute dimension sur laquelle la mesure est évaluée. La mesure a la même valeur pour chaque élément de cette dimension. </p> <p>Exemple : Pct_of_Visitors = Visitors / total(Visitors) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>all(Metric) </p> </td> 
   <td colname="col2"> <p>Ignore les filtres qui s’appliquent à la mesure. Les mesures ne sont pas affectées par les sélections et d’autres filtres. </p> <p>Exemple : Benchmark_Sessions = all( sessions ) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(all(Metric) </p> </td> 
   <td colname="col2"> <p>Ignore tous les filtres et dimensions. Elle a la même valeur dans un profil donné, quels que soient les filtres ou les dimensions appliqués. </p> <p>Exemple : Jeu de données_Visitors = total(all(Visitors) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(One,Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>Mesure qui donne le nombre d’une dimension dénombrable telle que Visiteur ou Session. </p> <p>Exemple : Visiteurs = sum(One,Visitor) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(Numeric_Dimension, Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>Mesure qui donne la somme d’une dimension numérique sur une dimension dénombrable. Les valeurs ordinales (par opposition aux valeurs formatées) des éléments de la dimension numérique sont utilisées, donc un facteur d’échelle doit souvent être appliqué au résultat. </p> <p>Exemple : Valeur = sum(Session_Value, Session)*0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>min(A, B) </p> </td> 
   <td colname="col2"> <p>Résultats inférieurs des mesures A et B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>max(A, B) </p> </td> 
   <td colname="col2"> <p>Le plus grand nombre de résultats des mesures A et B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>format(A, B) </p> </td> 
   <td colname="col2"> <p>Mesure identique à la mesure A, sauf qu’elle utilise la fonction de formatage de la mesure B. </p> </td> 
  </tr> 
 </tbody> 
</table>
