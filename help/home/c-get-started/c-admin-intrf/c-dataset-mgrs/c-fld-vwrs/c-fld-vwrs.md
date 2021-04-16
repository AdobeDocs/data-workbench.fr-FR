---
description: Une visionneuse de champs est un tableau contenant les valeurs d’un ou de plusieurs champs de données.
title: Visionneuse de champ
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# Visionneuse de champ{#field-viewer}

Une visionneuse de champs est un tableau contenant les valeurs d’un ou de plusieurs champs de données.

Les champs dont les valeurs s’affichent sont des entrées ou des sorties de sources de journaux, de transformations ou de dimensions étendues d’un jeu de données. Le nom du champ est indiqué dans l’en-tête de colonne et chaque ligne contient la valeur du champ pour une seule ligne de données source. Les visionneuses de champs vous permettant d’afficher les valeurs d’un champ, elles s’avèrent utiles pour écrire et tester [les expressions régulières](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

Vous pouvez ouvrir une visionneuse de champs en tant que légende à partir d’un mappage [!DNL Transformation Dependency] ou en tant que visualisation autonome à partir du menu [!DNL Admin] :

* Création d’une visionneuse de champs à partir d’un mappage [!DNL Transformation Dependency]. Lorsque vous ouvrez une visionneuse de champs à partir d’un mappage [!DNL Transformation Dependency], la visionneuse est automatiquement renseignée en fonction de la source, de la transformation ou de la dimension du journal sur laquelle vous cliquez avec le bouton droit de la souris. Pour une source de journal ou une transformation, les champs de la visionneuse sont des entrées ou des sorties de la source de journal ou de la transformation. Pour une dimension, les champs sont des entrées de la dimension. Vous pouvez ajouter et supprimer des champs selon vos besoins.

* Création d’une visionneuse de champs en tant que visualisation autonome. Lorsque vous ouvrez une visionneuse de champs en tant que visualisation autonome, vous pouvez créer une [!DNL Log Processing Field Viewer] ou une [!DNL Transformation Field Viewer]. La visionneuse est vide et vous devez ajouter les champs de votre choix à la visionneuse. Pour un [!DNL Log Processing Field Viewer], vous pouvez ajouter des champs à partir du fichier [!DNL Log Processing.cfg] ou de tout fichier [!DNL Log Processing Dataset Include]. Pour un [!DNL Transformation Field Viewer], vous pouvez ajouter des champs à partir du fichier [!DNL Transformation.cfg] ou de tout fichier [!DNL Transformation Dataset Include].

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>Les visionneuses de champs ne sont pas des visualisations de tableau ; par conséquent, elles n’ont pas les propriétés associées aux tableaux.

Pour plus d’informations sur l’ajout et la suppression de champs et le filtrage dans une visionneuse de champs, voir [Interfaces d’administration](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
