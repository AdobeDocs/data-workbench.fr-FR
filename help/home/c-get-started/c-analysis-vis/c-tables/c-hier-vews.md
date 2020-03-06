---
description: Les vues hiérarchiques sont disponibles uniquement lors de l’utilisation du site ou de l’application HBX.
solution: Analytics
title: Appliquer les vues de hiérarchie
topic: Data workbench
uuid: 859a92af-4f7e-4bb5-9a98-917006894301
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Appliquer les vues de hiérarchie{#apply-hierarchy-views}

Les vues hiérarchiques sont disponibles uniquement lors de l’utilisation du site ou de l’application HBX.

La vue Hiérarchie affiche les pages d’un site Web organisées de manière hiérarchique par nom de fichier et triées par ordre alphabétique. Bien qu’elle soit utile pour l’analyse elle-même, la vue de hiérarchie peut également être utilisée pour configurer des visualisations avancées telles que les mappages de processus. Pour plus d’informations sur les mappages de processus, voir [Process Maps](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

>[!NOTE]
>
>Si votre jeu de données a été configuré pour s’exécuter sur plusieurs serveurs d’une grappe, pour que cette fonctionnalité fonctionne correctement, votre administrateur système doit désigner l’ordinateur qui fonctionne comme votre serveur Central Normalization Server. Pour savoir comment procéder, reportez-vous au chapitre Fichier de configuration de traitement des journaux du Guide *de configuration des jeux de* données.

![](assets/vis_Table_CompareHierarchy.png)

**Pour activer ou désactiver la vue Hiérarchie**

* Dans une visualisation de page ou d’URI, cliquez avec le bouton droit de la souris sur un élément ou le libellé de la dimension de page, puis cliquez sur **[!UICONTROL Hierarchy View]**.

   ![](assets/mnu_Table_HierarchyView.png)

   Un X s’affiche en regard de l’option lorsque la balise [!DNL hierarchy view] est active.

   La hiérarchie est organisée en sections de site Web et en pages à l’aide d’une arborescence. Les sections (noeuds) peuvent être étendues ou condensées à l’aide du symbole + ou - en regard du nom de la section. Les pages individuelles ne sont pas accompagnées d’un symbole + ou -.

   ![](assets/vis_Table_HierarchyView_Expanded.png)

## Masquage des éléments de dimension dans une vue Hiérarchie {#section-e477c469934846da8d807f92fc2f3ed1}

Le masquage désigne la sélection d’un sous-ensemble de vos données ou d’un sous-ensemble des éléments d’une dimension. Vous masquez ou masquez les éléments que vous ne souhaitez pas inclure dans l’analyse. A l’aide des options [!DNL Mask] de menu pour les vues de hiérarchie, vous sélectionnez le pourcentage minimum d’une mesure qu’un élément doit afficher dans la visualisation.

**Pour masquer les données à l’aide de l’option de[!DNL Mask]menu**

1. Cliquez avec le bouton droit de la souris sur un élément ou l’étiquette de la dimension, puis cliquez sur **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_HierarchyView_Masking.png)

1. Sous Plus que, cliquez sur le pourcentage approprié, puis cliquez sur la mesure à masquer.

Par exemple, si vous cliquez sur 0,1 %, puis sur Pages vues, vous masquez (masquez) tout élément qui contient moins de 0,1 % du nombre total de pages vues et qui affiche tout élément qui a plus de 0,1 % du nombre total de pages vues. Si vous cliquez sur 0 %, vous masquez tous les éléments avec une valeur de 0 (zéro) pour la mesure sélectionnée.
