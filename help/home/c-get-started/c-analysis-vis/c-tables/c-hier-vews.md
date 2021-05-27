---
description: Les vues Hiérarchie sont disponibles uniquement lors de l’utilisation du site ou de l’application HBX.
title: Appliquer les vues de hiérarchie
uuid: 859a92af-4f7e-4bb5-9a98-917006894301
exl-id: 27a69404-40d3-44ab-bf5c-b2a5d8d836c2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Appliquer les vues de hiérarchie{#apply-hierarchy-views}

Les vues Hiérarchie sont disponibles uniquement lors de l’utilisation du site ou de l’application HBX.

La vue Hiérarchie affiche les pages d’un site web organisé hiérarchiquement par nom de fichier et triées par ordre alphabétique. Bien qu’utile pour l’analyse elle-même, la vue de hiérarchie peut également être utilisée pour configurer des visualisations avancées comme des mappages de processus. Pour plus d’informations sur les mappages de processus, voir [Cartes de processus](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

>[!NOTE]
>
>Si votre jeu de données a été configuré pour s’exécuter sur plusieurs serveurs d’une grappe, pour que cette fonctionnalité fonctionne correctement, votre administrateur système doit désigner la machine qui fonctionnera comme votre serveur de normalisation Central. Pour connaître les étapes à suivre, reportez-vous au chapitre Fichier de configuration de traitement du journal du *Guide de configuration des jeux de données*.

![](assets/vis_Table_CompareHierarchy.png)

**Pour activer ou désactiver la vue hiérarchique**

* Dans n’importe quelle visualisation de page ou d’URI, cliquez avec le bouton droit de la souris sur un élément ou le libellé de la dimension de page, puis cliquez sur **[!UICONTROL Hierarchy View]**.

   ![](assets/mnu_Table_HierarchyView.png)

   Un X s’affiche en regard de l’option lorsque la valeur [!DNL hierarchy view] est principale.

   La hiérarchie est organisée en sections de site web et en pages à l’aide d’une arborescence. Les sections (noeuds) peuvent être développées ou condensées à l’aide du symbole + ou - situé en regard du nom de la section. Les pages individuelles ne sont pas accompagnées d’un symbole + ou -.

   ![](assets/vis_Table_HierarchyView_Expanded.png)

## Masquage des éléments de Dimension dans une vue hiérarchique {#section-e477c469934846da8d807f92fc2f3ed1}

Le masquage consiste à sélectionner un sous-ensemble de vos données ou un sous-ensemble des éléments d’une dimension. Vous masquez ou masquez les éléments que vous ne souhaitez pas inclure dans l’analyse. À l’aide des options de menu [!DNL Mask] pour les vues de hiérarchie, vous sélectionnez le pourcentage minimum d’une mesure qu’un élément doit afficher dans la visualisation.

**Pour masquer les données à l’aide de l’option  [!DNL Mask] de menu**

1. Cliquez avec le bouton droit de la souris sur un élément ou le libellé de la dimension, puis cliquez sur **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_HierarchyView_Masking.png)

1. Sous Plus que, cliquez sur le pourcentage approprié, puis cliquez sur la mesure à masquer.

Si, par exemple, vous cliquez sur 0,1 %, puis sur Pages vues, vous masquez (masquez) tout élément dont le nombre total de pages vues est inférieur à 0,1 % et affichez tout élément dont le nombre total de pages vues est supérieur à 0,1 %. Si vous cliquez sur 0 %, vous masquez tous les éléments avec une valeur de 0 (zéro) pour la mesure sélectionnée.
