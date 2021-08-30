---
description: Le profil Trafic contient les mesures suivantes pour identifier le trafic des visiteurs.
title: Mesures de profil de trafic
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
exl-id: 38f191e5-5b30-4fe0-a680-bcb33fe52eca
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 2%

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
   <td colname="col2">Formule : <span class="filepath"> Pages_Views[no shift(None,Page_View, Session,-1)]</span><p>Niveau : Page vue </p></td> 
   <td colname="col3"> Nombre de sessions qui ont accédé au site sur chaque page. Cette mesure est évaluée uniquement sur la dimension Page . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Taux de sortie </td> 
   <td colname="col2">Formule : <span class="filepath"> Sorties/Pages_Vues </span><p>Niveau : Page vue </p></td> 
   <td colname="col3"> Pourcentage de sessions qui ont quitté le site à partir de chaque page. La mesure Taux de sortie ne peut être évaluée que sur la dimension de page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sorties </td> 
   <td colname="col2">Formule :<span class="filepath"> Pages_Views[no shift(Aucun,Page_View, Session,1)] </span><p>Niveau : Page vue </p></td> 
   <td colname="col3"> Nombre de sessions qui ont quitté le site à partir de chaque page. Cette mesure est évaluée uniquement sur la dimension Page . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">Formule : <span class="filepath"> (raw(Visitors) - ((raw(Visitors) + .69)^0.5 * 1.281551 - 1.2269)*(Visitors/raw(Visitors)))</span><p>Niveau : Visiteur </p></td> 
   <td colname="col3"> Mesure du nombre de visiteurs le plus faible possible, comme indiqué par Insight. Mathématiquement, il indique le nombre le plus faible de visiteurs avec une probabilité de 90 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée de page vue </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> somme (exact_page_duration, page_view)*0.1/Page_Views[any Exact_Page_Duration]</span></p> <p>Niveau : Page vue </p> </td> 
   <td colname="col3"> Durée moyenne (MM:SS) passée sur une page ou un groupe de pages spécifique. Cette mesure est évaluée uniquement sur la dimension Page . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pages vues par session </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Pages_Views/ (Sessions par page_View) </span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Nombre moyen de pages vues dans chaque session qui comporte des pages vues. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pages vues </td> 
   <td colname="col2">Formule : <span class="filepath"> sum(One, Page_View)</span><p>Niveau : Page vue </p></td> 
   <td colname="col3"> Nombre de pages vues. Une page vue est une requête pour une page définie (l’accès aux images et à d’autres types de contenu filtré ne sont pas comptabilisés). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre de pages vues </td> 
   <td colname="col2">Formule : <span class="filepath"> Pages_Views/total(Pages_Views) </span><p>Niveau : Page vue </p></td> 
   <td colname="col3"> Pourcentage de pages vues. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct de sessions </td> 
   <td colname="col2">Formule : <span class="filepath"> Sessions/total(sessions)</span><p>Niveau : Session </p></td> 
   <td colname="col3"> Pourcentage de sessions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre de visiteurs </td> 
   <td colname="col2">Formule : <span class="filepath"> Visiteurs/total(Visiteurs) </span><p>Niveau : Visiteur </p></td> 
   <td colname="col3"> Pourcentage de visiteurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct Visiteurs Référents </td> 
   <td colname="col2"> <p>Formule : Referred_Visitors/Visitors </p> <p>Niveau : Visiteur </p> </td> 
   <td colname="col3"> Pourcentage des visiteurs qui ont été renvoyés vers ce site à partir d’un autre site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessions référencées </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Sessions[Référent&lt;&gt; 'Aucun' et Référent&lt;&gt;'bookmarks']</span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Nombre de sessions qui ont été renvoyées à ce site à partir d’un autre site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs référents </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Visitors[Visitor_Referrer&lt;&gt;'None' and Visitor_Referrer&lt;&gt;'book marks']</span></p> <p>Niveau : Visiteur </p> </td> 
   <td colname="col3"> Nombre de visiteurs qui ont été renvoyés vers ce site à partir d’un autre site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rétention </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Sessions[shift(None,Ses,Visiteur,1) = ""] / Sessions</span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Pourcentage de sessions qui ne sont pas les dernières sessions des visiteurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée de la session </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> (sum (Exact_Page_Duration, Session)*.1/Sessions)[Session_Duration &lt;= '01:00:00']</span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3">Durée moyenne (MM:SS) passée par un visiteur au cours d’une session. <p><p>Remarque : Vous pouvez utiliser cette mesure avec la fonction <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> Exportation de segments</a> . </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessions par page vue </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Sessions par Page_View</span></p> <p> Niveau : Session </p> </td> 
   <td colname="col3"> Le nombre de sessions qui avaient une page vue. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessions </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> sum(One, Session)</span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Nombre de sessions de visiteurs. Une session est une période d’activité pour un visiteur d’un site web. Les sessions individuelles de chaque visiteur sont identifiées à l’aide de cookies, d’expirations de délai et d’autres heuristiques. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> trust(Sessions) * 1.281551 / Sessions</span></p> <p>Niveau : Visiteur </p> </td> 
   <td colname="col3"> Mesure de confiance de la mesure Sessions telle qu’elle est consignée par Data Workbench. Mathématiquement, il s’agit d’un pourcentage +/- spécifiant la plage dans laquelle la réponse réelle sera 80 % du temps. En règle générale, doubler le pourcentage de la SCI80 donnera une fourchette dans laquelle la réponse sera 99 % du temps. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> ((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) + raw(Visitors)*( Visitors/raw(Visitors)))</span></p> <p>Niveau : Visiteur </p> </td> 
   <td colname="col3"> Mesure du nombre maximum de visiteurs possible comme indiqué par Insight. Mathématiquement, il indique le nombre le plus élevé de visiteurs avec une probabilité de 90 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">Formule : <span class="filepath"> ((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) / raw(Visitors)</span><p>Niveau : Visiteur </p></td> 
   <td colname="col3"> Mesure de confiance de la mesure Visiteurs comme indiqué par Insight. Mathématiquement, il s’agit d’un pourcentage +/- spécifiant la plage dans laquelle la réponse réelle sera 80 % du temps. En règle générale, le doublement du pourcentage VCI80 donnera une plage dans laquelle la réponse réelle se situera 99 % du temps. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs par page vue </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Visiteurs par Page_View</span></p> <p>Niveau : Page vue </p> </td> 
   <td colname="col3"> Nombre de visiteurs qui ont eu une page vue. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs par session </td> 
   <td colname="col2"> <p>Formule : <span class="filepath"> Visiteurs par session </span></p> <p>Niveau : Session </p> </td> 
   <td colname="col3"> Nombre de visiteurs qui ont eu une session. </td> 
  </tr> 
 </tbody> 
</table>
