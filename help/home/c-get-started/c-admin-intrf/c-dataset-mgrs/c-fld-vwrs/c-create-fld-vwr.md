---
description: Vous pouvez ouvrir une visionneuse de champ en tant que légende à partir d’un mappage de dépendance ou en tant que visualisation autonome à partir du menu Admin.
title: Créer une visionneuse de champ
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
exl-id: a2563dbb-1d1f-4ed8-b73b-6ac7a2687405
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 2%

---

# Créer une visionneuse de champ{#create-a-field-viewer}

Vous pouvez ouvrir une visionneuse de champ en tant que légende à partir d’un mappage de dépendance ou en tant que visualisation autonome à partir du menu Admin.

## Création d’une visionneuse de champ à partir d’un mappage de dépendance {#section-040cb83c902b49c48b841d35abc127e5}

Lorsque vous ouvrez une visionneuse de champs à partir d’une carte de dépendance (comme illustré dans [Ouverture des visionneuses de champs](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)), la visionneuse est automatiquement renseignée en fonction de la source du journal, de la transformation ou de la dimension que vous avez cliqué avec le bouton droit de la souris. Pour une source de journal ou une transformation, les champs de la visionneuse sont des entrées ou des sorties de la source de journal ou de la transformation. Pour une dimension, les champs sont des entrées de la dimension. Vous pouvez ajouter et supprimer des champs selon vos besoins.

## Créer des visionneuses de champ comme visualisation autonome {#section-11d10e46631d4fdca45d7534336e1e80}

Lorsque vous ouvrez une visionneuse de champ en tant que visualisation autonome, vous pouvez créer une [!DNL Log Processing Field Viewer] ou une [!DNL Transformation Field Viewer]. La visionneuse est vide et vous devez ajouter les champs de votre choix à la visionneuse. Pour un [!DNL Log Processing Field Viewer], vous pouvez ajouter des champs à partir du fichier [!DNL Log Processing.cfg] ou de tout fichier [!DNL Log Processing dataset include]. Pour un [!DNL Transformation Field Viewer], vous pouvez ajouter des champs à partir du fichier [!DNL Transformation.cfg] ou de tout fichier [!DNL Transformation dataset include].

Pour plus d’informations sur la configuration et l’inclusion de fichiers, consultez le *Guide de configuration des jeux de données*.

## Ajouter et supprimer un champ {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**Pour ajouter un champ à une visionneuse de champ**

* Cliquez avec le bouton droit de la souris dans la visionneuse de champs, puis cliquez sur **[!UICONTROL Fields]** *&lt;**[!UICONTROL field name]*** *&lt;**[!UICONTROL instance]***.

   -ou-

* Cliquez avec le bouton droit de la souris dans une colonne existante de la visionneuse de champs, puis cliquez sur **[!UICONTROL Fields]** *&lt;**[!UICONTROL field name]*** > *&lt;**[!UICONTROL instance]***.

Le nom du champ fait référence au nom du champ et l’instance fait référence à l’emplacement d’utilisation du champ dans la configuration du jeu de données, par exemple une étape de traitement du jeu de données ou une transformation. Certains champs sont utilisés à plusieurs endroits dans la configuration du jeu de données (par exemple, un champ peut être modifié par plusieurs transformations). Vous devez donc sélectionner l’instance du champ à ajouter à votre visionneuse de champs.

Dans la liste des champs disponibles, un X apparaît à gauche de tout champ déjà affiché dans la visionneuse.

**Pour supprimer un champ d’une visionneuse de champ**

* Cliquez avec le bouton droit dans la colonne du champ à supprimer, puis cliquez sur **[!UICONTROL Remove Field]**.
