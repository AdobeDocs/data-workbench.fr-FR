---
description: Un navigateur de chemins d’accès permet d’analyser la séquence d’accès aux éléments d’une dimension particulière.
title: Navigateurs de chemins d’accès
uuid: 548091dc-935f-41ac-b67c-39080988f1ea
exl-id: 563cf0e3-39d7-49b7-b808-b0233169fb1a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 0%

---

# Navigateurs de chemins d’accès{#path-browsers}

{{eol}}

Un navigateur de chemins d’accès permet d’analyser la séquence d’accès aux éléments d’une dimension particulière.

Vous créez un navigateur de chemins d’accès en faisant glisser un élément d’une dimension sur une visualisation de navigateur de chemins d’accès vide. L’élément que vous faites glisser sur l’explorateur de chemins d’accès devient la racine de l’explorateur de chemins d’accès. L’explorateur de chemins d’accès affiche les chemins qui traversent la racine, ce qui vous permet de voir la séquence d’éléments consultés avant et après la racine.

L’explorateur de chemins d’accès suivant montre la séquence de films que les visiteurs ont évaluée avant et après l’évaluation du film. *L&#39;aviateur*, qui est la racine de l’explorateur de chemins d’accès. Chaque nom de film est un élément de la dimension Film, qui est défini dans un jeu de données constitué de données de film qui incluent les noms des films et l’évaluation de ces films par les visiteurs.

![](assets/vis_PathBrowser_Movies.png)

Vous pouvez créer des navigateurs de chemins d’accès pour afficher la séquence d’accès aux éléments de n’importe quelle dimension de votre jeu de données. Si vous utilisez, par exemple, des données de site web, vous pouvez créer un navigateur de chemins d’accès qui affiche la séquence des pages du site web consultées avant et après la racine de chaque session où la racine a été consultée ou pour chaque visiteur du site qui a consulté la racine.

![](assets/vis_PathBrowser_Pages.png)

Chaque navigateur de chemins d’accès est associé à une dimension de base, une dimension de groupe, une dimension de niveau et une mesure, qui fournissent des clés pour interpréter les données affichées dans l’explorateur de chemins d’accès.

* **Dimension de base :** Lorsque vous faites glisser et déposez un élément racine sur l’explorateur de chemins d’accès, vous faites glisser et déposez un élément de la dimension de base. Tous les autres éléments qui apparaissent dans les chemins sont des éléments de la dimension de base. Vous pouvez modifier la dimension de base en faisant glisser et en déposant un élément d’une autre dimension sur l’explorateur de chemins d’accès.
* **Dimension de niveau :** Chaque dimension de votre jeu de données est associée à une dimension de niveau (également appelée parent). La dimension de niveau de votre navigateur de chemins d’accès doit être identique à la dimension de niveau (ou parent) de la dimension de base de votre navigateur de chemins d’accès. La dimension de niveau d’un navigateur de chemins d’accès est importante pour deux raisons principales :

   * Lorsque vous suivez un chemin d’un élément de dimension de base à un autre, vous passez d’un élément de dimension de niveau à un autre. Supposons, par exemple, que vous ayez créé un navigateur de chemins d’accès affichant les pages d’un site web. Chaque page est un élément de la dimension Page et la dimension de niveau de Page est Page vue. Lorsque vous passez d’une page à l’autre, vous passez d’une page vue à l’autre.
   * Lorsque vous sélectionnez un chemin d’accès d’éléments de dimension de base dans un navigateur de chemins d’accès, vous sélectionnez des données pour les éléments correspondants de la dimension de niveau. La sélection inclut toujours les éléments de la dimension de niveau qui se rapportent à la racine. Elle est affinée en ajoutant d’autres éléments au chemin. Par exemple, lorsque vous sélectionnez un chemin d’accès aux pages, tel que root > A > B, vous sélectionnez des données pour les pages vues associées à la racine où la page suivante est A et la page suivante est B.

      Pour plus d’informations sur la sélection d’un chemin dans l’explorateur de chemins d’accès, voir [Sélection des chemins](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/t-sel-paths.md#task-bf44d08c71954ef2adec4b82f840adeb). Pour plus d’informations sur les sélections, voir [Réalisation de sélections dans les visualisations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).
   >[!NOTE]
   >
   >L’explorateur de chemins d’accès ignore les éléments de la dimension de niveau sans éléments de dimension de base associés. Cette situation peut se produire lorsque vous créez un navigateur de chemins d’accès à partir d’une cartographie des processus. Voir [Création de navigateurs de chemins d’accès](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-create-path-browsers.md#concept-e120de6a740d4b6f98dda9e2b638f6ff).

* **Dimension de groupe :** La dimension de groupe détermine la manière dont les éléments de la dimension de niveau sont regroupés pour former les chemins d’accès d’un navigateur de chemins d’accès. En particulier, les éléments de dimension de niveau associés à un seul chemin dans un navigateur de chemins d’accès ne peuvent pas couvrir plusieurs éléments d’une dimension de groupe.

   Pour comprendre cela, prenez un exemple d’utilisation des données web. Supposons que les dimensions de base, de niveau et de groupe de votre navigateur de chemins d’accès soient Page, Page vue et Session, respectivement. Un chemin dans l’explorateur de chemins d’accès affiche la séquence de page A > B > C. La dimension de groupe (Session) vous indique que les pages vues (éléments de la dimension Page vue) associées à la séquence de page A > B > C ont eu lieu au cours d’une seule session. Il est important de noter qu’il peut y avoir plusieurs sessions au cours desquelles il y a eu des pages vues pour la séquence de page A > B > C. Par conséquent, le chemin d’accès présentant la séquence de page A > B > C représente toutes les sessions individuelles au cours desquelles les pages vues pour cette séquence ont eu lieu.

* **Mesure**: L’épaisseur du chemin menant à un élément donné est proportionnelle à la valeur de la mesure pour cet élément. Les chemins plus épais indiquent des valeurs de mesure plus élevées que les chemins plus fins.

Le libellé situé dans le coin supérieur gauche de l’explorateur de chemins d’accès nomme les dimensions de base et de groupe représentées dans la visualisation. Le nom de la dimension de niveau n’est pas visible dans la visualisation de l’explorateur de chemins d’accès. Le libellé se présente sous la forme &quot;Séquence de *nom de la dimension de base*+s pour chaque *nom de la dimension du groupe*.&quot; Par exemple, le libellé Séquence de films pour chaque utilisateur indique que la dimension de base est Film et la dimension de groupe est Utilisateur.

![](assets/vis_PathBrowser_Movies.png)

En cliquant avec le bouton droit de la souris sur un élément de l’explorateur de chemins d’accès, vous pouvez voir le nom de la mesure associée à l’explorateur de chemins d’accès et sa valeur pour cet élément.

![](assets/vis_PathBrowser_RightClick.png)

>[!NOTE]
>
>Vous pouvez modifier les dimensions et les mesures par défaut d’un navigateur de chemins d’accès. Pour obtenir des instructions sur la configuration d’une visualisation de navigateur de chemins d’accès, voir [Configuration des navigateurs de chemins d’accès](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).
