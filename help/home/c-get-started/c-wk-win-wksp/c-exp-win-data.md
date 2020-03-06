---
description: Vous pouvez exporter les données de certaines fenêtres vers un fichier Excel (.xls ou .xlsx) ou un fichier de valeurs séparées par des tabulations (.tsv).
solution: Analytics
title: Exporter les données de la fenêtre
topic: Data workbench
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exporter les données de la fenêtre{#export-window-data}

Vous pouvez exporter les données de certaines fenêtres vers un fichier Excel (.xls ou .xlsx) ou un fichier de valeurs séparées par des tabulations (.tsv).

Les données ne sont pas exportées à partir de graphiques, de navigateurs de chemins, de mappages de processus, de tracés de dispersion et de globes.

## Exportation de données de fenêtre vers Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

Pour exporter des données de fenêtre individuelles vers Microsoft Excel, les conditions suivantes doivent être remplies :

* Microsoft Excel doit être installé sur le même ordinateur que les outils de données.
* Le compte utilisateur sous lequel s’exécute le processus Outils de données doit avoir l’autorisation d’accéder à Microsoft Excel.
* Lorsque vous exportez des données sous forme de fichiers Excel, vous ouvrez une nouvelle instance d’Excel.
* Bien que les outils de données prennent en charge plus de 256 colonnes et 65 536 lignes de données, les versions de Microsoft Excel antérieures à la version 8.0 ne le sont pas.

Si ces conditions sont remplies, les outils de données démarrent automatiquement Microsoft Excel et exportent les données vers un nouveau classeur Excel lorsque vous sélectionnez l’option de **[!UICONTROL Export To Excel]** menu.

**Pour exporter des données de fenêtre vers un fichier .xls ou .xlsx**

Cliquez avec le bouton droit sur la bordure supérieure de la fenêtre et cliquez sur **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Excel ouvre un nouveau classeur contenant les données exportées. Sauf si vous avez fourni un titre personnalisé (comme décrit dans la section suivante), ce classeur est nommé à l’aide de la [!DNL Export title] (table du jour dans l’exemple ci-dessus).

## Application de titres personnalisés {#section-2a6559df812a470685e43923b7b9024e}

Si vous fournissez un titre personnalisé pour une fenêtre (à l’aide du [!DNL Custom title] champ du [!DNL Export] menu), la feuille de calcul vers laquelle les outils de données exportent les données est nommée à l’aide de ce titre personnalisé au lieu du titre dans le [!DNL Export title] champ (Table des jours dans l’exemple ci-dessus).

**Pour appliquer un titre personnalisé à une visualisation**

1. Cliquez avec le bouton droit de la souris sur la bordure supérieure de la fenêtre, puis cliquez dans le **[!UICONTROL Custom title]** champ.
1. you

![](assets/mnu_window_TitleBar_Export.png)

Lorsque vous exportez la visualisation vers Excel, la feuille de calcul contenant les données de cette fenêtre est nommée à l’aide du titre que vous avez spécifié au lieu du titre dans le [!DNL Export title] champ.

## Exportation des données de fenêtre vers un fichier TSV {#section-93c6b24f7338430aaf5a63b99b9489e8}

**Pour exporter une fenêtre vers un fichier .tsv**

Cliquez avec le bouton droit sur la bordure supérieure de la fenêtre et cliquez sur **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. La [!DNL Save Window] boîte de dialogue s’affiche.
1. Accédez au répertoire dans lequel vous souhaitez enregistrer le fichier. Si nécessaire, modifiez le nom du fichier, puis cliquez sur **[!UICONTROL Save]**.

