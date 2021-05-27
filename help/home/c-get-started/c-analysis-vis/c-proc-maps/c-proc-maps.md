---
description: Les cartographies des processus permettent d'analyser le flux d'activité entre les éléments d'une dimension.
title: Cartographie des processus
uuid: f1db41a9-400e-467a-ba59-39831fb166af
exl-id: 019cee7b-a704-4b47-84c6-d3ddc277c43e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 0%

---

# Cartographie des processus{#process-map}

Les cartographies des processus permettent d&#39;analyser le flux d&#39;activité entre les éléments d&#39;une dimension.

Vous créez des mappages de processus en faisant glisser les éléments d’une dimension sur une carte vierge à deux dimensions (2D) ou à trois dimensions (3D). Les éléments deviennent des noeuds sur la carte. Les noeuds sont des cercles dans les cartes de processus 2D et les barres dans les cartes de processus 3D.

![](assets/vis_2DProcessMap.png)

![](assets/vis_3DProcessMap.png)

>[!NOTE]
>
>Une cartographie des processus obtient son nom à partir de son utilisation dans l’analyse du flux d’activité entre les étapes d’un processus. Dans ce type d’analyse, chaque élément de la carte représente une étape du processus.

Contrairement aux navigateurs de chemins d’accès, les mappages de processus peuvent afficher autant d’éléments que nécessaire pour votre analyse. Vous choisissez les éléments qui vous intéressent et faites-les glisser sur la carte. Contrairement aux navigateurs de chemins d’accès, les mappages de processus décrivent le flux d’activité dans les deux directions entre un élément et un ou plusieurs autres éléments.

>[!NOTE]
>
>Pour que ces cartes fonctionnent le mieux, vous devez ouvrir une légende en couleur dans l’espace de travail. Pour plus d’informations sur l’utilisation des légendes de couleur avec les mappages de processus, voir [Activation des liens de couleur](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-act-color-lnks.md#concept-2c9b9f67f2bd4cd7a5431fa21c094edc). Pour plus d’informations sur les légendes de couleur, voir [Légendes de couleur](../../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

Chaque cartographie des processus est associée à une dimension de base, une dimension de groupe, une dimension de niveau et une mesure, qui fournissent des clés pour interpréter les données affichées dans la cartographie des processus.

Les paramètres par défaut des dimensions et des mesures d’une cartographie des processus dépendent de l’application de Data Workbench que vous utilisez. Pour plus d’informations sur les dimensions et les mesures disponibles pour vos mappages de processus, consultez le guide de l’application pour votre application de Data Workbench.

* **Dimension de base :**  lorsque vous faites glisser un élément sur une cartographie des processus, vous faites glisser et déposez un élément de la dimension de base.
* **Dimension de niveau :** chaque dimension de votre jeu de données est associée à une dimension de niveau (également appelée parent). La dimension de niveau de votre cartographie des processus doit être identique à la dimension de niveau (ou parent) de la dimension de base de votre cartographie des processus. Par exemple, si vous faites glisser une page (un élément de la dimension Page) vers la carte, la dimension de niveau correspondante sera Page vue.
* **Dimension de groupe :**  la dimension de groupe détermine la manière dont les éléments de la dimension de niveau sont regroupés pour former les connexions entre les noeuds. Pour les cartographies des processus, la dimension de groupe est importante pour trois raisons principales :

   * Une connexion entre deux noeuds ne peut pas couvrir plusieurs éléments d’une dimension de groupe. Pour comprendre cela, prenez un exemple d’utilisation des données web. Supposons que les dimensions de base, de niveau et de groupe de votre cartographie des processus soient Page, Page vue et Session, respectivement. Une connexion de la page A à la page B vous indique qu’au cours d’une seule session, une page vue de la page A s’est produite avant une page vue de la page B sans que d’autres pages (noeuds) ne soient consultées entre elles sur la carte. Notez que d’autres pages du site ont peut-être été vues entre les pages A et B au cours de la même session, mais que ces pages ne sont pas affichées sur cette carte.
   * Une connexion entre deux noeuds peut représenter plusieurs éléments de la dimension de groupe. Par exemple, il peut y avoir plusieurs sessions au cours desquelles une page vue de la page A s’est produite avant une page vue de la page B. Par conséquent, la connexion entre la page A et la page B représente toutes les sessions individuelles au cours desquelles une page vue de la page A s’est produite avant une page vue de la page B sans que d’autres pages (noeuds) ne soient consultées entre elles sur la carte.
   * Lorsque vous effectuez une sélection en fonction d’un noeud dans une cartographie des processus, vous sélectionnez tous les éléments de la dimension de groupe qui ont impliqué ce noeud. Voir [Réalisation de sélections dans les visualisations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746). Pour plus d’informations sur les sélections, voir [Réalisation de sélections dans les visualisations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

* **Mesure :** la taille du noeud pour un élément donné est proportionnelle à la valeur de la mesure pour cet élément. Les noeuds plus grands indiquent des valeurs de mesure plus élevées que les noeuds plus petits.

Par exemple, si vous utilisez l’application [!DNL Site] ou HBX, vous pouvez faire glisser, par défaut, des éléments de la dimension Page sur la cartographie des processus. La taille de chaque noeud est liée à la quantité de sessions (définie par la mesure Sessions) au cours desquelles cette page a été consultée.

>[!NOTE]
>
>Vous pouvez modifier les dimensions ou les mesures par défaut d’une cartographie des processus. Pour connaître les étapes de configuration d’une cartographie des processus, voir [Configuration des cartographies des processus](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).
