---
description: L’interface Schéma du jeu de données affiche les dimensions étendues (dimensions dénombrables, simples, de type "plusieurs à plusieurs", numériques, non normalisées et temporelles) définies dans n’importe quel fichier de configuration du jeu de données de transformation et fournit une vue des relations entre ces dimensions.
title: Interface du schéma du jeu de données
uuid: 3726e568-d3ea-47f8-8ac4-582c97fbbe0a
exl-id: a8d4cf02-4ff7-4fcc-9062-425c1fe1fb28
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 3%

---

# Interface du schéma du jeu de données{#dataset-schema-interface}

{{eol}}

L’interface Schéma du jeu de données affiche les dimensions étendues (dimensions dénombrables, simples, de type &quot;plusieurs à plusieurs&quot;, numériques, non normalisées et temporelles) définies dans n’importe quel fichier de configuration du jeu de données de transformation et fournit une vue des relations entre ces dimensions.

En outre, la variable [!DNL Dataset Schema] affiche les dimensions dérivées que vous avez définies, ainsi que les dimensions étendues configurées pour être masquées.

![](assets/vis_DatasetSchema_Example2.png)

>[!NOTE]
>
>Vous pouvez rechercher des dimensions dans le diagramme de schéma. Le nom des dimensions trouvées par la chaîne de recherche est mis en surbrillance et les lignes de la classe parent changent de couleur pour tous les accès trouvés dans les dimensions enfants Secondaires. Les dimensions dénombrables restent visibles lorsque vous faites défiler l’écran pour afficher la hiérarchie et le contexte.

**Pour interpréter un type de dimension à l’aide de la variable [!DNL Dataset Schema] interface**

Le tableau suivant répertorie les types de dimensions et les couleurs dans lesquelles leurs noms apparaissent dans la variable [!DNL Dataset Schema] . Les parents des exemples de dimensions (de l’exemple ci-dessus) sont également pris en compte.

<table id="table_CF888522626E49A4A10D87085CAB5CC1"> 
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
   <td colname="col3"> <p>Visiteur : dans ce schéma, le visiteur est une dimension dénombrable racine. </p> <p>Session : le parent est Visiteur </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Jaune </td> 
   <td colname="col3"> DenormalPage : le parent est Page vue </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dérivé </td> 
   <td colname="col2"> Bleu </td> 
   <td colname="col3"> Page suivante : le parent est Page vue </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Multiple-à-multiple </td> 
   <td colname="col2"> Rose et vert (la racine du parent est rose, tandis que le nom de la dimension est vert.) </td> 
   <td colname="col3"> Terme de recherche : le parent est Session </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numérique </td> 
   <td colname="col2"> Vert </td> 
   <td colname="col3"> Durée exacte de la page : le parent est Page vue. Dans cet exemple, la durée exacte de la page est une dimension numérique masquée. Voir le type de dimension Masqué dans ce tableau. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simple </td> 
   <td colname="col2"> Vert </td> 
   <td colname="col3"> Page : le parent est Page vue </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure </td> 
   <td colname="col2"> Vert </td> 
   <td colname="col3"> Heure : le parent est Session </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Masqué </td> 
   <td colname="col2"> Les dimensions masquées sont une version plus foncée de la couleur de type de dimension appropriée. Par exemple, une dimension numérique masquée est un vert plus foncé et moins clair. </td> 
   <td colname="col3"> Durée exacte de la page : le parent est Page vue </td> 
  </tr> 
 </tbody> 
</table>

Pour plus d’informations sur ces types de dimension, voir *Guide de configuration des jeux de données*.

**Pour afficher la visualisation par défaut d’une dimension**

* Dans le [!DNL Dataset Schema] , cliquez sur la dimension souhaitée. La visualisation par défaut s’affiche. Par exemple, si la visualisation par défaut est un tableau affichant les sessions et la dimension sélectionnée et que vous cliquez sur la dimension URI, Data Workbench affiche un tableau URI par sessions.

   >[!NOTE]
   >
   >Si vous souhaitez modifier la visualisation par défaut qui s’affiche, reportez-vous à la section [Interface du schéma du jeu de données](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**Pour afficher une visualisation spécifique pour une dimension**

* Dans le [!DNL Dataset Schema] , cliquez avec le bouton droit de la souris sur la dimension souhaitée, puis cliquez sur **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.
