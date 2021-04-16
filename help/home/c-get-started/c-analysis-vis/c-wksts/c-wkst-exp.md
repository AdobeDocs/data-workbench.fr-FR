---
description: Informations conceptuelles sur les expressions de la feuille de calcul et l’utilisation des références de cellule.
title: Expressions des feuilles de calcul
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
exl-id: 1ff3ec24-0363-4b6c-8c91-31e49ed0f7c4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 2%

---

# Expressions des feuilles de calcul{#worksheet-expressions}

Informations conceptuelles sur les expressions de la feuille de calcul et l’utilisation des références de cellule.

La feuille de calcul suivante fournit des détails sur les visiteurs qui vue la page Assistant de demande de service financier fournie sur le formulaire de demande de service financier en ligne du site Web d’une banque.

![](assets/client-wkst.png)

* La colonne A présente une liste des catégories des visiteurs évalués : visiteurs, visiteurs référents et visiteurs de l&#39;Parrain A.
* La colonne B indique le nombre de visiteurs dans chaque catégorie qui ont consulté la page Appliquer maintenant.
* La colonne C affiche les visiteurs qui ont consulté les pages Appliquer maintenant et Assistant Application.
* La colonne D contient les pourcentages des visionneuses Appliquer maintenant dans les trois catégories qui ont également consulté la page Assistant Application.

La feuille de calcul montre qu&#39;environ 55 % des visiteurs provenant du Parrain A qui a affiché la page Appliquer maintenant ont également consulté la page Assistant Application.

Le tableau suivant fournit des exemples de formules pour la feuille de calcul de l&#39;exemple précédent :

<table id="table_0F5EFDB58040465AB599E6BE93324822"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cellule de feuille de calcul </th> 
   <th colname="col2" class="entry"> Formule </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>B2 </p> <p>Visiteurs qui ont consulté la page Appliquer maintenant </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Visiteur[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B3 </p> <p>Visiteurs référents qui ont consulté la page Demander ma carte maintenant </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Visiteurs_référencés[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>Visiteurs référencés du Parrain A qui ont consulté la page Demander ma carte maintenant </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visiteurs_référencés[Page="/applynow/default.asp"  </span> </p> <p> ET <span class="filepath"> Parrain="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>Visiteurs qui ont consulté la page Appliquer maintenant et la page Assistant Application </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visiteur[Page="/applynow/default.asp"  </span> </p> <p> ET <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>Visiteurs référents qui ont consulté la page Appliquer maintenant et la page Assistant Application </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visiteurs_référencés[Page="/applynow/default.asp"  </span> </p> <p> ET <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>Visiteurs référencés du Parrain A qui ont consulté la page Appliquer maintenant et la page Assistant Application </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visiteurs_référencés[Page="/applynow/default.asp"</span> </p> <p> ET <span class="filepath"> Page="/applynow/appwizard.asp"</span> </p> <p> ET <span class="filepath"> Parrain="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D2 </p> <p>Pourcentage de Visiteurs qui ont consulté la page Demander ma carte maintenant et la page Assistant d'application </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C2/B2*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D3 </p> <p>Pourcentage de Visiteurs référents qui ont consulté la page Appliquer maintenant et la page Assistant Application </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C3/B3*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D4 </p> <p>Pourcentage de Visiteurs référents du Parrain A qui ont consulté la page Appliquer maintenant et la page Assistant Application </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Comme pour les autres visualisations, les feuilles de calcul sont automatiquement mises à jour lorsque vous effectuez une sélection dans une autre visualisation de l’espace de travail. Pour plus d’informations sur les sélections, voir [Sélections dans Visualisations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

Dans l’exemple de données Web suivant, plusieurs jours de données de session ont été sélectionnés dans la visualisation Sessions par jour. La feuille de calcul montre qu&#39;au cours de la période sélectionnée, environ 69 % des visiteurs du Parrain A qui ont consulté la page Appliquer maintenant ont également consulté la page Assistant Application. Sans cette sélection (comme indiqué dans l&#39;exemple ci-dessus), environ 55 % des visiteurs du Parrain A ont consulté la page Appliquer maintenant ainsi que la page Assistant Application.

![](assets/client-exp.png)

## Utilisation des références de cellule {#section-0004e315c9c94d359b1a8a39794ba555}

Vous pouvez remplacer n’importe quelle chaîne, seule ou dans une autre expression de la feuille de calcul, par une référence de cellule.

* **Référence de cellule simple :** La cellule A2 contient les Visiteurs de texte, qui sont utilisés comme en-tête. La cellule B2 contient [!DNL eval(A1)], qui renvoie [!DNL =Visitors].

* **Référence de cellule de filtre :** la cellule A5 contient la date d’hier. La cellule B5 contient [ ! DNL Visiteurs[ Day=A5 ]], qui évalue le nombre de Visiteurs hier.

* **Référence de cellule concaténée :** la cellule A5 contient la date du jour et la cellule A6 contient la période d’une heure comprise entre 08:00 et 08:59. La cellule B6 contient [ ! DNL Visiteurs[ Heure=A5+&quot;&quot;+A6 ]], qui évalue le nombre de Visiteurs aujourd&#39;hui entre 8 h et 9 h.
