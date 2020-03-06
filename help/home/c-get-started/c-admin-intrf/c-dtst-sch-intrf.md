---
description: L’interface Schéma de jeu de données affiche les dimensions étendues (dénombrables, simples, de type "plusieurs à plusieurs", numériques, dénormalisées et temporelles) définies dans tout fichier de configuration de jeu de données de transformation et fournit une vue des relations entre ces dimensions.
solution: Analytics
title: Interface de schéma de jeu de données
topic: Data workbench
uuid: 3726e568-d3ea-47f8-8ac4-582c97fbbe0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Interface de schéma de jeu de données{#dataset-schema-interface}

L’interface Schéma de jeu de données affiche les dimensions étendues (dénombrables, simples, de type &quot;plusieurs à plusieurs&quot;, numériques, dénormalisées et temporelles) définies dans tout fichier de configuration de jeu de données de transformation et fournit une vue des relations entre ces dimensions.

En outre, l’ [!DNL Dataset Schema] interface affiche les dimensions dérivées que vous avez définies, ainsi que les dimensions étendues configurées pour être masquées.

![](assets/vis_DatasetSchema_Example2.png)

>[!NOTE]
>
>Vous pouvez rechercher des dimensions dans le diagramme de schéma. Le nom des dimensions trouvées par la chaîne de recherche est mis en surbrillance et les lignes de la classe parent changent de couleur pour tous les accès trouvés dans les dimensions enfants subordonnées. Les dimensions dénombrables restent visibles lorsque vous faites défiler l’écran pour afficher la hiérarchie et le contexte.

**Pour interpréter un type de dimension à l’aide de l’[!DNL Dataset Schema]interface**

Le tableau suivant répertorie les types de dimension et les couleurs dans lesquelles leurs noms apparaissent dans l’ [!DNL Dataset Schema] interface. Les parents des dimensions de l’échantillon (de l’exemple ci-dessus) sont également pris en compte.

<table id="table_CF888522626E49A4A10D87085CAB5CC1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de dimension </th> 
   <th colname="col2" class="entry"> Couleur </th> 
   <th colname="col3" class="entry"> Exemple de dimension et parent </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Comptable </td> 
   <td colname="col2"> Rose </td> 
   <td colname="col3"> <p>Visiteur : dans ce schéma, le visiteur est une dimension dénombrable racine. </p> <p>Session - parent est Visiteur </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Jaune </td> 
   <td colname="col3"> DenormalPage - parent est Page vue </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dérivé </td> 
   <td colname="col2"> Bleu </td> 
   <td colname="col3"> Page suivante - parent : Page vue </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plusieurs à plusieurs </td> 
   <td colname="col2"> Rose et Vert (la racine du parent est rose, tandis que le nom de la dimension est vert.) </td> 
   <td colname="col3"> Terme de recherche : le parent est Session </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numérique </td> 
   <td colname="col2"> Vert </td> 
   <td colname="col3"> Durée exacte de la page : parent est Page vue. Dans cet exemple, Durée exacte de la page est une dimension numérique masquée. Voir le type de dimension Masqué dans ce tableau. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simple </td> 
   <td colname="col2"> Vert </td> 
   <td colname="col3"> Page - parent est Page vue </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure </td> 
   <td colname="col2"> Vert </td> 
   <td colname="col3"> Heure - le parent est Session </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Masqué </td> 
   <td colname="col2"> Les dimensions masquées sont une version plus foncée de la couleur de type de dimension appropriée. Par exemple, une dimension numérique masquée est un vert plus foncé et moins lumineux. </td> 
   <td colname="col3"> Durée exacte de la page : parent est Page vue </td> 
  </tr> 
 </tbody> 
</table>

Pour plus d’informations sur ces types de dimension, voir le Guide *de configuration des jeux de* données.

**Pour afficher la visualisation par défaut d’une dimension**

* Dans l’ [!DNL Dataset Schema] interface, cliquez sur la dimension souhaitée. La visualisation par défaut s’affiche. Par exemple, si la visualisation par défaut est un tableau présentant les sessions et la dimension sélectionnée et que vous cliquez sur la dimension URI, les Outils de données affichent un tableau avec l’URI par session.

   >[!NOTE]
   >
   >Si vous souhaitez modifier la visualisation par défaut qui s’affiche, voir [L’interface](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)de schéma d’ensemble de données.

**Pour afficher une visualisation spécifique pour une dimension**

* Dans l’ [!DNL Dataset Schema] interface, cliquez avec le bouton droit de la souris sur la dimension souhaitée, puis cliquez sur **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.

