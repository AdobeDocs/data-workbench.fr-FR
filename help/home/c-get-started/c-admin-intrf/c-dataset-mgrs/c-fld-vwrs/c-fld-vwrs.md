---
description: Une visionneuse de champ est un tableau contenant les valeurs d’un ou de plusieurs champs de données.
title: Visionneuse de champ
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# Visionneuse de champ{#field-viewer}

{{eol}}

Une visionneuse de champ est un tableau contenant les valeurs d’un ou de plusieurs champs de données.

Les champs dont les valeurs s’affichent sont des entrées ou des sorties des sources de journaux, des transformations ou des dimensions étendues d’un jeu de données. Le nom du champ s’affiche dans l’en-tête de colonne et chaque ligne contient la valeur du champ pour une seule ligne de données source. Les visionneuses de champ permettant d’afficher les valeurs d’un champ, elles s’avèrent utiles pour l’écriture et le test. [expressions régulières](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

Vous pouvez ouvrir une visionneuse de champ en tant que légende à partir d’une [!DNL Transformation Dependency] mappage ou en tant que visualisation autonome à partir de [!DNL Admin] menu :

* Création d’une visionneuse de champ à partir d’un [!DNL Transformation Dependency] carte. Lorsque vous ouvrez une visionneuse de champ à partir d’une [!DNL Transformation Dependency] , la visionneuse est renseignée automatiquement en fonction de la source, de la transformation ou de la dimension du journal sur laquelle vous cliquez avec le bouton droit de la souris. Pour une source de journal ou une transformation, les champs de la visionneuse sont des entrées ou des sorties de la source de journal ou de la transformation. Pour une dimension, les champs sont des entrées de la dimension. Vous pouvez ajouter et supprimer des champs selon vos besoins.

* Création d’une visionneuse de champ en tant que visualisation autonome. Lorsque vous ouvrez une visionneuse de champ en tant que visualisation autonome, vous pouvez créer une [!DNL Log Processing Field Viewer] ou [!DNL Transformation Field Viewer]. La visionneuse est vide et vous devez ajouter les champs de votre choix à la visionneuse. Pour un [!DNL Log Processing Field Viewer], vous pouvez ajouter des champs depuis le [!DNL Log Processing.cfg] fichier ou tout [!DNL Log Processing Dataset Include] fichier . Pour un [!DNL Transformation Field Viewer], vous pouvez ajouter des champs depuis le [!DNL Transformation.cfg] fichier ou tout [!DNL Transformation Dataset Include] fichier .

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>Les visionneuses de champ ne sont pas des visualisations de tableau ; par conséquent, elles ne sont pas associées aux propriétés des tableaux.

Pour plus d’informations sur l’ajout et la suppression de champs et le filtrage dans une visionneuse de champs, voir [Interfaces administratives](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
