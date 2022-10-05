---
description: Informations conceptuelles sur les expressions de feuille de calcul et l’utilisation des références de cellule.
title: Expressions des feuilles de calcul
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
exl-id: 1ff3ec24-0363-4b6c-8c91-31e49ed0f7c4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 2%

---

# Expressions des feuilles de calcul{#worksheet-expressions}

{{eol}}

Informations conceptuelles sur les expressions de feuille de calcul et l’utilisation des références de cellule.

La feuille de calcul suivante fournit des détails sur les visiteurs qui consultent la page Assistant de demande fournie dans le formulaire de demande en ligne du site web d’une banque.

![](assets/client-wkst.png)

* La colonne A affiche la liste des catégories de visiteurs évalués : visiteurs, visiteurs référents et visiteurs référents provenant du référent A.
* La colonne B indique le nombre de visiteurs de chaque catégorie qui ont consulté la page Demander maintenant .
* La colonne C indique les visiteurs qui ont consulté les pages Appliquer maintenant et Assistant de l’application.
* La colonne D contient les pourcentages des visionneuses Demander maintenant dans les trois catégories qui ont également consulté la page Assistant de l’application.

La feuille de calcul indique qu’environ 55 % des visiteurs provenant du référent A qui a consulté la page Demander maintenant ont également consulté la page Assistant de l’application.

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
   <td colname="col1"> <p>B2 </p> <p>Visiteurs ayant consulté la page Demander maintenant </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Visiteurs[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B3 </p> <p>Visiteurs référents ayant consulté la page Demander maintenant </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>Visiteurs référents du référent A qui a consulté la page Demander maintenant . </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp" </span> </p> <p> ET <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>Visiteurs ayant consulté la page Demander maintenant et la page Assistant de l’application </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visiteurs[Page="/applynow/default.asp" </span> </p> <p> ET <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>Visiteurs référents qui ont consulté la page Demander maintenant et la page Assistant de l’application </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp" </span> </p> <p> ET <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>Visiteurs référents du référent A qui ont consulté la page Demander maintenant et la page Assistant de l’application </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"</span> </p> <p> ET <span class="filepath"> Page="/applynow/appwizard.asp"</span> </p> <p> ET <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D2 </p> <p>Pourcentage de visiteurs ayant consulté la page Demander maintenant et la page Assistant de l’application </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C2/B2*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D3 </p> <p>Pourcentage de visiteurs référents ayant consulté la page Demander maintenant et la page Assistant de l’application </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C3/B3*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D4 </p> <p>Pourcentage de visiteurs référents du référent A ayant consulté la page Demander maintenant et la page Assistant de l’application </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Comme pour les autres visualisations, les feuilles de calcul sont automatiquement mises à jour lorsque vous effectuez une sélection dans une autre visualisation de l’espace de travail. Pour plus d’informations sur la réalisation de sélections, voir [Réalisation de sélections dans les visualisations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

Dans l’exemple de données web suivant, plusieurs jours de données de session ont été sélectionnés dans la visualisation Sessions par jour . La feuille de calcul indique qu’au cours de la période sélectionnée, environ 69 % des visiteurs du référent A qui ont consulté la page Demander maintenant ont également consulté la page Assistant de l’application. Sans cette sélection (comme illustré dans l’exemple ci-dessus), environ 55 % des visiteurs du référent A ont consulté la page Demander maintenant ainsi que la page Assistant de l’application.

![](assets/client-exp.png)

## Utilisation de références de cellule {#section-0004e315c9c94d359b1a8a39794ba555}

Vous pouvez remplacer n’importe quelle chaîne, seule ou dans une autre expression de la feuille de calcul, par une référence de cellule.

* **Référence de cellule simple :** La cellule A2 contient le texte Visiteurs, qui est utilisé comme en-tête. La cellule B2 contient [!DNL eval(A1)], qui évalue à [!DNL =Visitors].

* **Référence de cellule de filtre :** La cellule A5 contient la date d’hier. La cellule B5 contient [!DNL Visitors[ Day=A5 ]], qui évalue le nombre de visiteurs hier.

* **Référence de cellule concaténée :** La cellule A5 contient la date d’aujourd’hui et la cellule A6 contient la période d’une heure comprise entre 8 h 00 et 8 h 59. La cellule B6 contient [!DNL Visitors[ Hour=A5+” ”+A6 ]], qui évalue le nombre de visiteurs aujourd’hui entre 8 h et 9 h.
