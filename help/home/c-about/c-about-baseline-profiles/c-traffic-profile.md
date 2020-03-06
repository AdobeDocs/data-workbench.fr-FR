---
description: Le profil Trafic contient les mesures suivantes pour identifier le trafic des visiteurs.
solution: Analytics
title: Mesures de profil de trafic
topic: Data workbench
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Mesures de profil de trafic{#traffic-profile-metrics}

Le profil Trafic contient les mesures suivantes pour identifier le trafic des visiteurs.

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
   <td colname="col2">Formule : <span class="filepath"> Page_Views[no shift(None,Page_View, Session,-1)]</span><p>Niveau : Page vue </p></td> 
   <td colname="col3"> Nombre de sessions qui sont entrées sur le site sur chaque page. Cette mesure est évaluée uniquement sur la dimension Page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Taux de sortie </td> 
   <td colname="col2">Formule : <span class="filepath"> Sorties/Pages_Vues </span><p>Niveau : Page vue </p></td> 
   <td colname="col3"> Pourcentage de sessions qui ont quitté le site à partir de chaque page. La mesure Taux de sortie ne peut être évaluée que sur la dimension de page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sorties </td> 
   <td colname="col2">Formule :<span class="filepath"> Page_Views[no shift(None,Page_View, Session,1)] </span><p>Niveau : Page vue </p></td> 
   <td colname="col3"> Nombre de sessions qui ont quitté le site à partir de chaque page. Cette mesure est évaluée uniquement sur la dimension Page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">Formule : <span class="filepath"> (raw(Visitors) - (raw(Visitors) + .69)^0.5 * 1.281551 - 1.2269))*(Visitors/raw(Visitors))</span><p>Niveau : Visiteur </p></td> 
   <td colname="col3"> Mesure du nombre de visiteurs le plus faible possible tel que rapporté par Insight. Mathématiquement, il indique le nombre le plus faible de visiteurs avec une probabilité de 90 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée des pages vues </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> somme (durée_de_la_page, page_vue)*0.1/Pages_Views[durée_de_la_page exacte]</span></p> <p>Niveau : Page vue </p> </td> 
   <td colname="col3"> Durée moyenne (MM:SS) passée sur une page ou un groupe de pages spécifique. Cette mesure est évaluée uniquement sur la dimension Page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pages vues par session </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Page_Views/ (Sessions par Page_View) </span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Nombre moyen de pages vues dans chaque session avec des pages vues. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pages vues </td> 
   <td colname="col2">Formule : <span class="filepath"> (Un, Page_View)</span><p>Niveau : Page vue </p></td> 
   <td colname="col3"> Nombre de pages vues. Une page vue est une requête pour une page définie (l’accès aux images et aux autres types de contenu filtré n’est pas comptabilisé). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct de pages vues </td> 
   <td colname="col2">Formule : <span class="filepath"> Page_Views/total(Page_Views) </span><p>Niveau : Page vue </p></td> 
   <td colname="col3"> Pourcentage de pages vues. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct de sessions </td> 
   <td colname="col2">Formule : <span class="filepath"> Sessions/total(Sessions)</span><p>Niveau : Session </p></td> 
   <td colname="col3"> Pourcentage de sessions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct des visiteurs </td> 
   <td colname="col2">Formule : <span class="filepath"> Visiteurs/total(Visiteurs) </span><p>Niveau : Visiteur </p></td> 
   <td colname="col3"> Pourcentage de visiteurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs Référents Pct </td> 
   <td colname="col2"> <p>Formule : Referred_Visitors/Visitors </p> <p>Niveau : Visiteur </p> </td> 
   <td colname="col3"> Pourcentage de visiteurs qui ont été dirigés vers ce site à partir d’un autre site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessions référencées </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Sessions[Référent&lt;&gt; 'Aucun' et Référent&lt;&gt;'signets']</span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Nombre de sessions renvoyées vers ce site à partir d’un autre site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs référents </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Visiteurs[Visitor_Referrer&lt;&gt;'None' et Visitor_Referrer&lt;&gt;'marks']</span></p> <p>Niveau : Visiteur </p> </td> 
   <td colname="col3"> Nombre de visiteurs qui ont été dirigés vers ce site à partir d’un autre site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rétention </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Sessions[shift(None,Ses sion,Visiteur,1) = ""] / Sessions</span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Pourcentage de sessions qui ne sont pas les dernières sessions des visiteurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée de la session </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> (somme (Durée_Page_Exact, Session)*.1/Sessions)[Durée_Session &lt;= '01:00:00']</span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3">Durée moyenne (MM:SS) passée par un visiteur dans une session. <p><p>Remarque : Vous pouvez utiliser cette mesure avec la fonction d’exportation <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"></a> de segment. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessions par page vue </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Sessions par Page_View</span></p> <p> Niveau : Session </p> </td> 
   <td colname="col3"> Nombre de sessions ayant une page vue. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessions </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> (Un, Session)</span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Nombre de sessions de visiteurs. Une session est une période d’activité pour un visiteur d’un site Web. Les sessions individuelles de chaque visiteur sont identifiées à l’aide de cookies, d’expirations de délai et d’autres méthodes heuristiques. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> (Sessions) * 1.281551 / Sessions</span></p> <p>Niveau : Visiteur </p> </td> 
   <td colname="col3"> Mesure de la confiance de la mesure Sessions telle qu’elle est signalée par les outils de données. Mathématiquement, il s’agit d’un pourcentage +/- spécifiant la plage au sein de laquelle la réponse réelle se trouve 80 % du temps. En règle générale, le fait de doubler le pourcentage de la SCI80 donnera une fourchette dans laquelle la réponse réelle sera de 99 % du temps. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> ((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) + raw(Visitors))*( Visitors/raw(Visitors)))</span></p> <p>Niveau : Visiteur </p> </td> 
   <td colname="col3"> Mesure du nombre de visiteurs le plus élevé possible tel que rapporté par Insight. Mathématiquement, il indique le nombre le plus élevé de visiteurs avec une probabilité de 90 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">Formule : <span class="filepath"> (raw(Visiteurs) + 0,68)^0,5 * 1.281551 + 1.2269) / raw(Visiteurs)</span><p>Niveau : Visiteur </p></td> 
   <td colname="col3"> Mesure de la confiance de la mesure Visiteurs telle qu’elle est signalée par Insight. Mathématiquement, il s’agit d’un pourcentage +/- spécifiant la plage au sein de laquelle la réponse réelle se trouve 80 % du temps. En règle générale, le fait de doubler le pourcentage de VCI80 donne une plage dans laquelle la réponse réelle sera de 99 % du temps. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs par page vue </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Visiteurs par page_View</span></p> <p>Niveau : Page vue </p> </td> 
   <td colname="col3"> Nombre de visiteurs ayant une page vue. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs par session </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Visiteurs par session </span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Nombre de visiteurs ayant eu une session. </td> 
  </tr> 
 </tbody> 
</table>

