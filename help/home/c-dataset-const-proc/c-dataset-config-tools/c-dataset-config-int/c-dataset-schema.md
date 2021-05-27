---
description: L’interface Schéma du jeu de données affiche les dimensions étendues (dimensions dénombrables, simples, de type "plusieurs à plusieurs", numériques, non normalisées et temporelles) définies dans n’importe quel fichier de configuration du jeu de données de transformation, ainsi que les relations entre ces dimensions.
title: Schéma du jeu de données
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
exl-id: b80e6e8e-9147-46ec-8602-2d7e5d33f077
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 3%

---

# Schéma du jeu de données{#dataset-schema}

L’interface Schéma du jeu de données affiche les dimensions étendues (dimensions dénombrables, simples, de type &quot;plusieurs à plusieurs&quot;, numériques, non normalisées et temporelles) définies dans n’importe quel fichier de configuration du jeu de données de transformation, ainsi que les relations entre ces dimensions.

En outre, l’interface [!DNL Dataset Schema] affiche toutes les dimensions dérivées que vous avez définies, ainsi que toutes les dimensions étendues configurées pour être masquées.

![](assets/vis_DatasetSchema_Example.png)

Cette section traite des sujets suivants :

* [Pour interpréter le type de dimension à l’aide de l’interface Schéma du jeu de données](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [Pour afficher la visualisation par défaut d’une dimension](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [Pour afficher une visualisation spécifique pour une dimension](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## Interprétation du type de Dimension à l’aide de l’interface du schéma du jeu de données {#section-16a0a12b11334c07bec558c0b7d260b1}

Le tableau suivant répertorie les types de dimensions et les couleurs dans lesquelles leurs noms apparaissent dans l’interface [!DNL Dataset Schema]. Les parents des exemples de dimensions (de l’exemple ci-dessus) sont également pris en compte.

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de Dimension </th> 
   <th colname="col2" class="entry"> Couleur </th> 
   <th colname="col3" class="entry"> Exemple de Dimension et parent </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> dénombrable </td> 
   <td colname="col2"> Rose </td> 
   <td colname="col3"> <p>Visiteur : dans ce schéma, le visiteur est une dimension dénombrable racine. </p> <p> Session : le parent est Visiteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Jaune </td> 
   <td colname="col3"> DenormalPage : le parent est Page vue. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dérivé </td> 
   <td colname="col2"> Bleu </td> 
   <td colname="col3"> Page suivante : le parent est Page vue. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Multiple-à-multiple </td> 
   <td colname="col2"> Rose et vert (la racine du parent est rose, tandis que le nom de la dimension est vert.) </td> 
   <td colname="col3"> Terme de recherche : le parent est Session. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numérique </td> 
   <td colname="col2"> Vert </td> 
   <td colname="col3"> Durée exacte de la page : le parent est Page vue Dans cet exemple, Durée exacte de la page est une dimension numérique masquée. Voir le type de dimension Masqué dans ce tableau. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simple </td> 
   <td colname="col2"> Vert </td> 
   <td colname="col3"> Page : le parent est Page vue . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure </td> 
   <td colname="col2"> Vert </td> 
   <td colname="col3"> Heure : le parent est Session. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Masqué </td> 
   <td colname="col2"> Les dimensions masquées sont une version plus foncée de la couleur de type de dimension appropriée. Par exemple, une dimension numérique masquée est un vert plus foncé et moins clair. </td> 
   <td colname="col3"> Durée exacte de la page : le parent est Page vue. </td> 
  </tr> 
 </tbody> 
</table>

## Pour afficher la visualisation par défaut d’une Dimension {#section-1bbb73a5cbb34ffb844eb1932db85318}

* Dans l’interface [!DNL Dataset Schema], cliquez sur la dimension souhaitée. La visualisation par défaut s’affiche. Par exemple, si la visualisation par défaut est un tableau affichant les sessions et la dimension sélectionnée, et que vous cliquez sur la dimension URI, Data Workbench affiche un tableau avec l’URI par sessions.

>[!NOTE]
>
>Si vous souhaitez modifier la visualisation par défaut qui s’affiche, reportez-vous au chapitre Configuration de l’interface et des fonctionnalités d’analyse du *Guide de l’utilisateur du Data Workbench*.

## Affichage d’une visualisation spécifique pour une Dimension {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* Dans l’interface [!DNL Dataset Schema], cliquez avec le bouton droit de la souris sur la dimension souhaitée, puis cliquez sur **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]***.
