---
description: Data Workbench comprend des dimensions intégrées.
title: Dimensions intégrées
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
exl-id: c08a487d-60b8-4db7-8776-7ae1b9f1f27c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 14%

---

# Dimensions intégrées{#built-in-dimensions}

Data Workbench comprend des dimensions intégrées.

Le tableau suivant répertorie les dimensions intégrées disponibles pour Data Workbench :

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
   <td colname="col4">Dispose d’un seul élément "" qui se rapporte à tous les éléments de toutes les dimensions. L’évaluation d’une mesure sur Aucune revient à l’évaluer sur aucune dimension. <p>Le <span class="filepath"> filtre [Aucun=""]</span> équivaut à <span class="filepath"> [True]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Un (masqué) </td> 
   <td colname="col2"> Numérique </td> 
   <td colname="col3"> S.O. </td> 
   <td colname="col4">L’élément "1", qui a également une valeur ordinale <span class="filepath"> = 1</span>, se rapporte à tous les éléments de toutes les dimensions. La dimension Un est normalement utilisée pour construire des décomptes à l’aide de cette syntaxe : <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>
