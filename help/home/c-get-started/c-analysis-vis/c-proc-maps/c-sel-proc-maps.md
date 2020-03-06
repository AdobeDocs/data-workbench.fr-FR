---
description: Vous pouvez effectuer des sélections dans des mappages de processus pour créer des filtres qui incluent ou excluent les données associées à un noeud particulier.
solution: Analytics
title: Effectuer une sélection à partir d’un mappage de processus
topic: Data workbench
uuid: 7fd00090-c9ab-4bb6-8584-7de7b6f4b68c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Effectuer une sélection à partir d’un mappage de processus{#make-a-selection-from-a-process-map}

Vous pouvez effectuer des sélections dans des mappages de processus pour créer des filtres qui incluent ou excluent les données associées à un noeud particulier.

La sélection dans une carte de processus implique la dimension de groupe de la carte, qui détermine comment les éléments de la dimension de base (c’est-à-dire les noeuds de la carte) sont regroupés pour former les connexions entre les noeuds.

>[!NOTE]
>
>Vous pouvez modifier la dimension de groupe par défaut pour un mappage de processus. Voir [Configuration des zones de processus](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).

Lorsque vous effectuez une sélection sur la base d’un noeud dans un mappage de processus, vous sélectionnez tous les éléments de la dimension de groupe qui impliquaient ce noeud. Pour mieux comprendre le rôle de la dimension de groupe, prenez en compte les exemples suivants :

* Les films peuvent être regroupés par spectateurs qui les ont classés. Chaque visionneuse est un élément de la dimension Utilisateur, de sorte que la dimension Utilisateur correspondrait à la dimension Groupe pour le mappage de processus. Lorsque vous effectuez une sélection à partir d’un noeud pour un film particulier, vous créez un filtre qui affiche les données des utilisateurs qui ont évalué ou non ce film.
* Les pages du site Web peuvent être regroupées selon les sessions au cours desquelles elles ont été consultées. Chaque session est un élément de la dimension Session, de sorte que la dimension Session correspondrait à la dimension de groupe pour le mappage de processus. Lorsque vous effectuez une sélection à partir d’un noeud pour une page spécifique, vous créez un filtre qui affiche les données des sessions pendant lesquelles cette page a été consultée ou non.

**Pour effectuer une sélection**

1. Cliquez avec le bouton droit de la souris sur un noeud d’un mappage de processus.
1. Cliquez sur l’une des options suivantes pour effectuer une sélection en fonction du noeud :

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL through node name]**: Filtre les données pour inclure tous les éléments de la dimension de groupe qui ont traversé le noeud en filtrant toutes les sessions qui n’ont pas traversé le noeud.

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL NOT through node name]**: Filtre les données pour inclure tous les éléments de la dimension de groupe qui n’ont pas traversé le noeud en filtrant toutes les sessions qui ont traversé le noeud.

![](assets/vis_2DProcessMap_Selections_Movie.png)

![](assets/vis_2DProcessMap_Selections_Page.png)

Lorsque vous effectuez une sélection dans une carte de processus 3D, le noeud pour lequel la sélection est effectuée est entouré. Les repères apparaissent autour de chaque barre pour vous aider à comparer les valeurs de mesure avec et sans la sélection. Voir [Présentation des tests](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).

![](assets/vis_3DProcessMap_Selection.png)

