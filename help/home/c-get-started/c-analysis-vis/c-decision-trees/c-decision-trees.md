---
description: Les arbres de décision sont une visualisation d’analyse prédictive utilisée pour évaluer les caractéristiques et les relations des visiteurs. Le créateur d’arborescence de décision génère une visualisation de l’arborescence de décision basée sur un cas positif et un jeu d’entrées spécifiques.
title: Créateur d’arbre de décision
uuid: 1f7e91ea-e5d9-4d8e-9fcf-cae4de42dfdd
exl-id: d93e6a34-be59-4af5-84c3-c13deb98b57b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 23%

---

# Créateur d’arbre de décision{#decision-tree-builder}

Les arbres de décision sont une visualisation d’analyse prédictive utilisée pour évaluer les caractéristiques et les relations des visiteurs. Le créateur d’arborescence de décision génère une visualisation de l’arborescence de décision basée sur un cas positif et un jeu d’entrées spécifiques.

Une Arborescence de décision est un classificateur binaire comportant un jeu de règles (ou de filtres) identifiant les visiteurs qui respectent des règles spécifiques basées sur un cas positif. Une arborescence de décision définit des règles pour classer les visiteurs qui respectent (ou ne respectent pas) ce cas positif. Ces règles génèrent une carte de l’arborescence qui fournit un niveau de confiance correspondant aux résultats des cas positifs.

Un arbre de décision est créé en examinant les entrées à chaque niveau et en choisissant celui qui fournit un gain maximal d&#39;informations à un point de division spécifié. La division des points pour chaque niveau de variable génère deux jeux :

* Valeurs inférieures ou égales au point de division, et
* Valeurs supérieures au point de division.

Utilisez les arborescences de décision pour

* Effectuez une analyse et une interprétation significatives en moins de temps.
* Utilisez la génération de segments automatisée.
* Effectuez rapidement des inférences à partir d’un modèle basé sur une grande quantité de données.

![](assets/decision_tree_parts.png)

<table id="table_FCC5D63EF8A843D79B2338BD951025EA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Barre d’outils et menus</b> </p> <p>La barre d'outils comprend des boutons et des commandes de menu pour l'arbre de décision, y compris des fonctions permettant de définir la casse positive et d'ajouter des listes d'entrée. </p> <p>Comme pour d’autres visualisations, la zone <span class="uicontrol"> Elément</span> permet de faire glisser et de déposer la Dimension et les éléments, bien que vous puissiez également faire glisser directement depuis le volet Rechercher. </p> <p>Pour plus d'informations, voir <a href="../../../../home/c-get-started/c-analysis-vis/c-decision-trees/c-decision-trees-menu.md#concept-bfc4e80651a243d3966cc770b205606c"> Options de l'arbre de décision</a>. </p> </td> 
   <td colname="col2"> <p><b>Liste des entrées</b> </p> <p>Cette zone affiche les entrées dans le modèle d'arborescence. Ils sont codés par couleur pour correspondre aux noeuds de la zone Affichage en arborescence. </p> <p>Le fait de cliquer avec le bouton droit sur une entrée permet de supprimer l'entrée du modèle et de la réinitialiser. </p> <p>Si vous placez le pointeur de la souris sur un noeud d’arborescence, les conditions de fractionnement le long de la branche vers ce noeud et la prévision à ce noeud avec sa valeur de fiabilité s’affichent. </p> </td> 
   <td colname="col3"> <p><b>Affichage en arborescence</b> </p> <p>Cette zone affiche le modèle de l’arborescence avec les noeuds feuille codés par couleur en fonction de sa prédiction : vert pour une prévision vraie du cas positif et rouge pour une prévision fausse. </p> <p>Les noeuds fractionnés sont codés par couleur sur les entrées correspondant à leur condition de sélection. Le survol d’un noeud affiche des informations sur la division et développe la liste des entrées pour afficher les points de division le long de la branche et la distribution du jeu de formations. </p> <p>Les noeuds situés en dessous d’un seuil ne s’affichent pas par défaut. Cliquez sur un noeud extensible (indiqué par un symbole +) pour explorer une branche. Cliquez sur le noeud racine pour revenir à l'affichage complet de l'arborescence. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_E800327344194A6DBF37F273D8462E2A"></a> -->
