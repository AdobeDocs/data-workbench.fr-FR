---
description: La visualisation Entonnoir comprend des fonctionnalités permettant de créer un entonnoir avec plusieurs dimensions, des nombres bruts de visiteurs, le pourcentage de visiteurs à chaque étape et des portées distinctes.
title: Fonctionnalités de l’entonnoir
uuid: 7d2f5ff9-95d3-41f5-931c-689f140714c2
exl-id: e78dcefe-6f92-45de-9990-0beac09ad82f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

---

# Fonctionnalités de l’entonnoir{#funnel-features}

{{eol}}

La visualisation Entonnoir comprend des fonctionnalités permettant de créer un entonnoir avec plusieurs dimensions, des nombres bruts de visiteurs, le pourcentage de visiteurs à chaque étape et des portées distinctes.

Voici les fonctions de base de la visualisation entonnoir.

![](assets/funnel_visualization_capture.png)

<table id="table_49A08740CEE74D64B6F9C37CD91F1AE5"> 
 <tbody> 
  <tr> 
   <td colname="col01"> <img id="image_0C1701833FE049708CE38ADEB5EC7EEF" src="assets/funnel_visualization_capture_1.png" /> </td> 
   <td colname="col1"> Premier élément </td> 
   <td colname="col2"> Première étape de l’entonnoir dans le processus. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_EF8AF94D833B4A249959B76F8FAF2318" src="assets/funnel_visualization_capture_2.png" /> </td> 
   <td colname="col1"> Troisième élément </td> 
   <td colname="col2">Troisième étape de l’entonnoir dans le processus. <p><p>Remarque : Les éléments sélectionnés ne doivent pas nécessairement appartenir à la même dimension. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_F3C5130B52234FAC9DEB50279F94FF90" src="assets/funnel_visualization_capture_3.png" /> </td> 
   <td colname="col1"> Pourcentage d’abandons </td> 
   <td colname="col2"> Pourcentage d’utilisateurs ayant suivi le chemin défini affiché en trois portées. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_3F030396CEB14528980F5B965113BD36" src="assets/funnel_visualization_capture_4.png" /> </td> 
   <td colname="col1"> Navigateur d’abandons </td> 
   <td colname="col2">Flèche d’abandons. Cliquez avec le bouton droit et sélectionnez <span class="uicontrol"> Ajouter un navigateur de chemins d’accès</span> pour voir les autres chemins empruntés par les visiteurs. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_0DA7567BDBDF4BEF9CA840D2F88A414E" src="assets/funnel_visualization_capture_5.png" /> </td> 
   <td colname="col1"> Abandon en pourcentage </td> 
   <td colname="col2">Pourcentages décrivant trois portées d’abandon pour les utilisateurs qui n’ont pas terminé le chemin d’accès. <p>Les pourcentages sont présentés dans trois portées : </p><p><img id="image_B85C46DDF12C41D5BF213D5F9DC04967" placement="break" src="assets/funnel_path_browser_5.png" /></p><p><img id="image_BC37007D7B4B425C8F87905CE68F0114" src="assets/funnel_path_browser_6.png" /> Pourcentage d’abandons de l’étape précédente à cette étape. </p><p><img id="image_B10866B083424360AFF1B19E836A94CF" src="assets/funnel_path_browser_7.png" /> Pourcentage d’abandons à partir de la première étape de l’entonnoir. </p><p><img id="image_19B9AE916B584E18A82F5D5E10674414" src="assets/funnel_path_browser_8.png" /> Pourcentage d’abandons basé sur le nombre total de visiteurs. </p></td> 
  </tr> 
 </tbody> 
</table>

## Étapes de l’entonnoir {#section-96a6732558dd4740b73541844f06d3ef}

Les disques d’un entonnoir représentent les étapes de navigation, les cônes représentent les abandons d’une étape à l’autre et les flèches représentent les abandons. Cliquer sur un cône permet de sélectionner les utilisateurs qui sont passés par là et de les inclure dans le filtre de l’espace de travail actuel. Cliquez sur une flèche pour sélectionner les visiteurs qui sont tombés.

>[!NOTE]
>
>La visualisation Entonnoir est limitée à huit étapes qui peuvent être appliquées.

## Fonctionnalités et fonctionnalités supplémentaires de l’entonnoir {#section-22a3582db8114ca8bce77f50bbbf296a}

* **Réglage de l’élément et du niveau de l’entonnoir**. Sélectionnez l’option Entonnoir dans le menu Visualisation . Une fois l’entonnoir créé, vous pouvez cliquer avec le bouton droit sur le titre pour ajuster le clip et le niveau à n’importe quelle mesure dénombrable de votre système.

   ![](assets/funnel_path_browser_9.png)

* **Faire glisser d’autres éléments**. Ajoutez d’autres éléments à votre entonnoir en les faisant glisser du tableau de Dimension vers l’entonnoir à l’aide de la fonction `<Ctrl>` + `<Alt>` clés. Vous pouvez faire glisser plusieurs étapes en même temps depuis le tableau de Dimension en sélectionnant plusieurs éléments (à l’aide de la fonction `<Ctrl>` + cliquez dessus), puis faites-les glisser vers la visualisation Entonnoir à l’aide du `<Ctrl>` + `<Alt>` clés.
* **Suppression d’une étape**: Supprimer des éléments en cliquant avec le bouton droit de la souris sur l’étape de la visualisation, puis en cliquant sur **Oui**.

   ![](assets/funnel_path_browser_4.png)

* **Réorganiser les étapes que vous avez glissées vers l’entonnoir**. Il vous suffit de cliquer sur l’étape pour la sélectionner et de la faire glisser vers un autre emplacement afin de réorganiser les étapes.
* **Ouvrir un navigateur de chemins d’accès**. Vous pouvez afficher plus d’informations sur les domaines dans lesquels les clients abandonnent le processus au moyen de la variable [Ajout d’un navigateur de chemins d’accès](../../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-path-browser-funnel.md#concept-b0cedf7a28ae422696ded1258c9a4119) fonction .

* **Ajouter d’autres étapes**. Vous pouvez ajouter huit étapes maximum à chaque visualisation entonnoir.
* **Modification de la mesure**. La mesure peut être modifiée afin que les étapes comptabilisent les visites ou une autre mesure à chaque étape. Les options disponibles varient selon le jeu de données.
* **Affichage dans une vue tabulaire**. Cliquez avec le bouton droit sur le titre pour afficher le menu de visualisation Entonnoir , puis cliquez sur **[!UICONTROL Show Tabular View]**. Une fois dans la vue tabulaire, vous pouvez sélectionner **[!UICONTROL Show Graph View]** pour revenir à la représentation graphique de l’entonnoir. Pour ouvrir la vue Tableau, cliquez avec le bouton droit sur le titre, puis sélectionnez Afficher la vue tabulaire dans le menu.

* **Comparaison de séquences**. Une méthode efficace pour comparer deux séquences similaires consiste à afficher côte à côte leurs deux visualisations. Vous pouvez également afficher côte à côte la vue tabulaire et la vue graphique à l’aide de la fonction Dupliquer . Pour ouvrir, cliquez avec le bouton droit sur le titre et sélectionnez Dupliquer dans le menu.
