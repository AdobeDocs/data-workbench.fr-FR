---
description: Les mappages de processus vous permettent d’analyser le flux d’activité entre les éléments d’une dimension.
title: Cartographie des processus
uuid: f1db41a9-400e-467a-ba59-39831fb166af
exl-id: 019cee7b-a704-4b47-84c6-d3ddc277c43e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 0%

---

# Cartographie des processus{#process-map}

Les mappages de processus vous permettent d’analyser le flux d’activité entre les éléments d’une dimension.

Pour créer des mappages de processus, faites glisser les éléments d’une dimension sur un mappage bidimensionnel (2D) ou tridimensionnel (3D) vide. Les éléments deviennent des noeuds sur la carte. Les noeuds sont des cercles dans les cartes de processus 2D et les barres dans les cartes de processus 3D.

![](assets/vis_2DProcessMap.png)

![](assets/vis_3DProcessMap.png)

>[!NOTE]
>
>Une carte de processus tire son nom de son utilisation dans l’analyse du flux d’activité entre les étapes d’un processus. Dans ce type d’analyse, chaque élément de la carte représente une étape du processus.

Contrairement aux navigateurs de chemins, les mappages de processus peuvent afficher autant d’éléments que nécessaire pour votre analyse. Vous choisissez les éléments qui vous intéressent et faites-les glisser sur la carte. Contrairement aux navigateurs de chemins, les mappages de processus décrivent le flux d’activité dans les deux directions entre un élément et un ou plusieurs autres éléments.

>[!NOTE]
>
>Pour que ces cartes fonctionnent le mieux possible, vous devez ouvrir une légende de couleur dans l’espace de travail. Pour plus d’informations sur l’utilisation des légendes de couleur avec les mappages de processus, voir [Activation des liens de couleur](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-act-color-lnks.md#concept-2c9b9f67f2bd4cd7a5431fa21c094edc). Pour plus d’informations sur les légendes de couleur, voir [Légendes de couleur](../../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

Chaque mappage de processus est associé à une dimension de base, une dimension de groupe, une dimension de niveau et une mesure, qui fournissent des clés pour interpréter les données affichées dans le mappage de processus.

Les paramètres par défaut pour les dimensions et les mesures d’un mappage de processus dépendent de l’application de Data Workbench que vous utilisez. Pour plus d’informations sur les dimensions et les mesures disponibles pour vos mappages de processus, voir le guide de l’application pour votre application Data Workbench.

* **Dimension de base :** lorsque vous faites glisser un élément sur un mappage de processus, vous faites glisser et déposez un élément de la dimension de base.
* **Dimension de niveau :** chaque dimension de votre jeu de données est associée à une dimension de niveau (également appelée parent). La dimension de niveau de votre mappage de processus doit être identique à la dimension de niveau (ou parent) de la dimension de base de votre mappage de processus. Par exemple, si vous faites glisser une page (un élément de la dimension Page) vers le mappage, la dimension de niveau correspondante sera la Vue de page.
* **Dimension de groupe :** la dimension de groupe détermine comment les éléments de la dimension de niveau sont regroupés pour former les connexions entre noeuds. Pour les mappages de processus, la dimension de groupe est importante pour trois raisons principales :

   * Une connexion entre deux noeuds ne peut pas couvrir plus d’un élément d’une dimension de groupe. Pour comprendre cela, prenez un exemple d’utilisation des données Web. Supposons que les dimensions de base, de niveau et de groupe pour votre mappage de processus soient Page, Vue de page et Session, respectivement. Une connexion de la page A à la page B vous indique que, au cours d’une session unique, une vue de page de la page A s’est produite avant une vue de page de la page B sans vue de page intermédiaire d’autres pages (noeuds) sur la carte. Notez que des vues de page d&#39;autres pages du site se sont peut-être produites entre les vues de page des pages A et B au cours de la même session, mais ces pages ne sont pas affichées sur cette carte.
   * Une connexion entre deux noeuds peut représenter plusieurs éléments de la dimension de groupe. Par exemple, il peut y avoir plusieurs sessions au cours desquelles une vue de page de la page A a eu lieu avant une vue de page de la page B. Par conséquent, la connexion entre la page A et la page B représente toutes les sessions individuelles au cours desquelles une vue de page de la page A s&#39;est produite avant une vue de page de la page B sans vues de page intermédiaires d&#39;autres pages (noeuds) sur la carte.
   * Lorsque vous effectuez une sélection basée sur un noeud dans un mappage de processus, vous sélectionnez tous les éléments de la dimension de groupe qui impliquaient ce noeud. Voir [Sélections dans Visualisations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746). Pour plus d’informations sur les sélections, voir [Création de sélections dans Visualisations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

* **Mesure :** la taille du noeud pour un élément donné est proportionnelle à la valeur de la mesure pour cet élément. Les noeuds plus grands indiquent des valeurs de mesure plus élevées que les noeuds plus petits.

Par exemple, si vous utilisez l&#39;application [!DNL Site] ou HBX, vous pouvez faire glisser, par défaut, des éléments de la dimension Page sur le mappage de processus. La taille de chaque noeud est liée à la quantité de sessions (définie par la mesure Sessions) au cours desquelles cette page a été consultée.

>[!NOTE]
>
>Vous pouvez modifier les dimensions ou les mesures par défaut d’un mappage de processus. Pour connaître les étapes de configuration d’un mappage de processus, voir [Configuration des mappages de processus](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).
