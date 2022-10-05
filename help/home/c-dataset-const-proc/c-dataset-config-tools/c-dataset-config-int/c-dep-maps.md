---
description: Les mappages de dépendances vous permettent de visualiser et de gérer la configuration des composants de votre profil.
title: Tables de dépendances
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
exl-id: 4618c735-f507-4abc-a4b4-d52a37c64c60,733407ca-3326-406a-a642-a3ea3d3f6b8b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 0%

---

# Tables de dépendances{#dependency-maps}

{{eol}}

Les mappages de dépendances vous permettent de visualiser et de gérer la configuration des composants de votre profil.

* **Composants du jeu de données :** Sources de journalisation, filtres, champs, transformations et dimensions étendues définies dans le jeu de données [!DNL Log Processing.cfg], [!DNL Transformation.cfg], et [!DNL dataset include] fichiers .

* **Composants de modèle de requête :** Mesures, dimensions et filtres définis dans les dossiers Dimensions, Mesures et Filtres .
* **Espaces de travail et visualisations :** Espaces de travail, rapports, options de menu et calques de globe.

Pour plus d’informations sur l’utilisation des composants de modèle de requête, des espaces de travail et des visualisations dans les mappages de dépendance, voir la section *Guide de l’utilisateur de Data Workbench*.

Les composants de profil sont représentés par des points de couleur (noeuds) dans la carte. Les lignes qui connectent les noeuds décrivent les dépendances, c&#39;est-à-dire la façon dont les composants se relient les uns aux autres. Une ligne entre deux noeuds signifie qu’une sortie du noeud à gauche est une entrée du noeud à droite, c’est-à-dire que le noeud à droite dépend du noeud à gauche.

## Affichage des composants de jeu de données {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Cliquez avec le bouton droit dans la carte des dépendances, puis cliquez sur **[!UICONTROL Display]**.
1. Choisir **[!UICONTROL Dataset]**. Un X apparaît à gauche de [!DNL Dataset].

Pour plus d’informations sur les autres options d’affichage, voir *Guide de l’utilisateur de Data Workbench*.

La figure suivante présente un mappage de dépendance dont les noeuds représentent les sources de journaux, les champs, les transformations et les dimensions étendues d’un jeu de données.

![](assets/vis_DependencyMap.png)

* Un noeud jaune-vert représente une ou plusieurs sources de journal ou un filtre défini dans le jeu de données. Un noeud pour une source de journal s’affiche toujours le plus à gauche dans la carte.
* Un noeud gris représente un champ répertorié dans le paramètre Champs d’un [!DNL Log Processing.cfg] ou [!DNL Log Processing Include]fichier .

* Un noeud bleu représente une transformation.
* Un noeud vert représente une dimension étendue.

>[!NOTE]
>
>Si votre jeu de données comporte une seule source de journal, la carte affiche Source du journal : *nom de la source du journal*. Si votre jeu de données comporte plusieurs sources de journal, la carte s’affiche. *nombre* Sources de journal, où nombre correspond au nombre de sources de journal. Par exemple, si votre jeu de données contient trois sources de journal, votre carte affiche 3 sources de journal.

Si vous ne pouvez pas voir tous les noeuds de la carte, vous pouvez déplacer la carte ou effectuer un zoom avant ou arrière pour afficher la carte entière ou pour vous concentrer sur une section spécifique. Pour plus d’informations sur le zoom, reportez-vous au chapitre Utilisation des visualisations de la section *Guide de l’utilisateur de Data Workbench*.

Lorsque vous cliquez sur un noeud, tous les noeuds qui en dépendent, ainsi que tous les noeuds dont dépend ce noeud, sont mis en surbrillance et leurs noms s’affichent.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Un chemin en surbrillance dans un mappage de dépendance ne constitue pas une sélection.

Lorsque vous cliquez avec le bouton droit sur un noeud, vous pouvez voir les informations d’identification de chaque composant affiché sur la carte et choisir les options de menu qui vous permettent d’afficher plus de détails sur le composant ou de le modifier. En outre, vous pouvez effectuer des recherches de texte et afficher des informations de performances pour les transformations et les dimensions étendues.

Pour plus d’informations sur ces fonctions pour les mappages de dépendances, reportez-vous au chapitre Interfaces d’administration de la section *Guide de l’utilisateur de Data Workbench*.
