---
description: Informations conceptuelles sur les composants de jeux de données.
title: Composants du jeu de données
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 1%

---

# Composants du jeu de données{#dataset-components}

Informations conceptuelles sur les composants de jeux de données.

La figure suivante présente un mappage de dépendance dont les noeuds représentent les sources de journaux, les champs, les transformations et les dimensions étendues d’un jeu de données.

![](assets/vis_DependencyMap.png)

* Un noeud jaune-vert représente une ou plusieurs sources de journal ou un filtre (tel qu’une condition d’entrée du journal) défini dans le jeu de données.

   * Un noeud pour une source de journal s’affiche toujours le plus à gauche dans la carte. Si votre jeu de données comporte une seule source de journal, la carte affiche Source du journal : *nom de la source du journal*. Si votre jeu de données comporte plusieurs sources de journal, la carte affiche *nombre* Sources de journal, où nombre correspond au nombre de sources de journal. Par exemple, si votre jeu de données contient trois sources de journal, votre carte affiche 3 sources de journal.

   * Le mappage affiche un noeud Condition d’entrée du journal pour chaque fichier [!DNL log processing dataset include], mais un seul noeud Condition d’entrée du journal pour la transformation (s’il est défini dans le fichier [!DNL Transformation.cfg]). Si la condition d’entrée du journal est vide, elle ne s’affiche pas sur la carte.

* Un noeud gris représente un champ répertorié dans le paramètre Champs d’un fichier [!DNL Log Processing.cfg] ou [!DNL Log Processing include].

* Un noeud bleu représente une transformation.
* Un noeud vert représente une dimension étendue.

>[!NOTE]
>
>Si le dossier du jeu de données de votre profil contient le fichier [!DNL Insight Transform.cfg], la carte des dépendances affiche les sources des journaux, les transformations et les exportateurs définis pour utilisation avec Transform. Pour plus d’informations sur Transform, consultez le *Guide de configuration des jeux de données*.

Lorsque vous activez l’option d’affichage Inclure [!DNL File Blocks] , le mappage affiche un seul noeud bleu pour toutes les transformations définies dans un fichier de configuration de jeu de données et un seul noeud vert pour toutes les dimensions étendues définies dans un fichier de configuration de jeu de données. Pour plus d’informations sur cette option d’affichage, voir [Utilisation de blocs de fichiers](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
