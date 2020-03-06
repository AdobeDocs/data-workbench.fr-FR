---
description: Les mappages de processus vous permettent d’analyser le flux d’activité entre les éléments d’une dimension.
solution: Analytics
title: Process Map
topic: Data workbench
uuid: f1db41a9-400e-467a-ba59-39831fb166af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Process Map{#process-map}

Les mappages de processus vous permettent d’analyser le flux d’activité entre les éléments d’une dimension.

Pour créer des mappages de processus, faites glisser les éléments d’une dimension sur un mappage bidimensionnel (2D) ou tridimensionnel (3D) vide. Les éléments deviennent des noeuds sur la carte. Les noeuds sont des cercles dans les cartes de processus 2D et les barres dans les cartes de processus 3D.

![](assets/vis_2DProcessMap.png)

![](assets/vis_3DProcessMap.png)

>[!NOTE]
>
>Une carte de processus tire son nom de son utilisation dans l’analyse du flux d’activité entre les étapes d’un processus. Dans ce type d’analyse, chaque élément de la carte représente une étape du processus.

Contrairement aux navigateurs de chemins, les mappages de processus peuvent afficher autant d’éléments que nécessaire pour votre analyse. Vous choisissez les éléments qui vous intéressent et faites-les glisser sur la carte. Contrairement aux navigateurs de chemins, les cartes de processus décrivent le flux d’activité dans les deux directions entre un élément et un ou plusieurs autres éléments.

>[!NOTE]
>
>Pour que ces cartes fonctionnent le mieux possible, vous devez ouvrir une légende de couleur dans l’espace de travail. Pour plus d’informations sur l’utilisation des légendes de couleur avec les mappages de processus, voir [Activation des liens](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-act-color-lnks.md#concept-2c9b9f67f2bd4cd7a5431fa21c094edc)de couleur. Pour plus d’informations sur les légendes de couleur, voir Légendes [](../../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)de couleur.

Chaque mappage de processus est associé à une dimension de base, une dimension de groupe, une dimension de niveau et une mesure, qui fournissent des clés pour interpréter les données affichées dans le mappage de processus.

Les paramètres par défaut pour les dimensions et la mesure d’un mappage de processus dépendent de l’application Outils de données que vous utilisez. Pour plus d’informations sur les dimensions et les mesures disponibles pour vos cartes de processus, voir le guide de l’application pour votre application Outils de données.

* **Dimension de base :** Lorsque vous faites glisser un élément sur un mappage de processus, vous faites glisser un élément de la dimension de base.
* **Dimension de niveau :** Chaque dimension de votre jeu de données est associée à une dimension de niveau (également appelée parent). La dimension de niveau de votre mappage de processus doit être la même que la dimension de niveau (ou parent) pour la dimension de base de votre mappage de processus. Par exemple, si vous faites glisser une page (un élément de la dimension Page) vers la carte, la dimension de niveau correspondante sera Page vue.
* **Dimension de groupe :** La dimension de groupe détermine comment les éléments de la dimension de niveau sont regroupés pour former les connexions entre les noeuds. Pour les mappages de processus, la dimension de groupe est importante pour trois raisons principales :

   * Une connexion entre deux noeuds ne peut pas couvrir plus d’un élément d’une dimension de groupe. Pour comprendre cela, prenez un exemple d’utilisation des données Web. Supposons que les dimensions de base, de niveau et de groupe pour votre mappage de processus soient Page, Page vue et Session, respectivement. Une connexion de la page A à la page B vous indique que, lors d’une session unique, une page vue de la page A s’est produite avant une page vue de la page B sans que d’autres pages (noeuds) de la carte ne soient consultées entre elles. Notez que des pages vues d&#39;autres pages du site ont pu se produire entre les pages vues des pages A et B au cours de la même session, mais ces pages ne sont pas affichées sur cette carte.
   * Une connexion entre deux noeuds peut représenter plusieurs éléments de la dimension de groupe. Par exemple, il peut y avoir plusieurs sessions au cours desquelles une page vue de la page A a eu lieu avant une page vue de la page B. Par conséquent, la connexion entre la page A et la page B représente toutes les sessions individuelles au cours desquelles une page vue de la page A s’est produite avant une page vue de la page B sans que d’autres pages (noeuds) de la carte ne soient consultées entre elles.
   * Lorsque vous effectuez une sélection sur la base d’un noeud dans un mappage de processus, vous sélectionnez tous les éléments de la dimension de groupe qui impliquaient ce noeud. Voir [Sélections dans Visualisations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746). Pour plus d’informations sur les sélections, voir [Création de sélections dans les visualisations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

* **Mesure :** La taille du noeud pour un élément donné est proportionnelle à la valeur de la mesure pour cet élément. Les noeuds plus grands indiquent des valeurs de mesure plus élevées que les noeuds plus petits.

Par exemple, si vous utilisez l’application [!DNL Site] ou HBX, vous pouvez faire glisser, par défaut, des éléments de la dimension Page sur le mappage de processus. La taille de chaque noeud est liée à la quantité de sessions (définie par la mesure Sessions) au cours desquelles cette page a été consultée.

>[!NOTE]
>
>Vous pouvez modifier les dimensions ou la mesure par défaut d’un mappage de processus. Pour connaître les étapes de configuration d’un mappage de processus, voir [Configuration des mappages](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6)de processus.

