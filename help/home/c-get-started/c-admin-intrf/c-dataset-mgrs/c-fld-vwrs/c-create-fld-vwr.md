---
description: Vous pouvez ouvrir une visionneuse de champ en tant que légende à partir d’un mappage de dépendance ou en tant que visualisation autonome à partir du menu Admin.
title: Créer une visionneuse de champ
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
exl-id: a2563dbb-1d1f-4ed8-b73b-6ac7a2687405
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 2%

---

# Créer une visionneuse de champ{#create-a-field-viewer}

{{eol}}

Vous pouvez ouvrir une visionneuse de champ en tant que légende à partir d’un mappage de dépendance ou en tant que visualisation autonome à partir du menu Admin.

## Création d’une visionneuse de champ à partir d’une carte des dépendances {#section-040cb83c902b49c48b841d35abc127e5}

Lorsque vous ouvrez une visionneuse de champ à partir d’une carte de dépendance (comme illustré dans la section [Ouverture des visionneuses de champ](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)), la visionneuse est renseignée automatiquement en fonction de la source, de la transformation ou de la dimension du journal sur laquelle vous cliquez avec le bouton droit de la souris. Pour une source de journal ou une transformation, les champs de la visionneuse sont des entrées ou des sorties de la source de journal ou de la transformation. Pour une dimension, les champs sont des entrées de la dimension. Vous pouvez ajouter et supprimer des champs selon vos besoins.

## Création de visionneuses de champ en tant que visualisation autonome {#section-11d10e46631d4fdca45d7534336e1e80}

Lorsque vous ouvrez une visionneuse de champ en tant que visualisation autonome, vous pouvez créer une [!DNL Log Processing Field Viewer] ou [!DNL Transformation Field Viewer]. La visionneuse est vide et vous devez ajouter les champs de votre choix à la visionneuse. Pour un [!DNL Log Processing Field Viewer], vous pouvez ajouter des champs depuis le [!DNL Log Processing.cfg] fichier ou tout [!DNL Log Processing dataset include] fichier . Pour un [!DNL Transformation Field Viewer], vous pouvez ajouter des champs depuis le [!DNL Transformation.cfg] fichier ou tout [!DNL Transformation dataset include] fichier .

Pour plus d’informations sur la configuration et l’inclusion de fichiers, voir *Guide de configuration des jeux de données*.

## Ajouter et supprimer un champ {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**Pour ajouter un champ à une visionneuse de champ**

* Cliquez avec le bouton droit dans la visionneuse de champ, puis cliquez sur **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

   -ou-

* Cliquez avec le bouton droit de la souris dans une colonne existante de la visionneuse de champs, puis cliquez sur **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

Le nom du champ fait référence au nom du champ et l’instance fait référence à l’emplacement d’utilisation du champ dans la configuration du jeu de données, par exemple une étape de traitement du jeu de données ou une transformation. Certains champs sont utilisés à plusieurs endroits dans la configuration du jeu de données (par exemple, un champ peut être modifié par plusieurs transformations). Vous devez donc sélectionner l’instance du champ à ajouter à votre visionneuse de champs.

Dans la liste des champs disponibles, un X apparaît à gauche de tout champ déjà affiché dans la visionneuse.

**Pour supprimer un champ d’une visionneuse de champ**

* Cliquez avec le bouton droit dans la colonne du champ à supprimer, puis cliquez sur **[!UICONTROL Remove Field]**.
