---
description: Une visionneuse de champs est un tableau contenant les valeurs d’un ou de plusieurs champs de données.
solution: Analytics
title: Lecteur de champ
topic: Data workbench
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Lecteur de champ{#field-viewer}

Une visionneuse de champs est un tableau contenant les valeurs d’un ou de plusieurs champs de données.

Les champs dont les valeurs s’affichent sont des entrées ou des sorties de sources de journaux, de transformations ou de dimensions étendues d’un jeu de données. Le nom du champ est indiqué dans l’en-tête de colonne et chaque ligne contient la valeur du champ pour une seule ligne de données source. Les visionneuses de champs vous permettant d’afficher les valeurs d’un champ, elles sont utiles pour l’écriture et le test des expressions [](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)régulières.

Vous pouvez ouvrir une visionneuse de champs en tant que légende à partir d’un [!DNL Transformation Dependency] mappage ou en tant que visualisation autonome à partir du [!DNL Admin] menu :

* Création d’une visionneuse de champs à partir d’un [!DNL Transformation Dependency] mappage. Lorsque vous ouvrez une visionneuse de champs à partir d’un [!DNL Transformation Dependency] mappage, la visionneuse est automatiquement renseignée en fonction de la source, de la transformation ou de la dimension du journal sur laquelle vous cliquez avec le bouton droit de la souris. Pour une source de journal ou une transformation, les champs du lecteur sont des entrées ou des sorties de la source ou de la transformation du journal. Pour une dimension, les champs sont des entrées de la dimension. Vous pouvez ajouter et supprimer des champs selon vos besoins.

* Création d’une visionneuse de champs en tant que visualisation autonome. Lorsque vous ouvrez une visionneuse de champs en tant que visualisation autonome, vous pouvez créer une [!DNL Log Processing Field Viewer] ou une [!DNL Transformation Field Viewer]. La visionneuse est vide et vous devez ajouter les champs de votre choix à la visionneuse. Pour un [!DNL Log Processing Field Viewer]fichier, vous pouvez ajouter des champs à partir du [!DNL Log Processing.cfg] fichier ou de n’importe quel [!DNL Log Processing Dataset Include] fichier. Pour un [!DNL Transformation Field Viewer]fichier, vous pouvez ajouter des champs à partir du [!DNL Transformation.cfg] fichier ou de n’importe quel [!DNL Transformation Dataset Include] fichier.

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>Les lecteurs de champ ne sont pas des visualisations de tableau ; par conséquent, elles n’ont pas les propriétés associées aux tableaux.

Pour plus d’informations sur l’ajout et la suppression de champs et le filtrage dans une visionneuse de champs, voir Interfaces [d’administration](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
