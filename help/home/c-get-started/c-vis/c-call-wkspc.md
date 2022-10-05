---
description: Les légendes sont des fenêtres que vous ajoutez à un espace de travail pour attirer l’attention sur un élément de dimension particulier en créant une nouvelle visualisation avec une sélection virtuelle de cet élément.
title: Ajout de légendes à un espace de travail
uuid: fb3dd74d-da20-40cb-bc96-e56d25003e48
exl-id: fcdb9231-d44a-4287-b799-6a66f7f79432
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 2%

---

# Ajout de légendes à un espace de travail{#adding-callouts-to-a-workspace}

{{eol}}

Les légendes sont des fenêtres que vous ajoutez à un espace de travail pour attirer l’attention sur un élément de dimension particulier en créant une nouvelle visualisation avec une sélection virtuelle de cet élément.

Data Workbench est fourni avec un ensemble standard de types de légende. Étant donné que votre mise en oeuvre peut être entièrement personnalisée, les types de légende disponibles qui apparaissent dans votre mise en oeuvre peuvent différer de ceux documentés dans ce guide.

Par défaut, Data Workbench fournit les légendes suivantes :

* [Annotation](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-7b6742160b3f4aed872a09c8c023f90d)
* [Graphique en courbes vierge](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Graphique de dispersion vide](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Tableau vierge](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Légende de confiance](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-386d1293ddc24a0c9cccb332e20db791)
* [Légende Mesure](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-daa6d372c22246d9827880a9d6e804d8)

>[!NOTE]
>
>Les légendes ne fonctionnent pas comme des sélections (c’est-à-dire qu’elles n’affectent pas d’autres visualisations dans l’espace de travail), sauf si vous effectuez une sélection dans la légende.

Vous pouvez ajouter ou modifier des définitions de légende en configurant les fichiers de légende stockés dans le *nom du profil*\Context\Callout dossier [!DNL Server] dossier d’installation. Voir [Configuration des légendes](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-callouts.md#concept-f6e91e172f5e4c009245c9c549beb76a).

## Pour ajouter une légende d’annotation à une visualisation {#section-7b6742160b3f4aed872a09c8c023f90d}

1. Cliquez avec le bouton droit de la souris sur l’élément pour lequel vous souhaitez créer une légende, puis cliquez sur **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Image]** ou **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Text]**. Une fenêtre vierge s’affiche avec une connexion visible à cet élément.

   ![](assets/client-call.png)

   Pour ajouter des légendes aux visualisations du graphique, vous devez cliquer avec le bouton droit de la souris au bas de la visualisation (l’axe de base) pour ouvrir un menu.

   ![](assets/visualization_callout_linegraph.png)

1. Selon votre sélection, effectuez l’étape appropriée :

   * Pour une annotation de texte, saisissez ou collez le texte de votre choix dans la légende, puis formatez le texte selon vos besoins. Voir [Utilisation des annotations de texte](../../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * Pour une annotation d’image, collez l’image souhaitée dans la légende en copiant l’image, puis cliquez avec le bouton droit de la souris dans la légende. Cliquez sur **[!UICONTROL Paste image]**. Voir [Utilisation des annotations d’image](../../../home/c-get-started/c-analysis-vis/c-annots/c-image-annots.md#concept-02081ed7d91c4fdcb8fc863f2a51c962).

## Pour ajouter une légende de tableau, de graphique en courbes ou de graphique de dispersion vide à une visualisation {#section-5dcc0504bdb64ed4976f880e2f7b277f}

1. Cliquez avec le bouton droit de la souris sur l’élément pour lequel vous souhaitez créer une légende, puis cliquez sur **[!UICONTROL Add Callout]** > *&lt;**[!UICONTROL callout type]**>*.

   L’exemple suivant illustre une légende Tableau vierge.

   ![](assets/vis_callout_blank_bar_graph.png)

1. Pour sélectionner une dimension, cliquez avec le bouton droit de la souris. **[!UICONTROL None]** et cliquez sur **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*.

   >[!NOTE]
   >
   >Si vous modifiez la dimension dans une visualisation avec une légende, la légende passe de la connexion à l’élément de la dimension d’origine à la connexion à l’ensemble de la visualisation.

## Pour ajouter une légende de confiance à une visualisation {#section-386d1293ddc24a0c9cccb332e20db791}

1. Cliquez avec le bouton droit de la souris sur l’élément pour lequel vous souhaitez créer la légende, puis cliquez sur **[!UICONTROL Add Callout]** > **[!UICONTROL Confidence Legend]**.

   ![](assets/vis_callout_confidenceLegend.png)

1. Si vous le souhaitez, modifiez la variable [!DNL Metric or Formula] champ .

Pour les règles de syntaxe d’expression, voir [Syntaxe du langage de requête](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f). Voir [Légendes de confiance](../../../home/c-get-started/c-analysis-vis/c-legends/c-conf-leg.md#concept-73db81c2c218427786c04068aa778efd).

## Pour ajouter une légende de mesure à une visualisation {#section-daa6d372c22246d9827880a9d6e804d8}

1. Cliquez avec le bouton droit de la souris sur l’élément pour lequel vous souhaitez créer la légende, puis cliquez sur **[!UICONTROL Add Callout]** > **[!UICONTROL Metric Legend]**.

   ![](assets/vis_callout_metricLegend.png)

1. Si vous le souhaitez, ajoutez des mesures à la légende des mesures ou supprimez-les.

Voir [Légendes des mesures](../../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
