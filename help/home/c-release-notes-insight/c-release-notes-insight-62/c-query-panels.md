---
description: Utilisez les panneaux du Finder dans Data Workbench pour sélectionner des mesures, des dimensions et des filtres. Ces panneaux fournissent la prise en charge de la recherche, des options de tri et des fonctionnalités de glisser-déposer.
title: Finders
uuid: 7a4144f5-133f-48ed-9613-1e42b1313120
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 1%

---


# Finders{#finders}

Utilisez les panneaux du Finder dans Data Workbench pour sélectionner des mesures, des dimensions et des filtres. Ces panneaux fournissent la prise en charge de la recherche, des options de tri et des fonctionnalités de glisser-déposer.

Un panneau de l’outil de recherche peut être ouvert dans la barre latérale gauche ou dans un espace de travail.

![](assets/query_entity_panel_main.png)

<table id="table_3E43DBA0646842898F14F31374F9E39C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Outil de recherche de Dimensions </th> 
   <th colname="col2" class="entry"> Outil de recherche de mesures </th> 
   <th colname="col3" class="entry"> Outil de recherche des filtres </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Liste de toutes les dimensions de votre modèle de requête. </p><img placement="break" id="image_D7D317D84C0843BE8D324E5B9F7AF20D" src="assets/query_entity_dim_panel.png" /> </td> 
   <td colname="col2"> <p>Liste de toutes les mesures de votre modèle de requête. </p><img placement="break" id="image_04553B2F2C6A48FE897B4EFF002BED59" src="assets/query_entity_metric_panel.png" /> </td> 
   <td colname="col3"> <p>Liste de tous les filtres créés pour votre organisation. </p><img placement="break" id="image_920E72D795644634A82D1955CB64B355" src="assets/query_entity_filters_panel.png" /> </td> 
  </tr> 
 </tbody> 
</table>

**Pour ouvrir un Finder :**

* Cliquez avec le bouton droit dans un espace de travail et sélectionnez **[!UICONTROL Tools]** > **[!UICONTROL Finder]**.

   Le volet de recherche contenant des onglets pour les mesures, les Dimensions et les filtres s’ouvre dans l’espace de travail.

* Cliquez avec le bouton droit dans la barre latérale gauche et sélectionnez **[!UICONTROL Add]** > **[!UICONTROL Finder]**.

   Le volet de recherche s’ouvre dans le panneau de gauche.

Le **Finder** comprend les fonctionnalités suivantes :

<table id="table_072047E919204577AE85789BAE0F4EE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fonctionnalités du Finder </th> 
   <th colname="col2" class="entry"> Détails </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Glisser-déposer</b> </td> 
   <td colname="col2"> <p> Vous pouvez faire glisser des dimensions ou des mesures du panneau vers une visualisation dans l’espace de travail pour modifier la dimension ou ajouter de nouvelles mesures. </p> 
    <ol id="ol_612DC76EC04C4FCE938B20B388C43CE8"> 
     <li id="li_7F73B781141E4B8CAE9800F580F62E44">Maintenez les touches <span class="uicontrol"> &lt;Ctrl&gt;</span> et <span class="uicontrol"> &lt;Alt&gt;</span> enfoncées et sélectionnez la dimension ou la mesure dans le panneau de l’outil de recherche. </li> 
     <li id="li_631D57976F71415AA61F33EBBFDD128A">Faites glisser une nouvelle dimension depuis le panneau et déposez-la dans la visualisation pour modifier ou ajouter des dimensions. </li> 
     <li id="li_5329FB82225F46EBBE3A996A641058DE">Pour ajouter des mesures, faites glisser une nouvelle mesure depuis le panneau et déposez-la dans l’en-tête de mesure de la visualisation sélectionnée. </li> 
    </ol> <p>Cela fonctionne pour toutes les visualisations pertinentes, y compris les tableaux, la grappe de visiteurs, la matrice de corrélation, les tracés de dispersion et le graphique à barres en 2D (selon l’axe). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Recherche</b> </td> 
   <td colname="col2">Une zone <span class="uicontrol"> Rechercher</span> dans les panneaux de l’outil de recherche vous permet de filtrer les noms des Dimensions, des mesures et des filtres. 
    <ul id="ul_0F6F377E9906472E99008EBE7483F689"> 
     <li id="li_75857895EDB045C8B2960393854B257D"> <p>Correspondance de motifs (recherche glob simple). Commencez à saisir le nom d’une dimension, d’une mesure ou d’une entité de filtre requise dans le champ Rechercher . Seules les chaînes correspondantes, qui se trouvent dans le nom, seront filtrées et affichées dans le volet Finders. </p> <p>Par exemple, saisissez : </p> <code><b>Search:</b>click</code> <p>Vous pouvez obtenir les résultats suivants dans l’outil de recherche de Dimensions : </p> <p><img placement="break" id="image_7CBAAABA92BB47658B7F9F5C0263CF20" src="assets/finders_glob_search.png" /> </p> <p>La correspondance de modèle standard vous permet d’utiliser des caractères génériques, tels que . (point), "?" , et "*" (étoile). </p> </li> 
     <li id="li_044F9EC1399B44CD81E1852F85137704"> <p>Expressions régulières. Des expressions régulières plus complexes sont également prises en charge pour ajouter des fonctionnalités de recherche. Ajoutez le préfixe "re:" devant votre terme de recherche (sans espaces) à interpréter comme une expression régulière. </p> <p>Par exemple, saisissez : </p> <code><b>Search:</b>re.*ip</code> <p>Vous pouvez obtenir les résultats suivants dans l’outil de recherche de Dimensions : </p> <p><img placement="break" id="image_F47DB90B36504997AA1C509855B89A47" src="assets/finders_regex_search.png" /> </p> </li> 
    </ul> <p>Pour des informations de recherche détaillées, voir <a href="https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-reg-exp.html" format="http" scope="external"> expressions régulières</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Type de Dimension</b> </td> 
   <td colname="col2">Dans l’onglet Dimension , vous pouvez cliquer avec le bouton droit de la souris sur l’en-tête de l’onglet pour trier par type de dimension. <p><img id="image_FB44D0F4D36B4AD7A6165E0432211AB6" placement="break" src="assets/query_entity_search_types.png" /> 
     <ul id="ul_D36B8474730F4859BC7AA015CC1B8EF0"> 
      <li id="li_4AE1D5699D0E45AF880A134F886B8B19">Attributs : Dimensions créées en fonction des caractéristiques du visiteur, des produits, de la zone géographique, de l’heure, de la vidéo et d’autres attributs. </li> 
      <li id="li_0B2A08F8CBE94356AC506F95DC268C47">Clusters : Dimensions créées dans le créateur de cluster. </li> 
      <li id="li_4BC3396A680B49A4B6BDAAD066826864">Scores : Dimensions créées dans le score de propension. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Étiquette</b> </td> 
   <td colname="col2">Dans chaque onglet, cliquez avec le bouton droit de la souris et sélectionnez <span class="uicontrol"> Libellé</span> pour renommer le volet de recherche. <p><img placement="break" id="image_F61C57F6548646069242DFB2490C67B9" src="assets/label_change.png" /> </p> <p>Les étiquettes Dimensions, Mesures et Filtres par défaut peuvent être remplacées par un nom d’onglet qui correspond aux conventions de votre entreprise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Ajouter un élément</b> </td> 
   <td colname="col2">Dans chaque onglet, cliquez avec le bouton droit de la souris et sélectionnez <span class="uicontrol"> Ajouter un élément</span> pour ouvrir un tableau et ajouter manuellement des Dimensions, des mesures et des filtres. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Barre de recherche</b> </td> 
   <td colname="col2">Cliquez avec le bouton droit de la souris dans la barre <span class="uicontrol"> Finders</span> de la barre latérale gauche pour ouvrir un menu pour des fonctionnalités supplémentaires. <p><img placement="break" id="image_4DA4930294B84308A1E627C828C35663" src="assets/finders_menu.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Fermer</b> </td> 
   <td colname="col2">Cliquez avec le bouton droit de la souris dans la barre <span class="uicontrol"> Finders</span> et sélectionnez <span class="uicontrol"> Close</span> pour fermer un volet Finders. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Enregistrer</b> </td> 
   <td colname="col2">Enregistrez la liste localement en cliquant avec le bouton droit de la souris dans la barre d’en-tête et en sélectionnant l’option <span class="uicontrol"> Enregistrer</span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Exporter</b> </td> 
   <td colname="col2">Vous pouvez exporter une liste de dimensions, de mesures ou de filtres sélectionnés à partir du panneau du Finder en cliquant avec le bouton droit de la souris dans la barre Finders et en sélectionnant <span class="uicontrol"> Exporter</span> dans le menu. <p> Ajoutez un nom et exportez-le dans Microsoft Excel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Copier</b> </td> 
   <td colname="col2"> Copiez une liste de Dimensions, de mesures ou de filtres. Vous pouvez le copier sous la forme d’un fichier ou d’un graphique dans un arrière-plan sombre, un arrière-plan clair ou un monochrome. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Réduire</b> </td> 
   <td colname="col2"> Minimiser le volet de recherche. Seule la barre de recherche s’affiche. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>sans bordure</b> </td> 
   <td colname="col2"> Affiche un volet sans lignes de bordure pour les outils de recherche dans l’espace de travail (mais pas dans la barre latérale gauche). </td> 
  </tr> 
 </tbody> 
</table>

