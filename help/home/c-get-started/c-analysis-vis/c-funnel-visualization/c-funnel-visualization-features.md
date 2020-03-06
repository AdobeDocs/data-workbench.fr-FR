---
description: La visualisation Entonnoir comprend des fonctionnalités permettant de créer un entonnoir avec plusieurs dimensions, un nombre brut de visiteurs, le pourcentage de visiteurs à chaque étape et des étendues distinctes.
solution: Analytics
title: Fonctionnalités de l'entonnoir
topic: Data workbench
uuid: 7d2f5ff9-95d3-41f5-931c-689f140714c2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Fonctionnalités de l&#39;entonnoir{#funnel-features}

La visualisation Entonnoir comprend des fonctionnalités permettant de créer un entonnoir avec plusieurs dimensions, un nombre brut de visiteurs, le pourcentage de visiteurs à chaque étape et des étendues distinctes.

Voici les fonctionnalités de base de la visualisation de l’entonnoir.

![](assets/funnel_visualization_capture.png)

<table id="table_49A08740CEE74D64B6F9C37CD91F1AE5"> 
 <tbody> 
  <tr> 
   <td colname="col01"> <img id="image_0C1701833FE049708CE38ADEB5EC7EEF" src="assets/funnel_visualization_capture_1.png" /> </td> 
   <td colname="col1"> Premier élément </td> 
   <td colname="col2"> Première étape de l'entonnoir dans le processus. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_EF8AF94D833B4A249959B76F8FAF2318" src="assets/funnel_visualization_capture_2.png" /> </td> 
   <td colname="col1"> Troisième élément </td> 
   <td colname="col2">Troisième étape de l'entonnoir dans le processus. <p><p>Remarque :  Les éléments sélectionnés ne doivent pas nécessairement provenir de la même dimension. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_F3C5130B52234FAC9DEB50279F94FF90" src="assets/funnel_visualization_capture_3.png" /> </td> 
   <td colname="col1"> Pourcentage de retombées </td> 
   <td colname="col2"> Pourcentage qui a terminé le chemin défini affiché dans trois étendues. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_3F030396CEB14528980F5B965113BD36" src="assets/funnel_visualization_capture_4.png" /> </td> 
   <td colname="col1"> Navigateur d’abandons </td> 
   <td colname="col2">Flèche d'abandons. Cliquez avec le bouton droit de la souris et sélectionnez <span class="uicontrol"> Ajouter un navigateur</span> de chemin pour afficher le chemin emprunté par les autres visiteurs. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_0DA7567BDBDF4BEF9CA840D2F88A414E" src="assets/funnel_visualization_capture_5.png" /> </td> 
   <td colname="col1"> Abandon en pourcentage </td> 
   <td colname="col2">Pourcentages décrivant trois étendues d’abandon pour les utilisateurs qui n’ont pas terminé le chemin d’accès. <p>Les pourcentages sont présentés dans trois domaines : </p><p><img id="image_B85C46DDF12C41D5BF213D5F9DC04967" placement="break" src="assets/funnel_path_browser_5.png" /></p><p><img id="image_BC37007D7B4B425C8F87905CE68F0114" src="assets/funnel_path_browser_6.png" /> Pourcentage d’abandons de l’étape précédente à cette étape. </p><p><img id="image_B10866B083424360AFF1B19E836A94CF" src="assets/funnel_path_browser_7.png" /> Pourcentage d’abandons de la première étape de l’entonnoir. </p><p><img id="image_19B9AE916B584E18A82F5D5E10674414" src="assets/funnel_path_browser_8.png" /> Pourcentage d’abandons en fonction du nombre total de visiteurs. </p></td> 
  </tr> 
 </tbody> 
</table>

## Etapes de l&#39;entonnoir {#section-96a6732558dd4740b73541844f06d3ef}

Les disques d&#39;un entonnoir représentent les étapes de la navigation, les cônes représentent les abandons d&#39;une étape à l&#39;autre et les flèches représentent les abandons. En cliquant sur un cône, vous sélectionnez les utilisateurs qui sont passés par ce point et les incluez dans le filtre de l’espace de travail actuel. Cliquez sur une flèche pour sélectionner les visiteurs qui sont tombés.

>[!NOTE]
>
>La visualisation Entonnoir est limitée à huit étapes qui peuvent être appliquées.

## Fonctionnalités et fonctionnalités supplémentaires de l&#39;entonnoir {#section-22a3582db8114ca8bce77f50bbbf296a}

* **Réglez l’élément et le niveau de l’entonnoir**. Sélectionnez l’option Entonnoir dans le menu Visualisation. Une fois l’entonnoir créé, vous pouvez cliquer avec le bouton droit sur le titre pour ajuster l’élément et le niveau à n’importe quelle mesure dénombrable de votre système.

   ![](assets/funnel_path_browser_9.png)

* **Faites glisser d’autres éléments**. Ajoutez d&#39;autres éléments à votre entonnoir en les faisant glisser du tableau Dimension vers l&#39;entonnoir à l&#39;aide des touches `<Ctrl>` + `<Alt>` . Vous pouvez faire glisser plusieurs étapes en même temps à partir du tableau Dimension en sélectionnant plusieurs éléments (à l’aide de `<Ctrl>` + clic), puis en les faisant glisser vers la visualisation Entonnoir à l’aide des `<Ctrl>` + `<Alt>` touches.
* **Supprimez une étape**: Supprimez des éléments en cliquant avec le bouton droit sur l’étape de la visualisation et en cliquant sur **Oui**.

   ![](assets/funnel_path_browser_4.png)

* **Réorganisez les étapes que vous avez déplacées vers l&#39;entonnoir**. Il vous suffit de cliquer sur l’étape pour la sélectionner et de la faire glisser vers une autre position pour réorganiser les étapes.
* **Ouvrez un navigateur** de chemins. Vous pouvez afficher plus de détails sur l’emplacement des clients qui passent par le processus ou en sortent grâce à la fonction [Ajouter un navigateur](../../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-path-browser-funnel.md#concept-b0cedf7a28ae422696ded1258c9a4119) de chemin.

* **Ajoutez d’autres étapes**. Vous pouvez ajouter un maximum de huit étapes à chaque visualisation de l’entonnoir.
* **Modifiez la mesure**. La mesure peut être modifiée afin que les étapes comptabilisent les visites ou une autre mesure à chaque étape. Les options disponibles varient en fonction du jeu de données.
* **S’affiche dans une vue** tabulaire. Cliquez avec le bouton droit sur le titre pour afficher le menu de visualisation de l&#39;entonnoir, puis cliquez sur **[!UICONTROL Show Tabular View]**. Une fois dans la vue tabulaire, vous pouvez choisir **[!UICONTROL Show Graph View]** de revenir à la représentation graphique de l&#39;entonnoir. Pour ouvrir la vue tabulaire, cliquez avec le bouton droit sur le titre et sélectionnez Afficher la vue tabulaire dans le menu.

* **Comparaison de séquences**. Une méthode efficace pour comparer deux séquences similaires consiste à afficher leurs deux visualisations côte à côte. Vous pouvez également afficher côte à côte la vue tabulaire et la vue graphique à l’aide de la fonction Dupliquer. Pour ouvrir, cliquez avec le bouton droit sur le titre et sélectionnez Dupliquer dans le menu.
