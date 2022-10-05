---
description: La Légende de traitement fournit des informations détaillées sur le traitement et la transformation des données d’un serveur particulier, ce qui vous permet de suivre la progression des données en cours de retraitement et de transformation.
title: Légende de traitement
uuid: 6c082c8f-fbb3-4e48-a249-2a13345fda86
exl-id: a83ce514-c92b-4cf8-a3cc-bff4e2ba63f1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---

# Légende de traitement{#processing-legend}

{{eol}}

La Légende de traitement fournit des informations détaillées sur le traitement et la transformation des données d’un serveur particulier, ce qui vous permet de suivre la progression des données en cours de retraitement et de transformation.

![](assets/vis_ProcessingLegend.png)

Le tableau suivant répertorie les tâches qui peuvent être effectuées à l’aide de la variable [!DNL Processing Legend].

<table id="table_6149250C44B14C44A3CB1CEF68B280C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour effectuer cette tâche.. </th> 
   <th colname="col2" class="entry"> Procédez comme suit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pour afficher la taille totale de toutes vos données </p> </td> 
   <td colname="col2"> <p>Vérifiez les valeurs de la variable <span class="wintitle"> Nombre total d’entrées du journal</span> et <span class="wintitle"> Nombre total d’octets du journal</span> champs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour vérifier si le filtrage fonctionne </p> </td> 
   <td colname="col2"> <p>Vérifiez les valeurs de la variable <span class="wintitle"> Nombre total d’entrées de journal filtrées</span> champs. Si la valeur est 0, le filtrage ne fonctionne pas et vous devez vérifier votre configuration pour résoudre le problème. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vérification de la progression du traitement des logs </p> </td> 
   <td colname="col2"> <p>Vérifiez la valeur dans la variable <span class="wintitle"> Progression du traitement du journal</span> champ . Ce pourcentage indique la quantité de retraitement terminée. </p> <p>Lors du retraitement pour affiner votre jeu de données, vous pouvez surveiller le nombre de <span class="wintitle"> Nombre total d’entrées de journal décodées</span> par rapport au nombre de <span class="wintitle"> Nombre total d’entrées de journal filtrées</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vérification de la progression de la transformation </p> </td> 
   <td colname="col2"> <p>Vérifiez la valeur dans la variable <span class="wintitle"> Progression de la transformation</span> champ . Ce pourcentage indique la part totale de la transformation. </p> </td> 
  </tr> 
 </tbody> 
</table>
