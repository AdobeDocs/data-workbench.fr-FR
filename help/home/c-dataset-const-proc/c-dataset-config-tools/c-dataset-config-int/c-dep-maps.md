---
description: Les cartes de dépendance vous permettent de visualiser et de gérer la configuration des composants de votre profil.
solution: Analytics
title: Cartes de dépendance
topic: Data workbench
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Cartes de dépendance{#dependency-maps}

Les cartes de dépendance vous permettent de visualiser et de gérer la configuration des composants de votre profil.

* **Composants de jeux de données :** Journalisez les sources, les filtres, les champs, les transformations et les dimensions étendues définis dans les fichiers [!DNL Log Processing.cfg], [!DNL Transformation.cfg]et [!DNL dataset include] du jeu de données.

* **Composants du modèle de requête :** Mesures, dimensions et filtres définis dans les dossiers Dimensions, Mesures et Filtres.
* **Espaces de travail et visualisations :** Espaces de travail, rapports, options de menu et calques globe.

Pour plus d’informations sur l’utilisation des composants de modèles de requête, des espaces de travail et des visualisations dans les mappages de dépendances, consultez le Guide *de l’utilisateur des outils de* données.

Les composants de profil sont représentés par des points de couleur (noeuds) dans la carte. Les lignes qui connectent les noeuds décrivent les dépendances, c&#39;est-à-dire la façon dont les composants se connectent les uns aux autres. Une ligne entre deux noeuds signifie qu’une sortie du noeud à gauche est une entrée du noeud à droite, c’est-à-dire que le noeud à droite dépend du noeud à gauche.

## Affichage des composants de jeux de données {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Cliquez avec le bouton droit de la souris dans le mappage des dépendances, puis cliquez sur **[!UICONTROL Display]**.
1. Sélectionner **[!UICONTROL Dataset]**. Un X apparaît à gauche de [!DNL Dataset].

Pour plus d’informations sur les autres options d’affichage, consultez le Guide *de l’utilisateur des outils de* données.

La figure suivante présente un mappage de dépendances dont les noeuds représentent les sources de journaux, les champs, les transformations et les dimensions étendues d’un jeu de données.

![](assets/vis_DependencyMap.png)

* Un noeud jaune-vert représente une ou plusieurs sources de journal ou un filtre défini dans le jeu de données. Un noeud pour une source de journal s’affiche toujours plus à gauche dans le mappage.
* Un noeud gris représente un champ répertorié dans le paramètre Champs dans un [!DNL Log Processing.cfg] fichier ou un [!DNL Log Processing Include]fichier.

* Un noeud bleu représente une transformation.
* Un noeud vert représente une dimension étendue.

>[!NOTE]
>
>Si votre jeu de données comporte une source de journal unique, le mappage affiche Source du journal : Nom *de la source du* journal. Si votre jeu de données comporte plusieurs sources de journal, le mappage affiche le *nombre* de sources de journal, où nombre correspond au nombre de sources de journal. Par exemple, si votre jeu de données contient trois sources de journal, votre mappage affiche 3 sources de journal.

Si vous ne pouvez pas voir tous les noeuds de la carte, vous pouvez déplacer la carte ou effectuer un zoom avant ou arrière pour afficher la carte entière ou pour vous concentrer sur une section spécifique. Pour plus d’informations sur le zoom, voir le chapitre Utilisation des visualisations du Guide *de l’utilisateur des outils de* données.

Lorsque vous cliquez sur un noeud, tous les noeuds qui dépendent de ce noeud et tous les noeuds dont dépend ce noeud sont mis en surbrillance et leurs noms s’affichent.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Un chemin en surbrillance dans un mappage de dépendance ne constitue pas une sélection.

Lorsque vous cliquez avec le bouton droit sur un noeud, vous pouvez voir les informations d’identification de chaque composant affichées sur la carte et choisir les options de menu qui vous permettent d’afficher plus de détails sur le composant ou de le modifier. En outre, vous pouvez effectuer des recherches de texte et afficher des informations sur les performances des transformations et des dimensions étendues.

Pour plus d’informations sur ces fonctions pour les mappages de dépendances, voir le chapitre Interfaces d’administration du Guide *de l’utilisateur des outils de* données.
