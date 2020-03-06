---
description: Après avoir créé et enregistré les espaces de travail dans le dossier du jeu de rapports, vous devez créer un nouveau fichier Report.cfg.
solution: Analytics
title: Configuration du jeu de rapports
topic: Data workbench
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration du jeu de rapports{#configure-the-report-set}

Après avoir créé et enregistré les espaces de travail dans le dossier du jeu de rapports, vous devez créer un nouveau fichier Report.cfg.

Vous devez spécifier dans le [!DNL Report.cfg] fichier le moment et le mode de génération et de distribution des rapports pour le jeu de rapports.

**Pour créer un nouveau fichier Report.cfg**

1. Dans les outils de données, ouvrez le fichier [!DNL Profile Manager] en cliquant avec le bouton droit dans un espace de travail et en cliquant sur **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. Cliquez sur **[!UICONTROL Reports]** pour ouvrir le [!DNL Reports] dossier.
1. Cliquez sur le dossier correspondant à votre jeu de rapports.
1. Dans la [!DNL User] colonne du dossier du jeu de rapports, cliquez avec le bouton droit de la souris et choisissez **[!UICONTROL Create]** > **[!UICONTROL Report]**. Un nouveau [!DNL Report.cfg] fichier apparaît dans la [!DNL File]colonne.
1. Dans la [!DNL User] colonne du nouveau [!DNL Report.cfg] fichier, cliquez avec le bouton droit de la souris sur la coche du [!DNL Report.cfg] fichier, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Infos sur l’étape](assets/cfg_reportcfg.png)

1. Modifiez les paramètres de configuration suivant vos besoins. Pour plus d’informations sur ces paramètres, voir Paramètres [](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.

   >[!NOTE]
   >
   >L’exemple [!DNL Report.cfg] illustré dans cet exemple contient uniquement les paramètres inclus dans le [!DNL Report.cfg] fichier par défaut. Si vous devez ajouter des paramètres supplémentaires à un [!DNL Report.cfg] fichier, vous devez le faire à l’aide d’un éditeur de texte. Pour connaître les étapes à suivre, voir [Modification des fichiers](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)Report.cfg existants.

1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL Report.cfg (modified)]** en haut du fichier et en cliquant sur **[!UICONTROL Save as Reports\]***&lt;**[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. Fermez le fichier.
1. Dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche de la [!DNL User] colonne du nouveau [!DNL Report.cfg] fichier et sélectionnez **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
