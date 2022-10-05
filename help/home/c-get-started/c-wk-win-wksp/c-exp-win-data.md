---
description: Vous pouvez exporter les données de certaines fenêtres vers un fichier Excel (.xls ou .xlsx) ou un fichier de valeurs séparées par des tabulations (.tsv).
title: Exporter les données des fenêtres
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
exl-id: ab931453-d366-4d3a-990e-7a368328da2d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# Exporter les données des fenêtres{#export-window-data}

{{eol}}

Vous pouvez exporter les données de certaines fenêtres vers un fichier Excel (.xls ou .xlsx) ou un fichier de valeurs séparées par des tabulations (.tsv).

Les données ne sont pas exportées à partir des graphiques, des navigateurs de chemins, des mappages de processus, des tracés de dispersion et des globes.

## Exportation des données de fenêtre dans Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

Pour exporter des données de fenêtre individuelles vers Microsoft Excel, les conditions suivantes doivent être remplies :

* Microsoft Excel doit être installé sur le même ordinateur que Data Workbench.
* Le compte utilisateur sous lequel le processus du Data Workbench est en cours d’exécution doit disposer des autorisations d’accès à Microsoft Excel.
* Lorsque vous exportez des données sous forme de fichiers Excel, vous ouvrez une nouvelle instance d’Excel.
* Bien que Data Workbench prenne en charge plus de 256 colonnes et 65 536 lignes de données, les versions de Microsoft Excel antérieures à la version 8.0 ne le font pas.

Si ces conditions sont remplies, Data Workbench lance automatiquement Microsoft Excel et exporte les données dans un nouveau classeur Excel lorsque vous sélectionnez l’option **[!UICONTROL Export To Excel]** .

**Pour exporter des données de fenêtre vers un fichier .xls ou .xlsx**

Cliquez avec le bouton droit de la souris sur la bordure supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Excel ouvre un nouveau classeur contenant les données exportées. À moins que vous n’ayez fourni un titre personnalisé (comme décrit dans la section suivante), ce classeur est nommé à l’aide de la variable [!DNL Export title] (Tableau des jours dans l’exemple ci-dessus).

## Application de titres personnalisés {#section-2a6559df812a470685e43923b7b9024e}

Si vous fournissez un titre personnalisé pour une fenêtre (à l’aide de la propriété [!DNL Custom title] sur le champ [!DNL Export] ) la feuille de calcul sur laquelle Data Workbench exporte les données est nommée à l’aide de ce titre personnalisé au lieu du titre dans la variable [!DNL Export title] (Tableau des jours dans l’exemple ci-dessus).

**Pour appliquer un titre personnalisé à une visualisation**

1. Cliquez avec le bouton droit de la souris sur la bordure supérieure de la fenêtre, puis cliquez dans le **[!UICONTROL Custom title]** champ .
1. you

![](assets/mnu_window_TitleBar_Export.png)

Lorsque vous exportez la visualisation vers Excel, la feuille de calcul contenant les données de cette fenêtre est nommée à l’aide du titre que vous avez spécifié à la place du titre dans le champ [!DNL Export title] champ .

## Exporter les données de fenêtre vers un fichier TSV {#section-93c6b24f7338430aaf5a63b99b9489e8}

**Pour exporter une fenêtre vers un fichier .tsv**

Cliquez avec le bouton droit de la souris sur la bordure supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. La boîte de dialogue [!DNL Save Window] sʼaffiche.
1. Accédez au répertoire dans lequel vous souhaitez enregistrer le fichier. Modifiez le nom du fichier si nécessaire, puis cliquez sur **[!UICONTROL Save]**.
