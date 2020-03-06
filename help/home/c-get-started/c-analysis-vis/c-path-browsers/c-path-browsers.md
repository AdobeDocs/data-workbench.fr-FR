---
description: Un navigateur de chemins vous permet d’analyser la séquence d’accès aux éléments d’une dimension particulière.
solution: Analytics
title: Navigateurs de chemins
topic: Data workbench
uuid: 548091dc-935f-41ac-b67c-39080988f1ea
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Navigateurs de chemins{#path-browsers}

Un navigateur de chemins vous permet d’analyser la séquence d’accès aux éléments d’une dimension particulière.

Pour créer un navigateur de chemins, faites glisser un élément d’une dimension sur une visualisation de navigateur de chemins vierge. L’élément que vous faites glisser sur le navigateur de chemins devient la racine du navigateur de chemins. Le navigateur de chemins affiche les chemins qui traversent la racine, ce qui vous permet de voir la séquence d’éléments qui ont été consultés avant et après la racine.

Le navigateur de chemins suivant affiche la séquence des films que les visiteurs ont classés avant et après avoir évalué le film *L’aviateur*, qui est la racine du navigateur de chemins d’accès. Chaque nom de film est un élément de la dimension Film, qui est défini dans un jeu de données constitué de données vidéo qui inclut le nom des films et l’évaluation de ces films par les visiteurs.

![](assets/vis_PathBrowser_Movies.png)

Vous pouvez créer des navigateurs de chemins pour afficher la séquence d’accès aux éléments de n’importe quelle dimension de votre jeu de données. Par exemple, si vous travaillez avec des données de site Web, vous pouvez créer un navigateur de chemins qui affiche la séquence des pages de site Web consultées avant et après la racine pour chaque session au cours de laquelle la racine a été consultée ou pour chaque visiteur du site qui a consulté la racine.

![](assets/vis_PathBrowser_Pages.png)

Chaque navigateur de chemins est associé à une dimension de base, une dimension de groupe, une dimension de niveau et une mesure, qui fournissent des clés pour interpréter les données affichées dans le navigateur de chemins.

* **Dimension de base :** Lorsque vous faites glisser un élément racine sur le navigateur de chemins, vous faites glisser un élément de la dimension de base. Tous les autres éléments qui apparaissent dans les chemins sont des éléments de la dimension de base. Vous pouvez modifier la dimension de base en faisant glisser un élément d’une autre dimension sur le navigateur de chemins.
* **Dimension de niveau :** Chaque dimension de votre jeu de données est associée à une dimension de niveau (également appelée parent). La dimension de niveau de votre navigateur de chemins doit être la même que la dimension de niveau (ou parent) pour la dimension de base de votre navigateur de chemins. La dimension de niveau d’un navigateur de chemins est importante pour deux raisons principales :

   * Lorsque vous suivez un chemin d’un élément de dimension de base à un autre, vous passez d’un élément de dimension de niveau à un autre. Supposons, par exemple, que vous ayez créé un navigateur de chemins affichant les pages d’un site Web. Chaque page est un élément de la dimension Page et la dimension de niveau de Page est Page vue. Lorsque vous passez d’une page à l’autre, vous passez d’une page vue à l’autre.
   * Lorsque vous sélectionnez un chemin d’accès aux éléments de dimension de base dans un navigateur de chemins, vous sélectionnez des données pour les éléments correspondants de la dimension de niveau. La sélection inclut toujours les éléments de la dimension de niveau qui se rapportent à la racine, et elle est affinée en ajoutant d’autres éléments au chemin. Par exemple, lorsque vous sélectionnez un chemin de pages, tel que root > A > B, vous sélectionnez les données pour les pages vues associées à la racine où la page suivante est A et la page suivante est B.

      Pour plus d’informations sur la sélection d’un chemin dans un navigateur de chemins, voir [Sélection de chemins](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/t-sel-paths.md#task-bf44d08c71954ef2adec4b82f840adeb). Pour plus d’informations sur les sélections, voir [Création de sélections dans les visualisations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).
   >[!NOTE]
   >
   >Le navigateur de chemins ignore les éléments de la dimension de niveau sans éléments de dimension de base associés. Cette situation peut se produire lorsque vous créez un navigateur de chemins à partir d’un mappage de processus. Voir [Création de navigateurs](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-create-path-browsers.md#concept-e120de6a740d4b6f98dda9e2b638f6ff)de chemin.

* **Dimension de groupe :** La dimension de groupe détermine la manière dont les éléments de la dimension de niveau sont regroupés pour former les chemins d’un navigateur de chemins. Plus précisément, les éléments de dimension de niveau associés à un chemin unique dans un navigateur de chemins ne peuvent pas couvrir plus d’un élément d’une dimension de groupe.

   Pour comprendre cela, prenez un exemple d’utilisation des données Web. Supposons que les dimensions de base, de niveau et de groupe pour votre navigateur de chemins soient Page, Page vue et Session, respectivement. Un chemin dans votre navigateur de chemins affiche la séquence de pages A > B > C. La dimension de groupe (Session) vous indique que les pages vues (éléments de la dimension Page vue) associées à la séquence de pages A > B > C se sont produites au cours d’une session unique. Il est important de noter qu’il peut y avoir plusieurs sessions au cours desquelles il y a eu des pages vues pour la séquence de pages A > B > C. Par conséquent, le chemin présentant la séquence de pages A > B > C représente toutes les sessions individuelles au cours desquelles les pages vues pour cette séquence ont eu lieu.

* **Mesure**: L’épaisseur du chemin conduisant à un élément donné est proportionnelle à la valeur de la mesure pour cet élément. Les chemins plus épais indiquent des valeurs de mesure plus élevées que les chemins plus fins.

Le libellé dans le coin supérieur gauche du navigateur de chemins désigne les dimensions de base et de groupe représentées dans la visualisation. Le nom de la dimension de niveau n’est pas visible dans la visualisation du navigateur de chemins. Le libellé prend la forme &quot;Séquence du nom *de dimension de* base+s pour chaque nom *de dimension de* groupe&quot;. Par exemple, le libellé Séquence de films pour chaque utilisateur indique que la dimension de base est Film et que la dimension de groupe est Utilisateur.

![](assets/vis_PathBrowser_Movies.png)

En cliquant avec le bouton droit sur un élément du navigateur de chemins, vous pouvez voir le nom de la mesure associée au navigateur de chemins et sa valeur pour cet élément.

![](assets/vis_PathBrowser_RightClick.png)

>[!NOTE]
>
>Vous pouvez modifier les dimensions et les mesures par défaut d’un navigateur de chemins. Pour plus d’informations sur la configuration de la visualisation d’un navigateur de chemins, voir [Configuration des navigateurs](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3)de chemins.

