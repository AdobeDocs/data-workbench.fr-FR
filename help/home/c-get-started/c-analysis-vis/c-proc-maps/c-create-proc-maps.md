---
description: Vous pouvez créer des mappages de processus 2D et 3D en faisant glisser des éléments des graphiques à barres, des tableaux et des vues de hiérarchie sur une carte vide.
solution: Analytics
title: Création d’une carte de processus
topic: Data workbench
uuid: dbcde637-0411-4296-99ca-5510e0285e4b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Création d’une carte de processus{#create-a-process-map}

Vous pouvez créer des mappages de processus 2D et 3D en faisant glisser des éléments des graphiques à barres, des tableaux et des vues de hiérarchie sur une carte vide.

Les éléments que vous pouvez ajouter doivent être des éléments de la dimension de base du mappage de processus. Vous pouvez également faire glisser et déposer des noeuds d’une carte de processus vers une autre tant que les cartes utilisent la même dimension de base. En outre, il est possible de zoomer ou de déplacer la carte entière pour se concentrer sur un noeud particulier ou de la modifier en d’autres types de visualisation. Voir [Zoom dans les visualisations](../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

**Pour ajouter des éléments à une carte de processus à l’aide d’un tableau ou d’un graphique à barres**

* Dans un tableau ou un graphique à barres ayant la même dimension de base que la carte de processus, appuyez sur Ctrl+Alt pendant que vous cliquez et faites glisser des éléments individuels vers la carte de processus. Le curseur de la souris affiche le mot &quot;Non&quot; jusqu’à ce que votre souris atteigne le mappage de processus.

   >[!NOTE]
   >
   >Les éléments que vous pouvez ajouter doivent être des éléments de la dimension de base du mappage de processus.

   ![](assets/vis_2DProcessMap_addPages.png)

**Pour ajouter des éléments à un mappage de processus à l’aide d’une vue de hiérarchie**

>[!NOTE]
>
>Adobe recommande d’ajouter des noeuds du niveau supérieur de la hiérarchie que vous analysez.

1. Dans un tableau ou un graphique à barres ayant la même dimension de base que la carte de processus, cliquez avec le bouton droit de la souris sur un élément ou sur l’étiquette de la dimension de base, puis cliquez sur **[!UICONTROL Hierarchy View]**.
1. Appuyez sur Ctrl+Alt pendant que vous cliquez et faites glisser des éléments vers la carte de processus. Le curseur de votre souris affiche le mot &quot;Non&quot; jusqu’à ce que votre souris atteigne la carte.

   >[!NOTE]
   >
   >Les éléments que vous pouvez ajouter doivent être des éléments de la dimension de base du mappage de processus.

   Le fait de faire glisser un seul élément sur un mappage de processus crée un noeud de mappage pour cet élément uniquement, mais si vous sélectionnez plusieurs éléments (un groupe) ou un dossier contenant plusieurs éléments, le fait de faire glisser un noeud de la hiérarchie crée un noeud unique pour ce groupe ou ce dossier. Par exemple, si vous travaillez avec des données de site Web, faire glisser un dossier nommé [!DNL site.com/cgi-bin] sur un mappage crée un noeud appelé [!DNL site.com/cgi-bin/*], qui représente toutes les pages et tous les répertoires qui sont des enfants de ce dossier.

Pour plus d&#39;informations sur les vues de hiérarchie des pages, voir [Application des vues](../../../../home/c-get-started/c-analysis-vis/c-tables/c-hier-vews.md#concept-b461183424a841eb94f8143a0eaf9bff)hiérarchiques.

**Pour ajouter des noeuds à une carte de processus à partir d’une autre carte de processus**

>[!NOTE]
>
>Les mappages de processus doivent avoir la même dimension de base.

* Copiez un noeud du premier vers le deuxième mappage de processus à l’aide des méthodes suivantes :

   * Pour copier des noeuds individuels, cliquez sur chaque noeud et faites-le glisser vers la deuxième carte de processus.
   * Pour copier plusieurs noeuds, cliquez tout en maintenant la touche Ctrl enfoncée et faites glisser la souris pour créer une zone autour des noeuds à copier, puis cliquez et faites glisser les noeuds en surbrillance vers la deuxième carte de processus. Tous les noeuds mis en surbrillance sont copiés dans le second mappage de processus.
