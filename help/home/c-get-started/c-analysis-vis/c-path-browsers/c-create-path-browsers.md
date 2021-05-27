---
description: Vous pouvez créer un navigateur de chemins d’accès à partir d’un graphique, d’un tableau ou d’une cartographie des processus.
title: Création de navigateurs de chemins d’accès
uuid: 84a5e587-fb02-461b-aec8-1b6ad473ebc3
exl-id: 9fa11b84-da73-447a-8b10-7eab381e3f66
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Création de navigateurs de chemins d’accès{#creating-path-browsers}

Vous pouvez créer un navigateur de chemins d’accès à partir d’un graphique, d’un tableau ou d’une cartographie des processus.

**Pour créer un navigateur de chemins d’accès à partir d’un graphique ou d’un tableau**

1. Ajoutez un navigateur de chemins d’accès à votre espace de travail. La visualisation est vide, à l’exception du libellé (Séquence de...) dans le coin supérieur gauche.
1. Ouvrez un graphique ou un tableau présentant la dimension dont vous souhaitez afficher les éléments dans l’explorateur de chemins d’accès. Par exemple, si vous utilisez des données de site web, ouvrez un graphique ou un tableau de page et identifiez la page que vous souhaitez définir comme racine.
1. Appuyez sur Ctrl+Alt et faites glisser l’élément souhaité vers l’explorateur de chemins d’accès. Le libellé dans le coin supérieur gauche de l’explorateur de chemins d’accès change pour refléter la dimension de base de l’élément que vous faites glisser vers l’explorateur de chemins d’accès.

>[!NOTE]
>
>Le fait de faire glisser un élément vers un navigateur de chemins d’accès peut modifier la dimension de base associée à l’explorateur de chemins d’accès, mais cela ne modifie pas la dimension de niveau, la dimension de groupe ou la mesure. Par conséquent, vous devez être prudent lors du choix d’une dimension de base qui est logique lorsqu’elle est utilisée avec la dimension de niveau, la dimension de groupe et la mesure du navigateur de chemins d’accès. Pour modifier la dimension de niveau, la dimension de groupe ou la mesure, vous devez modifier le fichier [!DNL *.vw] de l’explorateur de chemins d’accès dans un éditeur de texte tel que le Bloc-notes. Voir [Configuration des navigateurs de chemins](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

**Pour créer un navigateur de chemins d’accès à partir d’une cartographie des processus**

>[!NOTE]
>
>Un navigateur de chemins d’accès créé à partir d’une cartographie des processus affiche uniquement les éléments affichés sur la cartographie des processus. Les autres éléments de la dimension de base ne sont pas affichés.

1. Création d’une cartographie des processus. Voir [Création de mappages de processus](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-create-proc-maps.md#concept-daf5b14dae7a442191611b1b9c1122bf).
1. Faites glisser l’élément souhaité de la cartographie des processus vers l’explorateur de chemins d’accès. L’élément devient la racine de l’explorateur de chemins d’accès.

>[!NOTE]
>
>Lorsque vous créez un navigateur de chemins d’accès à partir d’une cartographie des processus, l’explorateur de chemins d’accès ignore les éléments de la dimension de niveau sans éléments de dimension de base associés. Lorsque vous faites glisser un noeud d’une cartographie des processus sur un navigateur de chemins d’accès, la dimension de base de l’explorateur de chemins d’accès (appelée Map) est définie par la cartographie des processus et ses éléments sont limités aux éléments de la cartographie des processus. Par conséquent, certains éléments de la dimension de niveau de l’explorateur de chemins d’accès n’ont pas d’éléments de dimension de base associés et ne sont pas représentés dans l’explorateur de chemins d’accès.
