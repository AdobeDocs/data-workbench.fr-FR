---
description: Les cartes de dépendance vous permettent de visualiser et de gérer la configuration des composants de votre profil.
title: Tables de dépendances
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
exl-id: 4618c735-f507-4abc-a4b4-d52a37c64c60,733407ca-3326-406a-a642-a3ea3d3f6b8b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 1%

---

# Tables de dépendances{#dependency-maps}

Les cartes de dépendance vous permettent de visualiser et de gérer la configuration des composants de votre profil.

* **Composants d’un jeu de données : sources de** journaux, filtres, champs, transformations et dimensions étendues définis dans les  [!DNL Log Processing.cfg]fichiers,  [!DNL Transformation.cfg]et  [!DNL dataset include] fichiers de votre jeu de données.

* **Composants du modèle de requête :** Mesures, dimensions et filtres définis dans les dossiers Dimensions, Mesures et Filtres.
* **Espaces de travail et visualisations:** Espaces de travail, rapports, options de menu et calques globe.

Pour plus d&#39;informations sur l&#39;utilisation des composants de modèle de requête, des espaces de travail et des visualisations dans les mappages de dépendance, consultez le *Guide de l&#39;utilisateur Data Workbench*.

Les composants de profil sont représentés par des points de couleur (noeuds) dans la carte. Les lignes connectant les noeuds dépeignent les dépendances, c&#39;est-à-dire la façon dont les composants se connectent les uns aux autres. Une ligne entre deux noeuds signifie qu’une sortie du noeud à gauche est une entrée du noeud à droite, c’est-à-dire que le noeud à droite dépend du noeud à gauche.

## Affichage des composants de jeux de données {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Cliquez avec le bouton droit de la souris dans le mappage des dépendances, puis cliquez sur **[!UICONTROL Display]**.
1. Sélectionner **[!UICONTROL Dataset]**. Un X apparaît à gauche de [!DNL Dataset].

Pour plus d&#39;informations sur les autres options d&#39;affichage, consultez le *Guide de l&#39;utilisateur Data Workbench*.

La figure suivante illustre un mappage de dépendances dont les noeuds représentent les sources de journaux, les champs, les transformations et les dimensions étendues d’un jeu de données.

![](assets/vis_DependencyMap.png)

* Un noeud jaune-vert représente une ou plusieurs sources de journal ou un filtre défini dans le jeu de données. Un noeud pour une source de journal s’affiche toujours le plus à gauche dans la carte.
* Un noeud gris représente un champ répertorié dans le paramètre Fields d’un fichier [!DNL Log Processing.cfg] ou [!DNL Log Processing Include].

* Un noeud bleu représente une transformation.
* Un noeud vert représente une dimension étendue.

>[!NOTE]
>
>Si votre jeu de données possède une source de journal unique, la carte affiche Source de journal : *nom source du journal*. Si votre jeu de données comporte plusieurs sources de journal, la carte affiche *nombre* Sources de journal, où nombre correspond au nombre de sources de journal. Par exemple, si votre jeu de données contient trois sources de journaux, votre mappage affiche 3 sources de journaux.

Si vous ne pouvez pas afficher tous les noeuds de la carte, vous pouvez déplacer la carte ou effectuer un zoom avant ou arrière pour afficher la carte entière ou pour vous concentrer sur une section particulière. Pour plus d&#39;informations sur le zoom, consultez le chapitre Utilisation des visualisations du *Guide de l&#39;utilisateur Data Workbench*.

Lorsque vous cliquez sur un noeud, tous les noeuds qui dépendent de ce noeud et tous les noeuds dont dépend ce noeud sont mis en surbrillance et leurs noms s’affichent.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Un chemin surligné dans un mappage de dépendance ne constitue pas une sélection.

Lorsque vous cliquez avec le bouton droit sur un noeud, vous pouvez voir les informations d&#39;identification de chaque composant affichées sur la carte et choisir les options de menu qui vous permettent de vue plus de détails sur le composant ou de modifier le composant. En outre, vous pouvez effectuer des recherches de texte et afficher des informations de performances pour les transformations et les dimensions étendues.

Pour plus d&#39;informations sur ces fonctions pour les mappages de dépendance, consultez le chapitre Interfaces d&#39;administration du *Guide de l&#39;utilisateur Data Workbench*.
