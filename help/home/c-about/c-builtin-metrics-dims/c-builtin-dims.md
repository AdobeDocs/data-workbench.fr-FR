---
description: Les outils de données comprennent des dimensions intégrées.
solution: Analytics
title: Dimensions intégrées
topic: Data workbench
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensions intégrées{#built-in-dimensions}

Les outils de données comprennent des dimensions intégrées.

Le tableau suivant répertorie les dimensions intégrées disponibles pour les outils de données :

<table id="table_40796088B3484F98889859C59D525AD7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom </th> 
   <th colname="col2" class="entry"> Détails </th> 
   <th colname="col3" class="entry"> Niveau </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Aucun </td> 
   <td colname="col2"> Dérivé </td> 
   <td colname="col3"> S.O. </td> 
   <td colname="col4">Comporte un seul élément "" qui se rapporte à tous les éléments de toutes les dimensions. Évaluer une mesure sur Aucune revient à l’évaluer sur aucune dimension. <p>Le <span class="filepath"> filtre [None=""]</span> est équivalent à <span class="filepath"> [True]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Un (Masqué) </td> 
   <td colname="col2"> Numérique </td> 
   <td colname="col3"> S.O. </td> 
   <td colname="col4">L’élément "1", qui a également une valeur ordinale <span class="filepath"> = 1</span>, se rapporte à tous les éléments de toutes les dimensions. La dimension Un est normalement utilisée pour construire des comptes à l’aide de la syntaxe suivante : <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>

