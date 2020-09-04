---
description: Créez des en-têtes d’exportation de colonne personnalisés pour vos fichiers d’exportation de segments afin d’ajouter des descriptions facilement compréhensibles pour les segments exportés. Cette fonction d’exportation vous permet également de générer des fichiers au format TSV et CSV.
title: Exportation de segments à l’aide d’en-têtes personnalisés
uuid: 186e7868-13b2-42e1-b83f-5a752ee9b407
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 4%

---


# Exportation de segments à l’aide d’en-têtes personnalisés{#segment-export-with-custom-headers}

Créez des en-têtes d’exportation de colonne personnalisés pour vos fichiers d’exportation de segments afin d’ajouter des descriptions facilement compréhensibles pour les segments exportés. Cette fonction d’exportation vous permet également de générer des fichiers au format TSV et CSV.

De nouvelles fonctionnalités ont été ajoutées à l’exportation de segments, notamment la possibilité d’exporter avec un en-tête, ou dans des formats CSV et TSV.

Vous pouvez créer des en-têtes de colonne pour vos fichiers d’exportation.

## Création d’une exportation de segment {#section-cffff55855f8467ea468b71393ab7676}

1. Ouvrez un espace de travail et cliquez avec le bouton droit de la souris **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]**.

1. Cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Add Level > Extended]** > Choisir un élément.
1. Cliquez avec le bouton droit sur le titre et sélectionnez **[!UICONTROL Add Attribute.]** Sélectionner une dimension dans le menu.

1. Cliquez avec le bouton droit sur le titre et sélectionnez **[!UICONTROL Add Metric.]** Sélectionner une mesure dans le menu.

1. Cliquez avec le bouton droit sur le titre et sélectionnez **[!UICONTROL New Segment Export]**.

   ![](assets/segment_export_headers.png)

   **[!UICONTROL New Segment Export with Header]** renseigne automatiquement le nom de colonne avec le nom de la mesure. **[!UICONTROL New Segment Export]** requiert que vous définissiez un nom personnalisé. ![](assets/segment_export_with_headers.png)

   >[!NOTE]
   >
   >Le champ Nom de colonne ne peut pas rester vide ou l&#39;en-tête ne sera pas présent.

1. Cliquez avec le bouton droit de la souris et nommez le segment, puis cliquez sur **[!UICONTROL Save Export File]**.

   Une fenêtre d&#39;exportation s&#39;ouvre.

1. Cliquez avec le bouton droit de la souris sur le nom de l’exportation, puis cliquez sur **Enregistrer sous`<export filename>`**.

   ![](assets/segment_export_headers_7.png)

1. Right-click [!DNL Admin] > [!DNL Profile Manager] > [!DNL Expand Export]. Recherchez le fichier d’exportation que vous venez de créer et enregistrez-le sur un profil existant.

   ![](assets/segment_export_headers_8.png)

