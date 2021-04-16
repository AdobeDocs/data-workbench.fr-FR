---
description: Les vues de hiérarchie ne sont disponibles que lors de l’utilisation du site ou de l’application HBX.
title: Appliquer les vues de hiérarchie
uuid: 859a92af-4f7e-4bb5-9a98-917006894301
exl-id: 27a69404-40d3-44ab-bf5c-b2a5d8d836c2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Appliquer les vues de hiérarchie{#apply-hierarchy-views}

Les vues de hiérarchie ne sont disponibles que lors de l’utilisation du site ou de l’application HBX.

La vue de hiérarchie affiche les pages d’un site Web organisées de manière hiérarchique par nom de fichier et triées par ordre alphabétique. Bien qu’elle soit utile pour l’analyse elle-même, la vue de hiérarchie peut également être utilisée pour configurer des visualisations avancées telles que les mappages de processus. Pour plus d’informations sur les mappages de processus, voir [Process Maps](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

>[!NOTE]
>
>Si votre jeu de données a été configuré pour s&#39;exécuter sur plusieurs serveurs d&#39;une grappe, pour que cette fonctionnalité fonctionne correctement, votre administrateur système doit désigner l&#39;ordinateur qui fonctionne comme votre serveur Central Normalization Server. Pour connaître les étapes à suivre, consultez le chapitre Fichier de configuration de traitement du journal du *Guide de configuration des jeux de données*.

![](assets/vis_Table_CompareHierarchy.png)

**Pour activer ou désactiver la vue de hiérarchie**

* Dans une visualisation de page ou d’URI, cliquez avec le bouton droit de la souris sur un élément ou l’étiquette de la dimension de page, puis cliquez sur **[!UICONTROL Hierarchy View]**.

   ![](assets/mnu_Table_HierarchyView.png)

   Un X s&#39;affiche en regard de l&#39;option lorsque [!DNL hierarchy view] est principal.

   La hiérarchie est organisée en sections de site Web et en pages à l’aide d’une arborescence. Les sections (noeuds) peuvent être développées ou condensées à l’aide du symbole + ou - en regard du nom de la section. Les pages individuelles ne sont pas accompagnées d’un symbole + ou -.

   ![](assets/vis_Table_HierarchyView_Expanded.png)

## Masquage des éléments de Dimension dans une Vue de hiérarchie {#section-e477c469934846da8d807f92fc2f3ed1}

Le masquage désigne la sélection d’un sous-ensemble de vos données ou d’un sous-ensemble des éléments d’une dimension. Vous masquez ou masquez les éléments que vous ne souhaitez pas inclure dans l’analyse. A l’aide des options de menu [!DNL Mask] pour les vues de hiérarchie, vous sélectionnez le pourcentage minimum d’une mesure qu’un élément doit afficher dans la visualisation.

**Pour masquer les données à l’aide de l’option de  [!DNL Mask] menu**

1. Cliquez avec le bouton droit de la souris sur un élément ou l&#39;étiquette de la dimension, puis cliquez sur **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_HierarchyView_Masking.png)

1. Sous Plus que, cliquez sur le pourcentage approprié, puis cliquez sur la mesure à masquer.

Par exemple, si vous cliquez sur 0,1 %, puis sur Vues de page, vous masquez (masquez) tout élément qui contient moins de 0,1 % du nombre total de pages vues et qui affiche tout élément qui contient plus de 0,1 % du nombre total de pages vues. Si vous cliquez sur 0 %, vous masquez tous les éléments avec la valeur 0 (zéro) pour la mesure sélectionnée.
