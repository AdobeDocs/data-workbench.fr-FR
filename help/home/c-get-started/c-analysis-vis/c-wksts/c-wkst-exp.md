---
description: Informations conceptuelles sur les expressions de feuille de calcul et l’utilisation des références de cellule.
solution: Analytics
title: Expressions de feuille de calcul
topic: Data workbench
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Expressions de feuille de calcul{#worksheet-expressions}

Informations conceptuelles sur les expressions de feuille de calcul et l’utilisation des références de cellule.

La feuille de calcul suivante fournit des détails sur les visiteurs qui consultent la page Assistant de demande de service financier fournie dans le formulaire de demande de service financier en ligne du site Web d’une banque.

![](assets/client-wkst.png)

* La colonne A affiche la liste des catégories de visiteurs évalués : visiteurs, visiteurs référents et visiteurs référents du référent A.
* La colonne B indique le nombre de visiteurs de chaque catégorie qui ont consulté la page Appliquer maintenant.
* La colonne C indique les visiteurs qui ont consulté les pages Appliquer maintenant et Assistant Application.
* La colonne D contient les pourcentages des visionneuses Demander maintenant dans les trois catégories qui ont également consulté la page Assistant Application.

La feuille de calcul montre qu’environ 55 % des visiteurs provenant du référent A qui ont consulté la page Appliquer maintenant ont également consulté la page Assistant Application.

Le tableau suivant fournit des exemples de formules pour la feuille de calcul dans l’exemple précédent :

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
   <td colname="col2"> <p><span class="filepath"> =Visiteurs[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B3 </p> <p>Visiteurs référents qui ont consulté la page Demander maintenant </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Visiteurs_Référés[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>Visiteurs référents du référent A qui a consulté la page Appliquer maintenant </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visiteurs_Référés[Page="/applynow/default.asp" </span> </p> <p> ET <span class="filepath"> Référent="Réf A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>Visiteurs qui ont consulté la page Appliquer maintenant et la page Assistant Application </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visiteurs[Page="/applynow/default.asp" </span> </p> <p> ET <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>Visiteurs référents qui ont consulté la page Demander maintenant et la page Assistant Application </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visiteurs_Référés[Page="/applynow/default.asp" </span> </p> <p> ET <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>Visiteurs référents du référent A qui ont consulté la page Appliquer maintenant et la page Assistant d’application </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visiteurs_Référés[Page="/applynow/default.asp"</span> </p> <p> ET <span class="filepath"> Page="/applynow/appwizard.asp"</span> </p> <p> ET <span class="filepath"> Référent="Réf A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D2 </p> <p>Pourcentage de visiteurs qui ont consulté la page Appliquer maintenant et la page Assistant d’application </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C2/B2*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D3 </p> <p>Pourcentage de visiteurs référents qui ont consulté la page Demander maintenant et la page Assistant d’application </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C3/B3*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D4 </p> <p>Pourcentage de visiteurs provenant du référent A qui ont consulté la page Demander maintenant et la page Assistant d’application </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Comme pour les autres visualisations, les feuilles de calcul sont automatiquement mises à jour lorsque vous effectuez une sélection dans une autre visualisation de l’espace de travail. Pour plus d’informations sur les sélections, voir [Création de sélections dans les visualisations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

Dans l’exemple de données Web suivant, plusieurs jours de données de session ont été sélectionnés dans la visualisation Sessions par jour. La feuille de calcul montre que pendant la période sélectionnée, environ 69 % des visiteurs du Référent A qui ont consulté la page Demander maintenant ont également consulté la page Assistant Application. Sans cette sélection (comme illustré dans l’exemple ci-dessus), environ 55 % des visiteurs du Référent A ont consulté la page Demander maintenant ainsi que la page Assistant d’application.

![](assets/client-exp.png)

## Utilisation des références de cellule {#section-0004e315c9c94d359b1a8a39794ba555}

Vous pouvez remplacer n’importe quelle chaîne, seule ou dans une autre expression de la feuille de calcul, par une référence de cellule.

* **Référence de cellule simple :** La cellule A2 contient le texte Visiteurs, qui est utilisé comme en-tête. La cellule B2 contient [!DNL eval(A1)], ce qui est évalué [!DNL =Visitors].

* **Référence de la cellule de filtre :** La cellule A5 contient la date d’hier. La cellule B5 contient [!DNL Visitors[ Day=A5 ]], qui évalue le nombre de visiteurs hier.

* **Référence de cellule concaténée :** La cellule A5 contient la date d’aujourd’hui et la cellule A6 contient la période d’une heure comprise entre 8 h et 8 h 59. La cellule B6 contient [!DNL Visitors[ Hour=A5+” ”+A6 ]], qui évalue le nombre de visiteurs aujourd’hui entre 8:00 et 9:00.

