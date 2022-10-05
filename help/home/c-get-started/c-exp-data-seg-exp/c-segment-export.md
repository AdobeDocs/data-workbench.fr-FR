---
description: Créez des en-têtes d’exportation de colonnes personnalisés pour vos fichiers d’exportation de segments afin d’ajouter des descriptions facilement comprises pour les segments exportés. Cette fonction d’exportation permet également d’effectuer une sortie au format TSV et CSV.
title: Exportation de segments à l’aide d’en-têtes personnalisés
uuid: 186e7868-13b2-42e1-b83f-5a752ee9b407
exl-id: 1d27f926-35e1-4886-b7a6-702d9947dabb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 4%

---

# Exportation de segments à l’aide d’en-têtes personnalisés{#segment-export-with-custom-headers}

{{eol}}

Créez des en-têtes d’exportation de colonnes personnalisés pour vos fichiers d’exportation de segments afin d’ajouter des descriptions facilement comprises pour les segments exportés. Cette fonction d’exportation permet également d’effectuer une sortie au format TSV et CSV.

De nouvelles fonctionnalités ont été ajoutées à l’exportation de segments, notamment la possibilité d’exporter avec un en-tête, ou dans des formats CSV et TSV.

Vous pouvez créer des en-têtes de colonne pour vos fichiers d’exportation.

## Création d’une exportation de segment {#section-cffff55855f8467ea468b71393ab7676}

1. Ouvrez un espace de travail et cliquez avec le bouton droit de la souris. **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]**.

1. Cliquez avec le bouton droit et sélectionnez **[!UICONTROL Add Level > Extended]** > Sélectionnez un élément.
1. Cliquez avec le bouton droit sur le titre, puis sélectionnez **[!UICONTROL Add Attribute.]** Sélectionnez une dimension dans le menu.

1. Cliquez avec le bouton droit sur le titre, puis sélectionnez **[!UICONTROL Add Metric.]** Sélectionnez une mesure dans le menu.

1. Cliquez avec le bouton droit sur le titre, puis sélectionnez **[!UICONTROL New Segment Export]**.

   ![](assets/segment_export_headers.png)

   **[!UICONTROL New Segment Export with Header]** renseigne automatiquement le nom de la colonne avec le nom de la mesure. **[!UICONTROL New Segment Export]** nécessite que vous définissiez un nom personnalisé. ![](assets/segment_export_with_headers.png)

   >[!NOTE]
   >
   >Le champ Nom de colonne ne peut pas être laissé vide ou l’en-tête ne sera pas présent.

1. Cliquez avec le bouton droit de la souris et nommez le segment, puis cliquez sur **[!UICONTROL Save Export File]**.

   Une fenêtre d’exportation s’ouvre.

1. Cliquez avec le bouton droit sur le nom de l&#39;export, puis cliquez sur **Enregistrer sous`<export filename>`**.

   ![](assets/segment_export_headers_7.png)

1. Clic droit [!DNL Admin] > [!DNL Profile Manager] > [!DNL Expand Export]. Recherchez le fichier d&#39;export que vous venez de créer et enregistrez-le dans un profil existant.

   ![](assets/segment_export_headers_8.png)
