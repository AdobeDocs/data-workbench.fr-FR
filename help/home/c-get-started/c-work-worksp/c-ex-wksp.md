---
description: Vous pouvez exporter un espace de travail sous la forme d’un fichier image .png ou exporter les données de certaines fenêtres vers un fichier Excel (.xls ou .xlsx).
title: Exporter un espace de travail
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
exl-id: 87416ddf-2ac0-4f95-ae8e-71051061c757
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# Exporter un espace de travail{#export-a-workspace}

Vous pouvez exporter un espace de travail sous la forme d’un fichier image .png ou exporter les données de certaines fenêtres vers un fichier Excel (.xls ou .xlsx).

## Exporter un espace de travail au format PNG {#section-f9fbe0f0a1c341e2b063cce106cac35e}

Vous pouvez enregistrer un instantané d&#39;un espace de travail au format Portable Network Graphic (`.png` fichiers). Les options de couleur suivantes sont disponibles lors de l’enregistrement des espaces de travail sous la forme de fichiers `.png` :

* **L’** arrière-plan noir copie l’espace de travail tel qu’il s’affiche.
* **L’** arrière-plan blanc copie en couleur les éléments de l’espace de travail et les affiche sur un arrière-plan blanc.
* **L’arrière-plan blanc (B&amp;W)** copie les éléments de l’espace de travail en niveaux de gris et les affiche sur un arrière-plan blanc.

**Pour exporter un espace de travail en tant que fichier .png**

Dans le menu de la barre de titre d’un espace de travail, cliquez sur **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]***.

La boîte de dialogue [!UICONTROL Save Image As] sʼaffiche.

Accédez au répertoire dans lequel vous souhaitez enregistrer le fichier, modifiez le nom du fichier si nécessaire, puis cliquez sur **[!UICONTROL Save]**.

## Exporter les données de l&#39;espace de travail vers Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

Lors de l’exportation d’un espace de travail vers Excel, le Data Workbench exporte les données de certaines visualisations, légendes de dimension et de valeur et annotations de texte dans un nouveau classeur Excel avec une visualisation par feuille de calcul.

Pour exporter des espaces de travail et des fenêtres individuelles vers Microsoft Excel, les exigences suivantes doivent être respectées :

* Microsoft Excel doit être installé sur le même ordinateur que Data Workbench.
* Le compte utilisateur sous lequel s&#39;exécute le processus du Data Workbench doit être autorisé à accéder à Microsoft Excel.

>[!NOTE]
>
>* Lorsque vous exportez des données sous forme de fichiers Excel, vous ouvrez une nouvelle instance d’Excel. Pour plus d’informations sur ce processus, voir [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
>* Bien que le Data Workbench prenne en charge plus de 256 colonnes et 65 536 lignes de données, les versions de Microsoft Excel antérieures à la version 8.0 ne le font pas.
>



Si ces conditions sont remplies, le Data Workbench début automatiquement Microsoft Excel et exporte les données dans un nouveau classeur Excel. Les données ne sont pas exportées à partir des visualisations suivantes : graphiques, navigateurs de chemins, mappages de processus, tracés de dispersion et globes.

## Appliquer des titres personnalisés {#section-a332e157554546cb8e88922a8d7a4fa2}

A moins que vous n&#39;ayez spécifié un titre personnalisé pour la fenêtre dans le menu [!UICONTROL Export], le [!UICONTROL Export title] répertorié (par exemple, Tableau de ville) est utilisé comme nom de feuille de calcul.

1. Cliquez avec le bouton droit de la souris sur la bordure supérieure de la fenêtre et cliquez dans le champ **[!UICONTROL Custom title]**.
1. Tapez le titre à appliquer à la fenêtre.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>Si vous saisissez un trait d’union (-) dans le champ [!UICONTROL Custom title], cette visualisation n’est pas exportée avec l’espace de travail.

Lorsque vous exportez l&#39;espace de travail vers Excel, la feuille de calcul contenant les données de cette fenêtre est nommée à l&#39;aide du titre que vous avez spécifié à la place du titre dans le champ [!UICONTROL Export title].

## Exporter un espace de travail ou une barre latérale vers Excel {#section-360438b66d5f4734826ab463b4a01a75}

**Pour exporter des données d&#39;espace de travail vers un nouveau  [!DNL .xls] ou  [!DNL .xlsx] fichier**

1. Dans la barre de titre de l’espace de travail, cliquez sur **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. Indiquez si l’espace de travail, l’encadré ou les deux doivent être exportés.

## Exporter vers un fichier Excel modèle {#section-814772929ca64cf6b92b89d3fdd02302}

Vous pouvez exporter des données de votre espace de travail vers un fichier Excel de modèle (`.xls` ou `.xlsx`). L’utilisation d’un fichier de modèle peut réduire le temps passé à formater vos données chaque fois que l’espace de travail est exporté.

>[!NOTE]
>
>Ce fichier de modèle doit être un fichier `.xls` ou `.xlsx`, et non un fichier `.xlt`.

Lorsque les données sont exportées, les feuilles à onglets existantes dans le modèle (chacune représentant une visualisation) sont réinsérées avec les données les plus récentes de l’espace de travail, tandis que les nouvelles fenêtres qui ne sont pas présentes dans le modèle en tant que feuilles à onglets sont ignorées. Toutes les autres feuilles à onglets du fichier de modèle restent inchangées.

En outre, si une macro est définie dans le fichier Excel du modèle que vous souhaitez exécuter automatiquement lors de la génération du rapport, nommez la macro &quot;VSExport&quot;.

Supposons que vous souhaitiez utiliser les données de campagne exportées à partir d’une visualisation de tableau dans un graphique circulaire sur une autre feuille à onglets d’un fichier Excel et que vous souhaitiez mettre à jour ces informations chaque semaine. Vous pouvez utiliser un modèle afin de ne pas avoir à recréer vos références depuis la feuille à onglets du tableau vers la feuille à onglets du graphique circulaire chaque fois que vous souhaitez mettre à jour les données. Les données du tableau sont mises à jour lors de l’exportation, ce qui met automatiquement à jour le graphique circulaire.

**Pour exporter des données d&#39;espace de travail vers un modèle  [!DNL .xls] ou un  [!DNL .xlsx] fichier**

1. Cliquez avec le bouton droit sur la barre de titre de l’espace de travail et cliquez sur **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. Indiquez si vous souhaitez exporter un espace de travail, une barre latérale ou les deux.

   La boîte de dialogue [!UICONTROL Select a template worksheet] s&#39;ouvre.

1. Suivez l’une des étapes suivantes, le cas échéant :

   * Si vous utilisez un fichier de modèle `.xls` :

      1. Recherchez et sélectionnez le fichier de modèle `.xls`.
      1. Cliquez sur **[!UICONTROL Open]**.
   * Si vous utilisez un fichier de modèle `.xlsx` :

      1. Accédez à l’emplacement du fichier de modèle. Le nom de fichier `.xlsx` n&#39;est pas affiché.
      1. Dans le champ [!UICONTROL File name], saisissez `.xlsx` et cliquez sur **[!UICONTROL Open]**. Tous les noms de fichier `.xlsx` s&#39;affichent dans la liste de fichiers.

      1. Sélectionnez le fichier de modèle `.xlsx`.
      1. Cliquez sur **[!UICONTROL Open]**.
