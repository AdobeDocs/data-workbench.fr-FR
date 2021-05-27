---
description: Vous pouvez créer des mappages de processus 2D et 3D en faisant glisser des éléments à partir des graphiques en barres, des tableaux et des vues hiérarchiques sur une carte vierge.
title: Création d’une cartographie des processus
uuid: dbcde637-0411-4296-99ca-5510e0285e4b
exl-id: 2e417a8e-5b1c-4dce-9e4e-ac7ed044564c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 1%

---

# Création d’une cartographie des processus{#create-a-process-map}

Vous pouvez créer des mappages de processus 2D et 3D en faisant glisser des éléments à partir des graphiques en barres, des tableaux et des vues hiérarchiques sur une carte vierge.

Les éléments que vous pouvez ajouter doivent être des éléments de la dimension de base de la cartographie des processus. Vous pouvez également faire glisser et déposer des noeuds d’une cartographie des processus vers une autre tant que les cartes utilisent la même dimension de base. En outre, la carte entière peut être agrandie ou déplacée pour se concentrer sur un noeud particulier, ou elle peut être modifiée sur d’autres types de visualisation. Voir [Zoom dans les visualisations](../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

**Pour ajouter des éléments à une cartographie des processus à l’aide d’un tableau ou d’un graphique à barres**

* Dans n’importe quel tableau ou graphique à barres avec la même dimension de base que la cartographie des processus, appuyez sur Ctrl+Alt tout en cliquant sur et en faisant glisser des éléments individuels vers la cartographie des processus. Le curseur de la souris affiche le mot &quot;Non&quot; jusqu’à ce que la souris atteigne la cartographie des processus.

   >[!NOTE]
   >
   >Les éléments que vous pouvez ajouter doivent être des éléments de la dimension de base de la cartographie des processus.

   ![](assets/vis_2DProcessMap_addPages.png)

**Pour ajouter des éléments à une cartographie des processus à l’aide d’une vue hiérarchique**

>[!NOTE]
>
>Adobe recommande d’ajouter des noeuds du niveau supérieur de la hiérarchie que vous analysez.

1. Dans n’importe quel tableau ou graphique à barres ayant la même dimension de base que la cartographie des processus, cliquez avec le bouton droit de la souris sur un élément ou le libellé de la dimension de base, puis cliquez sur **[!UICONTROL Hierarchy View]**.
1. Appuyez sur Ctrl+Alt lorsque vous cliquez et faites glisser des éléments vers la cartographie des processus. Le curseur de la souris affiche le mot &quot;Non&quot; jusqu’à ce que la souris atteigne la carte.

   >[!NOTE]
   >
   >Les éléments que vous pouvez ajouter doivent être des éléments de la dimension de base de la cartographie des processus.

   Le fait de faire glisser un seul élément sur une cartographie des processus crée un noeud map pour cet élément uniquement, mais si vous sélectionnez plusieurs éléments (un groupe) ou un dossier contenant plusieurs éléments, le fait de faire glisser à partir de la hiérarchie crée un noeud unique pour ce groupe ou ce dossier. Par exemple, si vous utilisez des données de site web, faire glisser un dossier nommé [!DNL site.com/cgi-bin] sur une carte crée un noeud appelé [!DNL site.com/cgi-bin/*], qui représente toutes les pages et tous les répertoires qui sont des enfants de ce dossier.

Pour plus d’informations sur les vues de hiérarchie de pages, voir [Application des vues de hiérarchie](../../../../home/c-get-started/c-analysis-vis/c-tables/c-hier-vews.md#concept-b461183424a841eb94f8143a0eaf9bff).

**Pour ajouter des noeuds à une cartographie des processus à partir d’une autre cartographie des processus**

>[!NOTE]
>
>Les mappages de processus doivent avoir la même dimension de base.

* Copiez un noeud du premier vers le deuxième mappage de processus à l’aide des méthodes suivantes :

   * Pour copier des noeuds individuels, cliquez sur chaque noeud et faites-le glisser vers la deuxième carte de processus.
   * Pour copier plusieurs noeuds, maintenez la touche Ctrl enfoncée tout en cliquant et faites glisser le curseur pour créer une zone autour des noeuds à copier, puis cliquez sur les noeuds mis en surbrillance et faites-les glisser vers la deuxième cartographie des processus. Tous les noeuds mis en surbrillance sont copiés dans la deuxième cartographie des processus.
