---
description: Vous pouvez exporter les données de certaines fenêtres vers un fichier Excel (.xls ou .xlsx) ou un fichier de valeurs séparées par des tabulations (.tsv).
title: Exporter les données des fenêtres
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
exl-id: ab931453-d366-4d3a-990e-7a368328da2d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# Exporter les données des fenêtres{#export-window-data}

Vous pouvez exporter les données de certaines fenêtres vers un fichier Excel (.xls ou .xlsx) ou un fichier de valeurs séparées par des tabulations (.tsv).

Les données ne sont pas exportées à partir de graphiques, de navigateurs de chemins, de mappages de processus, de tracés de dispersion et de globes.

## Exporter les données de fenêtre vers Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

Pour exporter des données de fenêtre individuelles vers Microsoft Excel, les conditions suivantes doivent être remplies :

* Microsoft Excel doit être installé sur le même ordinateur que Data Workbench.
* Le compte utilisateur sous lequel s&#39;exécute le processus du Data Workbench doit être autorisé à accéder à Microsoft Excel.
* Lorsque vous exportez des données sous forme de fichiers Excel, vous ouvrez une nouvelle instance d’Excel.
* Bien que le Data Workbench prenne en charge plus de 256 colonnes et 65 536 lignes de données, les versions de Microsoft Excel antérieures à la version 8.0 ne le font pas.

Si ces conditions sont remplies, le Data Workbench début automatiquement Microsoft Excel et exporte les données dans un nouveau classeur Excel lorsque vous sélectionnez l&#39;option de menu **[!UICONTROL Export To Excel]**.

**Pour exporter des données de fenêtre vers un fichier .xls ou .xlsx**

Cliquez avec le bouton droit sur la bordure supérieure de la fenêtre et cliquez sur **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Excel ouvre un nouveau classeur contenant les données exportées. Sauf si vous avez fourni un titre personnalisé (comme décrit dans la section suivante), ce classeur porte le nom [!DNL Export title] (Table de journée dans l’exemple ci-dessus).

## Appliquer des titres personnalisés {#section-2a6559df812a470685e43923b7b9024e}

Si vous fournissez un titre personnalisé pour une fenêtre (à l&#39;aide du champ [!DNL Custom title] du menu [!DNL Export]), la feuille de calcul à laquelle le Data Workbench exporte les données est nommée à l&#39;aide de ce titre personnalisé au lieu du titre dans le champ [!DNL Export title] (Table de journée dans l&#39;exemple ci-dessus).

**Pour appliquer un titre personnalisé à une visualisation**

1. Cliquez avec le bouton droit de la souris sur la bordure supérieure de la fenêtre et cliquez dans le champ **[!UICONTROL Custom title]**.
1. you

![](assets/mnu_window_TitleBar_Export.png)

Lorsque vous exportez la visualisation vers Excel, la feuille de calcul contenant les données de cette fenêtre est nommée à l’aide du titre que vous avez spécifié à la place du titre dans le champ [!DNL Export title].

## Exporter les données de fenêtre dans un fichier TSV {#section-93c6b24f7338430aaf5a63b99b9489e8}

**Pour exporter une fenêtre vers un fichier .tsv**

Cliquez avec le bouton droit sur la bordure supérieure de la fenêtre et cliquez sur **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. La boîte de dialogue [!DNL Save Window] sʼaffiche.
1. Accédez au répertoire dans lequel vous souhaitez enregistrer le fichier. Modifiez le nom du fichier si nécessaire, puis cliquez sur **[!UICONTROL Save]**.
