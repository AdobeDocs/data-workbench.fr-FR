---
description: Vous pouvez ouvrir une visionneuse de champs en tant que légende à partir d’un mappage de dépendances ou en tant que visualisation autonome à partir du menu Admin.
solution: Analytics
title: Création d’une visionneuse de champs
topic: Data workbench
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Création d’une visionneuse de champs{#create-a-field-viewer}

Vous pouvez ouvrir une visionneuse de champs en tant que légende à partir d’un mappage de dépendances ou en tant que visualisation autonome à partir du menu Admin.

## Création d’une visionneuse de champs à partir d’un mappage de dépendances {#section-040cb83c902b49c48b841d35abc127e5}

Lorsque vous ouvrez une visionneuse de champs à partir d’un mappage de dépendances (comme illustré dans [Ouverture des visionneuses](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)de champs), la visionneuse est renseignée automatiquement en fonction de la source, de la transformation ou de la dimension du journal sur laquelle vous cliquez avec le bouton droit de la souris. Pour une source de journal ou une transformation, les champs du lecteur sont des entrées ou des sorties de la source ou de la transformation du journal. Pour une dimension, les champs sont des entrées de la dimension. Vous pouvez ajouter et supprimer des champs selon vos besoins.

## Création de visionneuses de champs en tant que visualisation autonome {#section-11d10e46631d4fdca45d7534336e1e80}

Lorsque vous ouvrez une visionneuse de champs en tant que visualisation autonome, vous pouvez créer une [!DNL Log Processing Field Viewer] ou une [!DNL Transformation Field Viewer]. La visionneuse est vide et vous devez ajouter les champs de votre choix à la visionneuse. Pour un [!DNL Log Processing Field Viewer]fichier, vous pouvez ajouter des champs à partir du [!DNL Log Processing.cfg] fichier ou de n’importe quel [!DNL Log Processing dataset include] fichier. Pour un [!DNL Transformation Field Viewer]fichier, vous pouvez ajouter des champs à partir du [!DNL Transformation.cfg] fichier ou de n’importe quel [!DNL Transformation dataset include] fichier.

Pour plus d’informations sur la configuration et les fichiers inclus, consultez le Guide *de configuration des jeux de* données.

## Ajouter et supprimer un champ {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**Pour ajouter un champ à une visionneuse de champs**

* Cliquez avec le bouton droit de la souris dans la visionneuse de champs, puis cliquez sur **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

   -ou-

* Cliquez avec le bouton droit dans une colonne existante de la visionneuse de champs, puis cliquez sur **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

Le nom du champ fait référence au nom du champ et l’instance fait référence à l’emplacement d’utilisation du champ dans la configuration du jeu de données, par exemple une étape de traitement du jeu de données ou une transformation. Certains champs sont utilisés à plusieurs endroits dans la configuration du jeu de données (par exemple, un champ peut être modifié par plusieurs transformations). Vous devez donc sélectionner l’instance du champ à ajouter à la visionneuse de champs.

Dans la liste des champs disponibles, un X s’affiche à gauche de tout champ déjà affiché dans le lecteur de contenu.

**Pour supprimer un champ d’une visionneuse de champs**

* Cliquez avec le bouton droit de la souris dans la colonne pour le champ à supprimer, puis cliquez sur **[!UICONTROL Remove Field]**.
