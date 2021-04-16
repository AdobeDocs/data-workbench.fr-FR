---
description: Le profil de trafic contient les mesures suivantes pour identifier le trafic des visiteurs.
title: Mesures de profil de trafic
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
exl-id: 38f191e5-5b30-4fe0-a680-bcb33fe52eca
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 2%

---

# Mesures de profil de trafic{#traffic-profile-metrics}

Le profil de trafic contient les mesures suivantes pour identifier le trafic des visiteurs.

<table id="table_D981FB9F8B734E3C845A9628548565F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mesure </th> 
   <th colname="col2" class="entry"> Formule et niveau de mesure </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Entrées </td> 
   <td colname="col2">Formule : <span class="filepath"> Page_Vues[no shift(None,Page_Vue, Session,-1)]</span><p>Niveau : Vue de page </p></td> 
   <td colname="col3"> Nombre de sessions qui sont entrées sur le site sur chaque page. Cette mesure est évaluée uniquement sur la dimension Page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Taux de sortie </td> 
   <td colname="col2">Formule : <span class="filepath"> Sorties/Page_Vues </span><p>Niveau : Vue de page </p></td> 
   <td colname="col3"> Pourcentage de sessions qui ont quitté le site à partir de chaque page. La mesure Taux de sortie ne peut être évaluée que sur la dimension de page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sorties </td> 
   <td colname="col2">Formule : <span class="filepath"> Vues_page[pas de décalage (Aucun, Vue_page, Session,1)] </span><p>Niveau : Vue de page </p></td> 
   <td colname="col3"> Nombre de sessions qui ont quitté le site à partir de chaque page. Cette mesure est évaluée uniquement sur la dimension Page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">Formule : <span class="filepath"> (raw(Visiteur) - ((raw(Visiteur) + 0,69)^0,5 * 1.281551 - 1.2269))*(Visiteur/raw(Visiteur))</span><p>Niveau : Visiteur </p></td> 
   <td colname="col3"> Mesure du nombre le plus faible de visiteurs possibles, tel que rapporté par Insight. Mathématiquement, il spécifie le nombre le plus faible de visiteurs avec une probabilité de 90 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée de la Vue de page </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> somme (durée_de_page exacte, vue_de_page)*0.1/Vues_de_page[toute durée_de_page_exacte]</span></p> <p>Niveau : Vue de page </p> </td> 
   <td colname="col3"> Durée moyenne (MM:SS) passée sur une page ou un groupe de pages particulier. Cette mesure est évaluée uniquement sur la dimension Page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vues de page par session </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Page_Vues/ (Sessions par Page_Vue) </span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Nombre moyen de vues de page dans chaque session qui comporte des vues de page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pages vues </td> 
   <td colname="col2">Formule : <span class="filepath"> sum(One, Page_Vue)</span><p>Niveau : Vue de page </p></td> 
   <td colname="col3"> Nombre de vues de page. Une vue de page est une requête pour une page définie (l’accès aux images et aux autres types de contenu filtré n’est pas comptabilisé). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct de Vues de page </td> 
   <td colname="col2">Formule : <span class="filepath"> Page_Vues/total(Page_Vues) </span><p>Niveau : Vue de page </p></td> 
   <td colname="col3"> Pourcentage de vues de page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct des sessions </td> 
   <td colname="col2">Formule : <span class="filepath"> Sessions/total(Sessions)</span><p>Niveau : Session </p></td> 
   <td colname="col3"> Pourcentage de sessions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct de Visiteur </td> 
   <td colname="col2">Formule : <span class="filepath"> Visiteurs/total(Visiteur) </span><p>Niveau : Visiteur </p></td> 
   <td colname="col3"> Pourcentage de visiteurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs référencés Pct </td> 
   <td colname="col2"> <p>Formule : Visiteurs/Visiteurs_référents </p> <p>Niveau : Visiteur </p> </td> 
   <td colname="col3"> Pourcentage de visiteurs qui ont été redirigés vers ce site à partir d’un autre site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessions référencées </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Sessions[Parrain&lt;&gt; 'Aucun' et Parrain&lt;&gt;'signets']</span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Nombre de sessions renvoyées à ce site à partir d’un autre site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs référencés </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Visiteur[Visiteur_Parrain&lt;&gt;'None' et Visiteur_Parrain&lt;&gt;'book marks']</span></p> <p>Niveau : Visiteur </p> </td> 
   <td colname="col3"> Nombre de visiteurs qui ont été dirigés vers ce site à partir d’un autre site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rétention </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Sessions[shift(None, Ses sion, Visiteur,1 = ""] / Sessions</span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Pourcentage de sessions qui ne sont pas les dernières sessions visiteuses. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée de la session </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> (somme (Durée_Page_Exact, Session)*.1/Sessions)[Durée_Session &lt;= '01:00:00']</span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3">Durée moyenne (MM:SS) qu’un visiteur passe dans une session. <p><p>Remarque : Vous pouvez utiliser cette mesure avec la fonction <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> Exportation de segment</a>. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessions par Vue de page </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Sessions par Vue de page</span></p> <p> Niveau : Session </p> </td> 
   <td colname="col3"> Nombre de sessions comportant une vue de page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessions </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> sum(One, Session)</span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Nombre de sessions de visiteur. Une session est une période d’activité pour un visiteur d’un site Web. Les sessions individuelles de chaque visiteur sont identifiées à l'aide de cookies, de dépassements de délai et d'autres méthodes heuristiques. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> fiabilité(sessions) * 1.281551 / Sessions</span></p> <p>Niveau : Visiteur </p> </td> 
   <td colname="col3"> Mesure de la confiance de la mesure Sessions telle que rapportée par les outils de données. Mathématiquement, il s'agit d'un pourcentage +/- qui spécifie la plage dans laquelle la réponse réelle sera 80 % du temps. En règle générale, le fait de doubler le pourcentage de SIC80 donnera une fourchette dans laquelle la réponse réelle sera de 99 % du temps. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> ((raw(Visiteur) + .68)^0.5 * 1.281551 + 1.2269) + raw(Visiteur))*( Visiteur/raw(Visiteur))</span></p> <p>Niveau : Visiteur </p> </td> 
   <td colname="col3"> Mesure présentant le plus grand nombre de visiteurs possibles, comme indiqué par Insight. Mathématiquement, il spécifie le plus grand nombre de visiteurs avec une probabilité de 90 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">Formule : <span class="filepath"> ((raw(Visiteur) + .68)^0.5 * 1.281551 + 1.2269) / raw(Visiteur)</span><p>Niveau : Visiteur </p></td> 
   <td colname="col3"> Mesure de la confiance de la mesure Visiteuse telle que rapportée par Insight. Mathématiquement, il s'agit d'un pourcentage +/- qui spécifie la plage dans laquelle la réponse réelle sera 80 % du temps. En règle générale, le doublement du pourcentage VCI80 donnera une plage dans laquelle la réponse réelle sera comprise 99 % du temps. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs par Vue de page </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Visiteurs par Vue_de_page</span></p> <p>Niveau : Vue de page </p> </td> 
   <td colname="col3"> Nombre de visiteurs ayant une vue de page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs par session </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Visiteurs par session </span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Nombre de visiteurs qui ont eu une session. </td> 
  </tr> 
 </tbody> 
</table>
