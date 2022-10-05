---
description: Vous pouvez exporter un espace de travail sous la forme d’un fichier image .png ou exporter les données de certaines fenêtres vers un fichier Excel (.xls ou .xlsx).
title: Exporter un espace de travail
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
exl-id: 87416ddf-2ac0-4f95-ae8e-71051061c757
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# Exporter un espace de travail{#export-a-workspace}

{{eol}}

Vous pouvez exporter un espace de travail sous la forme d’un fichier image .png ou exporter les données de certaines fenêtres vers un fichier Excel (.xls ou .xlsx).

## Exportation des espaces de travail sous la forme d’un fichier PNG {#section-f9fbe0f0a1c341e2b063cce106cac35e}

Vous pouvez enregistrer un instantané d’un espace de travail au format Portable Network Graphic (`.png` ). Les options de couleur suivantes sont disponibles lors de l’enregistrement des espaces de travail en tant que `.png` files :

* **Arrière-plan noir** copie l’espace de travail tel qu’il s’affiche.
* **Arrière-plan blanc** copie les éléments de l’espace de travail en couleur et les affiche sur un arrière-plan blanc.
* **Arrière-plan blanc (B&amp;W)** copie les éléments de l’espace de travail en niveaux de gris et les affiche sur un fond blanc.

**Pour exporter un espace de travail sous la forme d’un fichier .png**

Dans le menu de la barre de titre d’un espace de travail, cliquez sur **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>*.

La boîte de dialogue [!UICONTROL Save Image As] sʼaffiche.

Accédez au répertoire dans lequel vous souhaitez enregistrer le fichier, modifiez le nom du fichier si nécessaire, puis cliquez sur **[!UICONTROL Save]**.

## Exportation des données de l’espace de travail vers Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

Lors de l’exportation d’un espace de travail vers Excel, Data Workbench exporte les données de certaines visualisations, légendes des dimensions et des valeurs, annotations de texte dans un nouveau classeur Excel avec une visualisation par feuille de calcul.

Pour exporter des espaces de travail et des fenêtres individuelles vers Microsoft Excel, les exigences suivantes doivent être respectées :

* Microsoft Excel doit être installé sur le même ordinateur que Data Workbench.
* Le compte utilisateur sous lequel le processus du Data Workbench est en cours d’exécution doit disposer des autorisations d’accès à Microsoft Excel.

>[!NOTE]
>
>* Lorsque vous exportez des données sous forme de fichiers Excel, vous ouvrez une nouvelle instance d’Excel. Pour plus d’informations sur ce processus, voir [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).
>* Bien que Data Workbench prenne en charge plus de 256 colonnes et 65 536 lignes de données, les versions de Microsoft Excel antérieures à la version 8.0 ne le font pas.
>


Si ces conditions sont remplies, Data Workbench lance automatiquement Microsoft Excel et exporte les données vers un nouveau classeur Excel. Les données ne sont pas exportées à partir des visualisations suivantes : graphiques, navigateurs de chemins, mappages de processus, tracés de dispersion et globes.

## Application de titres personnalisés {#section-a332e157554546cb8e88922a8d7a4fa2}

Sauf si vous avez spécifié un Titre personnalisé pour la fenêtre de la [!UICONTROL Export] , [!UICONTROL Export title] répertorié (tableau de ville, par exemple) est utilisé comme nom de feuille de calcul.

1. Cliquez avec le bouton droit de la souris sur la bordure supérieure de la fenêtre, puis cliquez dans le **[!UICONTROL Custom title]** champ .
1. Saisissez le titre à appliquer à la fenêtre.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>Si vous saisissez un trait d’union (-) dans la variable [!UICONTROL Custom title] , cette visualisation n’est pas exportée avec l’espace de travail.

Lorsque vous exportez l’espace de travail vers Excel, la feuille de calcul contenant les données de cette fenêtre est nommée à l’aide du titre que vous avez spécifié au lieu du titre dans le champ [!UICONTROL Export title] champ .

## Exporter un espace de travail ou une barre latérale vers Excel {#section-360438b66d5f4734826ab463b4a01a75}

**Pour exporter des données d’espace de travail vers une nouvelle [!DNL .xls] ou [!DNL .xlsx] fichier**

1. Dans la barre de titre de l’espace de travail, cliquez sur **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. Indiquez si vous souhaitez exporter l’espace de travail, la barre latérale ou les deux.

## Exporter vers un fichier Excel modèle {#section-814772929ca64cf6b92b89d3fdd02302}

Vous pouvez exporter des données de votre espace de travail vers un fichier Excel de modèle (`.xls` ou `.xlsx`). L’utilisation d’un fichier modèle peut réduire le temps que vous passez à formater vos données chaque fois que l’espace de travail est exporté.

>[!NOTE]
>
>Ce fichier de modèle doit être `.xls` ou `.xlsx` fichier, pas un `.xlt` fichier .

Lors de l’exportation des données, les feuilles de tabulation existantes dans le modèle (qui représentent chacune une visualisation) sont rérenseignées avec les données les plus récentes de l’espace de travail, tandis que toutes les nouvelles fenêtres qui ne sont pas présentes dans le modèle sous forme de feuilles à onglets sont ignorées. Toutes les autres feuilles à onglets du fichier de modèle restent inchangées.

En outre, si une macro est définie dans le fichier Excel modèle que vous souhaitez exécuter automatiquement lors de la génération du rapport, nommez la macro &quot;VSExport&quot;.

Supposons que vous souhaitiez utiliser les données de campagne exportées d’une visualisation de tableau dans un graphique en secteurs sur une autre feuille de calcul à onglets dans un fichier Excel et que vous souhaitiez mettre à jour ces informations chaque semaine. Vous pouvez utiliser un modèle de sorte que vous n’ayez pas à recréer vos références depuis la feuille d’onglets du tableau vers la feuille d’onglets du graphique en secteurs chaque fois que vous souhaitez mettre à jour les données. Les données du tableau sont mises à jour lors de l’exportation, ce qui met automatiquement à jour le graphique en secteurs.

**Pour exporter des données d’espace de travail vers un modèle [!DNL .xls] ou [!DNL .xlsx] fichier**

1. Cliquez avec le bouton droit sur la barre de titre de l’espace de travail, puis cliquez sur **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. Indiquez si vous souhaitez exporter un espace de travail, une barre latérale ou les deux.

   Le [!UICONTROL Select a template worksheet] s’ouvre.

1. Effectuez l’une des étapes suivantes, le cas échéant :

   * Si vous utilisez une `.xls` fichier de modèle :

      1. Parcourir et sélectionner le modèle `.xls` fichier .
      1. Cliquez sur **[!UICONTROL Open]**.
   * Si vous utilisez une `.xlsx` fichier de modèle :

      1. Accédez à l’emplacement du fichier de modèle. Le `.xlsx` nom de fichier ne s’affiche pas.
      1. Dans le [!UICONTROL File name] champ, type `.xlsx` et cliquez sur **[!UICONTROL Open]**. Tous `.xlsx` les noms de fichier s’affichent dans la liste des fichiers.

      1. Sélectionner le modèle `.xlsx` fichier .
      1. Cliquez sur **[!UICONTROL Open]**.
