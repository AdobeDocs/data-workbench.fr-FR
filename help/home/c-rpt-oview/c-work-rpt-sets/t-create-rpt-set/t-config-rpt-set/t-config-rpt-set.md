---
description: Après avoir créé et enregistré les espaces de travail dans le dossier du jeu de rapports, vous devez créer un nouveau fichier Report.cfg.
title: Configurer le jeu de rapports
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Configurer le jeu de rapports{#configure-the-report-set}

Après avoir créé et enregistré les espaces de travail dans le dossier du jeu de rapports, vous devez créer un nouveau fichier Report.cfg.

Vous devez indiquer dans le fichier [!DNL Report.cfg] le moment et la manière de générer et de distribuer les rapports.

**Pour créer un nouveau fichier Report.cfg**

1. Dans les outils de données, ouvrez [!DNL Profile Manager] en cliquant avec le bouton droit dans un espace de travail et en cliquant sur **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. Cliquez sur **[!UICONTROL Reports]** pour ouvrir le dossier [!DNL Reports].
1. Cliquez sur le dossier correspondant à votre jeu de rapports.
1. Dans la colonne [!DNL User] du dossier du jeu de rapports, cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Create]** > **[!UICONTROL Report]**. Un nouveau fichier [!DNL Report.cfg] apparaît dans la colonne [!DNL File].
1. Dans la colonne [!DNL User] du nouveau fichier [!DNL Report.cfg], cliquez avec le bouton droit de la souris sur la coche du fichier [!DNL Report.cfg], puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Infos sur l’étape](assets/cfg_reportcfg.png)

1. Modifiez les paramètres de configuration selon vos besoins. Pour plus d’informations sur ces paramètres, voir [Paramètres Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >L&#39;exemple [!DNL Report.cfg] illustré dans cet exemple contient uniquement les paramètres inclus par défaut dans le fichier [!DNL Report.cfg]. Si vous devez ajouter des paramètres supplémentaires à un fichier [!DNL Report.cfg], vous devez le faire à l’aide d’un éditeur de texte. Pour connaître les étapes à suivre, voir [Modification de fichiers Report.cfg existants](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL Report.cfg (modified)]** dans la partie supérieure du fichier et en cliquant sur **[!UICONTROL Save as Reports\]***&lt; **[!UICONTROL ReportSetName]*****[!UICONTROL \Report.cfg]**.
1. Fermez le fichier.
1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche de la colonne [!DNL User] du nouveau fichier [!DNL Report.cfg] et sélectionnez **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]***.
