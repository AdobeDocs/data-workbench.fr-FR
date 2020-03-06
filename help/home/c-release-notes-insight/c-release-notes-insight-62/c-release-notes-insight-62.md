---
description: Les notes de mise à jour des outils de données version 6.2 comprennent les nouvelles fonctionnalités, les exigences de mise à niveau, les correctifs de bogues et les problèmes connus.
title: Notes de mise à jour des outils de données version 6.1
uuid: 8631c936-d53b-493d-9f58-72f541c3ddce
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbench 6.2 Release Notes{#data-workbench-release-notes}

Les notes de mise à jour des outils de données version 6.2 comprennent les nouvelles fonctionnalités, les exigences de mise à niveau, les correctifs de bogues et les problèmes connus.

## Nouvelles fonctionnalités {#section-1225066ea8f44cf68e42e019d0bca816}

Les outils de données version 6.2 comprennent les nouvelles fonctionnalités suivantes :

| Fonctionnalités  | Description |
|--- |--- |
| Arbres de décision | Les arborescences de décision sont une visualisation d’analyse prédictive utilisée pour évaluer les caractéristiques et les relations des visiteurs. Le créateur d’arborescence de décision génère une visualisation de l’arborescence de décision basée sur un cas positif et un jeu d’entrées spécifiques. |
| Mise à jour du filtre binaire dans la matrice de corrélation | Le filtre binaire a été mis à jour avec de nouvelles fonctionnalités, ce qui nécessite de recréer toute matrice de corrélation avec un filtre binaire créé dans les versions précédentes. |
| Carte de densité | La carte de densité est une visualisation qui affiche les éléments sous forme de rectangles ombrés dans une carte carrée. |
| Profil d’attribution | Pour analyser rapidement les valeurs d’attribution (événements afin d’attribuer la responsabilité d’une conversion ou d’une vente réussie), les outils de données fournissent un profil d’attribution basé sur des règles avec des fonctionnalités permettant à l’architecte de configurer les rapports d’attribution et à l’analyste d’exécuter les rapports. |
| Rapports Analytics | Les modèles de rapports normalisent les rapports d’Adobe Analytics pour les utilisateurs des outils de données qui utilisent le profil Adobe SC. Ces rapports sont identiques à ceux utilisés dans les rapports et analyses marketing (anciennement SiteCatalyst). |
| Graphiques de dispersion 3D | Un graphique de dispersion 3D montre les éléments d’une dimension de données (tels que Jours ou Site de référence) sur une grille tridimensionnelle où les axes x, y et z représentent différentes mesures. |


## Mises à jour de l’interface utilisateur client des outils de données{#data-workbench-client-ui-updates}

Outils de données version 6.2 comprend de nouvelles mises à jour de l’interface utilisateur du panneau Signets, de nouvelles icônes dans la barre d’outils de l’espace de travail, la possibilité de faire glisser l’espace de travail dans un écran, de nouvelles touches rapides et des mises à jour de la visualisation du graphique circulaire.

## Nouvelles fonctionnalités de signet {#section-e361b605441540ca8213c3fddb5e0718}

Vous pouvez désormais mettre en signet des espaces de travail importants pour passer rapidement d’une visualisation à l’autre des rapports utilisés dans votre flux de travail.

**Utilisation de signets**

1. Mettez un signet dans un espace de travail en cliquant sur l’icône Signet ![](assets/bookmark_icon.png) dans le coin supérieur droit de la barre d’outils.
1. Cliquez sur **[!UICONTROL Add]** > **[!UICONTROL Bookmarks Panel]** dans le volet de gauche pour ouvrir une liste de signets.

   ![](assets/bookmarks_panel.png)

1. Pour ouvrir un espace de travail marqué d’un signet, cliquez sur le nom d’un espace de travail dans le **[!UICONTROL Bookmark Panel]**.

   ![](assets/bookmarks_panel_left.png)

   L&#39;espace de travail sélectionné s&#39;ouvre. Lorsque vous cliquez sur un autre espace de travail marqué, l’espace de travail précédent se ferme et le nouvel espace de travail sélectionné s’ouvre, ce qui vous permet de naviguer rapidement dans votre flux de travail.

**Pour supprimer un signet :**

* Dans le panneau Signet, cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Supprimer.<bookmark title>]**pour supprimer un signet sélectionné ou **[!UICONTROL Clear All Bookmarks]**pour supprimer tous les signets.

* Vous pouvez également cliquer avec le bouton droit de la souris sur l’espace de travail dans la vue miniature du plan de travail et sélectionner **[!UICONTROL Clear Bookmark]**.

>[!IMPORTANT]
>
>* 25 signets peuvent être enregistrés.
>* Si vous ajoutez un signet, puis déplacez l’emplacement de l’espace de travail, le signet n’est pas valide et doit être supprimé du panneau des signets et réinitialisé.
>



## Nouvelles icônes dans Workspace {#section-c108bbd1661249e79c146727ff3d2470}

Les outils de données version 6.2 remplacent désormais le texte de l’espace de travail par des icônes. Vous pouvez toujours placer le pointeur de la souris sur l’icône et afficher le message d’info-bulle identifiant l’icône, y compris **[!UICONTROL File]**, **[!UICONTROL Add]** et **[!UICONTROL Export]**.

![](assets/new_icons.png)

Une nouvelle **[!UICONTROL Help]** icône est ajoutée pour accéder à la documentation et aux autres centres de connaissances, notamment les liens suivants :

<table id="table_64BBC67B1BB44B1197FF7E5E7B067696"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Liens vers la documentation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Reports &amp; Analytics marketing </td> 
   <td colname="col2">Ouvrez la page d’aide Rapports et analyses <span class="uicontrol"> marketing d’</span> Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Échange d’idées </td> 
   <td colname="col2">Ouvrez une session <span class="uicontrol"> Idea Exchange</span>. Ce portail en ligne permet aux utilisateurs de proposer des modifications de mise à jour et des idées d’amélioration aux outils de données. Ces idées orientées client peuvent alors être votées par tous les utilisateurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aide </td> 
   <td colname="col2">Ouvrez la documentation <span class="uicontrol"> des outils de</span>données. <p>Vous pouvez également appuyer sur <span class="uicontrol"> &lt;F1&gt;</span> pour ouvrir l’aide dans un espace de travail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> À propos de </td> 
   <td colname="col2">Ouvrez cette fenêtre pour identifier la version <span class="uicontrol"></span> client des outils de données. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Vous pouvez également appuyer sur `<F1>` pour ouvrir la documentation à partir d’un espace de travail.

## Faire glisser les vues de l’espace de travail {#section-9129c340c21d45a3864c923884cd4382}

Si un espace de travail est plus grand que l’écran affichable, vous pouvez déplacer la vue pour afficher tous les éléments de l’espace de travail. Vous pouvez cliquer en arrière-plan (en dehors des visualisations et des tableaux) et faire glisser l’écran pour déplacer la zone visible dans l’espace de travail. Le curseur se transforme en icône en forme de main lorsque vous faites glisser la vue dans le cadre de l’espace de travail.

![](assets/drag_workspace.png)

## Touches rapides pour modifier les vues de l’espace de travail {#section-d8322f72423f437aa2e34f2188b1341c}

Les nouvelles touches rapides vous permettent de redimensionner et de redimensionner les espaces de travail entre les vues de la fenêtre et de la page entière.

<table id="table_A01C514C99F043338D183A6839E03DEA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Commandes </th> 
   <th colname="col2" class="entry"> Touches rapides </th> 
   <th colname="col3" class="entry"> Commandes de menu combinées </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Affichage</b>plein écran. Workspace remplit l’écran et le redimensionne. </td> 
   <td colname="col2"><b>Ctrl +</b> <p>Ctrl + (sur le pavé numérique) </p> <p><i>ou</i> </p> <p>Ctrl + Maj (sur le clavier) </p> </td> 
   <td colname="col3"> 
    <ul id="ul_C7C731B894D946D9916F50806F015857"> 
     <li id="li_452B4C119B1A40038A408CFFC53653A9">Fichier &gt; Format de page &gt; Ecran de remplissage <p><i>suivi par</i> </p> </li> 
     <li id="li_DE9B8B31B9F24A6AA68A1D0DB886B501">Fichier &gt; Modifier l’espace de travail </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Vue</b>fenêtre. Workspace s’affiche dans une fenêtre standard et s’adapte à la nouvelle taille. </td> 
   <td colname="col2"><b>Ctrl moins</b> <p>Ctrl - </p> </td> 
   <td colname="col3"> 
    <ul id="ul_3474B9EFD69343C09BC84E485D896C28"> 
     <li id="li_820BAED76FF24A5785E6D89C5C692DD5">Fichier &gt; Format de page &gt; Standard <p><i>suivi par</i> </p> </li> 
     <li id="li_337789F282CE4C2C990C67B115782454">Fichier &gt; Modifier l’espace de travail </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Corrections de bogues {#section-8704a9ac358246cd81233dd0982d534f}

* Mise à jour du fichier de recherche Site visuel afin d’examiner les modifications apportées au terme de recherche de requête par les moteurs de recherche.
* Correction d’un message d’erreur inexact, &quot;Impossible d’importer l’espace de travail&quot;, lors de l’importation d’un espace de travail dans la station de travail cliente, même si l’importation a réussi.
* L’erreur de connexion à la station de travail affichant le message &quot;Conflit de configuration 412&quot; est maintenant remplacée par un message convivial qui identifie l’action du système.
* La commande post peut être désormais exécutée dans Report Server.
* Correction des erreurs d’interface utilisateur dans l’interface utilisateur client pour le chinois simplifié.
* Adobe Analytics a mis à jour le flux de données qui alimente les outils de données afin de tirer parti des profils et audiences qui s’intègrent à Adobe Experience Cloud. Tous les utilisateurs des outils de données devaient préparer leur environnement pour cette transition d’ici le 21 avril 2014.

   Profils et audiences ont été introduits afin de fournir une vue complète des clients dans Adobe Analytics. Ce nouveau service est disponible dans Adobe Experience Cloud afin d’optimiser davantage les outils d’analyse et de créer ainsi les bases de ces fonctionnalités dans Analytics. Le nouvel identifiant visiteur d’Experience Cloud sera ajouté au flux de données, ainsi que d’autres améliorations et améliorations pour s’adapter au nouveau flux de données et à l’identifiant visiteur global.
* Lors de l’importation d’un espace de travail, un message d’erreur s’affiche même si l’importation a réussi.

## Configuration requise pour la mise à niveau {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* Le profil d’attribution est configuré pour que les utilisateurs qui ont mis en oeuvre le profil Adobe SC utilisent le flux de données Analytics (SC/Insight). Par défaut, les événements Marketing et Conversion sont utilisés comme interactions par défaut évaluées dans les modèles basés sur des règles.
* Pour les utilisateurs de la mise à niveau du profil Adobe SC vers Data Workbench 6.2, si vous n’utilisez pas les configurations par défaut, vérifiez que la [!DNL x-bot_id] valeur du [!DNL SC Fields.cfg] fichier est décodée correctement et que le [!DNL x-bot_id] champ est correctement répertorié dans les fichiers [!DNL Decoding Instructions.cfg] et [!DNL Exclude Hit.cfg] . Ce problème se produira uniquement si vous avez modifié le fichier de configuration à partir de la configuration par défaut.

* Si vous avez supprimé des champs inutilisés dans le fichier **[!UICONTROL Dataset]** > **[!Traitement** du journal UICONTROL > **[!DNL SC Fields.cfg]** pour le profil Adobe SC, vous devez effectuer une mise à jour afin de prendre en compte les valeurs de champ mises à jour utilisées pour le profil d’attribution.

## Problèmes connus {#section-dbb307639835493a83409f5f461932b8}

* Lorsque la visualisation en graphique de dispersion 3D inclut des légendes, le zoom peut afficher des tracés en dehors de la bordure de la visualisation.

   Solution : Faites d’abord un zoom sur le graphique de dispersion 3D, puis ajoutez des légendes à votre visualisation.
* Si vous faites glisser la mesure du panneau Rechercher vers la légende de mesure en dehors de la colonne de mesure, la légende de mesure sera supprimée de l’espace de travail.

   Solution : Les utilisateurs qui souhaitent faire glisser des mesures vers la légende des mesures doivent déposer leur nom dans la première colonne (colonne des mesures).
* L’option Imprimer l’espace de travail à l’aide de l’encadré et des deux options n’inclut pas les informations de copyright sur la page imprimée.
* L’utilisation de Workstation dans une session de bureau distante se bloque lors du changement de nom des espaces de travail.
* (Dans la version en chinois simplifié) Les sorties de rapport réelles sont valides dans le serveur de rapports, mais les lignes d’objet du courrier électronique et les noms des fichiers joints sont altérés.
* (En chinois simplifié) Lors de l’utilisation de l’encapsulation de mot dans la visualisation Feuille de calcul, les mots localisés ne sont pas correctement encapsulés, ce qui entraîne l’ajout de caractères indésirables à la chaîne.
* (Dans la version en chinois simplifié) Impossible de lancer Insight.exe si le répertoire d’installation est nommé avec des caractères non anglais.

   Solution : Conservez les noms par défaut ou renommez en utilisant uniquement des caractères anglais dans le chemin du dossier pour lancer les exécutables.

