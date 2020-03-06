---
description: Informations conceptuelles sur les composants de jeux de données.
solution: Analytics
title: Composants de jeux de données
topic: Data workbench
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Composants de jeux de données{#dataset-components}

Informations conceptuelles sur les composants de jeux de données.

La figure suivante illustre un mappage de dépendances dont les noeuds représentent les sources de journaux, les champs, les transformations et les dimensions étendues d’un jeu de données.

![](assets/vis_DependencyMap.png)

* Un noeud jaune-vert représente une ou plusieurs sources de journal ou un filtre (tel qu’une condition d’entrée dans le journal) défini dans le jeu de données.

   * Un noeud pour une source de journal s’affiche toujours plus à gauche dans le mappage. Si votre jeu de données comporte une source de journal unique, le mappage affiche Source du journal : Nom *de la source du* journal. Si votre jeu de données comporte plusieurs sources de journal, le mappage affiche le *nombre* de sources de journal, où nombre correspond au nombre de sources de journal. Par exemple, si votre jeu de données contient trois sources de journal, votre mappage affiche 3 sources de journal.

   * Le mappage affiche un noeud de condition d’entrée de journal pour chaque [!DNL log processing dataset include] fichier, mais un seul noeud de condition d’entrée de journal pour la transformation (s’il est défini dans le [!DNL Transformation.cfg] fichier). Si la condition d’entrée du journal est vide, elle ne s’affiche pas sur le mappage.

* Un noeud gris représente un champ répertorié dans le paramètre Champs d’un [!DNL Log Processing.cfg] fichier ou d’un [!DNL Log Processing include] fichier.

* Un noeud bleu représente une transformation.
* Un noeud vert représente une dimension étendue.

>[!NOTE]
>
>Si le dossier Dataset de votre profil contient le fichier [!DNL Insight Transform.cfg], le mappage des dépendances affiche les sources, les transformations et les exportateurs de journaux définis pour l’utilisation avec Transform. Pour plus d’informations sur Transform, consultez le Guide *de configuration des jeux de* données.

Lorsque vous activez l’option Inclure [!DNL File Blocks] l’affichage, le mappage affiche un noeud bleu unique pour toutes les transformations définies dans un fichier de configuration de jeu de données et un noeud vert unique pour toutes les dimensions étendues définies dans un fichier de configuration de jeu de données. Pour plus d’informations sur cette option d’affichage, voir [Utilisation de blocs](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc)de fichiers.
