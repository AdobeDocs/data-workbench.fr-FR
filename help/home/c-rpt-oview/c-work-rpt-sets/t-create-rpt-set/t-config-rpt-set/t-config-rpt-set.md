---
description: Après avoir créé et enregistré les espaces de travail dans le dossier du jeu de rapports, vous devez créer un fichier Report.cfg .
title: Configurer le jeu de rapports
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Configurer le jeu de rapports{#configure-the-report-set}

{{eol}}

Après avoir créé et enregistré les espaces de travail dans le dossier du jeu de rapports, vous devez créer un fichier Report.cfg .

Vous devez spécifier dans la variable [!DNL Report.cfg] pour le jeu de rapports, quand et comment les rapports doivent être générés et distribués.

**Pour créer un nouveau Report.cfg**

1. Dans Data Workbench, ouvrez le [!DNL Profile Manager] en cliquant avec le bouton droit dans un espace de travail, puis en cliquant sur **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. Cliquez sur **[!UICONTROL Reports]** pour ouvrir le [!DNL Reports] dossier.
1. Cliquez sur le dossier de votre jeu de rapports.
1. Dans le [!DNL User] pour le dossier du jeu de rapports, cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Create]** > **[!UICONTROL Report]**. Une nouvelle [!DNL Report.cfg] apparaît dans le [!DNL File]colonne .
1. Dans le [!DNL User] pour la nouvelle colonne [!DNL Report.cfg] , cliquez avec le bouton droit de la souris sur la coche correspondant au [!DNL Report.cfg] , puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Infos sur l’étape](assets/cfg_reportcfg.png)

1. Modifiez les paramètres de configuration suivant vos besoins. Pour plus d’informations sur ces paramètres, voir [Paramètres Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >L’exemple [!DNL Report.cfg] illustré dans cet exemple contient uniquement les paramètres inclus dans la variable [!DNL Report.cfg] par défaut. Si vous devez ajouter des paramètres supplémentaires à un [!DNL Report.cfg] , vous devez le faire à l’aide d’un éditeur de texte. Pour connaître les étapes à suivre, voir [Modification de fichiers Report.cfg existants](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

1. Enregistrez le fichier en cliquant avec le bouton droit de la souris **[!UICONTROL Report.cfg (modified)]** dans la partie supérieure du fichier et en cliquant sur **[!UICONTROL Save as Reports\]***&lt; **[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. Fermez le fichier.
1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche dans la variable [!DNL User] pour la nouvelle colonne [!DNL Report.cfg] et sélectionnez **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
