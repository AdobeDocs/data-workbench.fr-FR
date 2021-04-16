---
description: Vous pouvez créer un navigateur de chemins à partir d’un graphique, d’un tableau ou d’une carte de processus.
title: Création de navigateurs de chemins d’accès
uuid: 84a5e587-fb02-461b-aec8-1b6ad473ebc3
exl-id: 9fa11b84-da73-447a-8b10-7eab381e3f66
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Création de navigateurs de chemins d’accès{#creating-path-browsers}

Vous pouvez créer un navigateur de chemins à partir d’un graphique, d’un tableau ou d’une carte de processus.

**Pour créer un navigateur de chemins d’accès à partir d’un graphique ou d’un tableau**

1. Ajoutez un navigateur de chemins d’accès à votre espace de travail. La visualisation est vide, à l’exception de l’étiquette (Séquence de...) dans le coin supérieur gauche.
1. Ouvrez un graphique ou un tableau présentant la dimension dont vous souhaitez afficher les éléments dans le navigateur de chemins. Par exemple, si vous travaillez sur des données de site Web, ouvrez un graphique ou un tableau de page et identifiez la page que vous souhaitez définir comme racine.
1. Appuyez sur Ctrl+Alt et faites glisser l’élément souhaité vers le navigateur de chemins. Le libellé dans le coin supérieur gauche du navigateur de chemins change pour refléter la dimension de base dont vous faites glisser l’élément vers le navigateur de chemins.

>[!NOTE]
>
>Le fait de faire glisser un élément vers un navigateur de chemins peut modifier la dimension de base associée au navigateur de chemins, mais cela ne change pas la dimension de niveau, la dimension de groupe ou la mesure. Par conséquent, vous devez faire preuve de prudence dans le choix d’une dimension de base qui a du sens lorsqu’elle est utilisée avec la dimension de niveau, la dimension de groupe et la mesure du navigateur de chemins. Pour modifier la dimension de niveau, la dimension de groupe ou la mesure, vous devez modifier le fichier [!DNL *.vw] du navigateur de chemins d’accès dans un éditeur de texte tel que le Bloc-notes. Voir [Configuration des navigateurs de chemin](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

**Pour créer un navigateur de chemins à partir d’un mappage de processus**

>[!NOTE]
>
>Un navigateur de chemins créé à partir d’une carte de processus affiche uniquement les éléments affichés sur la carte de processus. Les autres éléments de la dimension de base ne s’affichent pas.

1. Création d’une cartographie des processus. Voir [Création de zones de processus](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-create-proc-maps.md#concept-daf5b14dae7a442191611b1b9c1122bf).
1. Faites glisser l’élément de votre choix de la mise en correspondance des processus vers le navigateur de chemins. L’élément devient la racine du navigateur de chemins.

>[!NOTE]
>
>Lorsque vous créez un navigateur de chemins à partir d’une carte de processus, le navigateur de chemins ignore les éléments de la dimension de niveau sans éléments de dimension de base associés. Lorsque vous faites glisser un noeud d’un mappage de processus sur un navigateur de chemins, la dimension de base du navigateur de chemins (appelée Carte) est définie par le mappage de processus et ses éléments sont limités aux éléments du mappage de processus. Par conséquent, certains éléments de la dimension de niveau du navigateur de chemins n’ont pas d’éléments de dimension de base associés et ne sont pas représentés dans le navigateur de chemins.
