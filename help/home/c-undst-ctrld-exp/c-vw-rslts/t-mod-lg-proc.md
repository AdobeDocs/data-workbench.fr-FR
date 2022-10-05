---
description: Vous devez ajouter le champ x-expérience au fichier Log Processing.cfg, utilisé pour créer une dimension étendue.
solution: Analytics
title: Modification du journal de traitement.cfg
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# Modification du journal de traitement.cfg{#modifying-log-processing-cfg}

{{eol}}

Vous devez ajouter le champ x-expérience au fichier Log Processing.cfg, utilisé pour créer une dimension étendue.

Voir [Modification de Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Pour modifier Log Processing.cfg**

1. Dans [!DNL Insight], ouvrez le [!DNL Profile Manager] en cliquant avec le bouton droit dans un espace de travail, puis en cliquant sur **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** ou en ouvrant l’espace de travail de la gestion des profils sur le [!DNL Admin] .
1. Dans le [!DNL Profile Manager], cliquez sur **[!UICONTROL Dataset]** pour afficher son contenu.
1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL Log Processing.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .
1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Le [!DNL Log Processing.cfg] s’affiche.
1. Cliquez sur **[!UICONTROL Fields]** pour afficher son contenu.
1. Cliquez avec le bouton droit sur le dernier champ de la liste active, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Saisissez x-expérience dans le champ nouvellement créé, comme illustré dans l’exemple suivant :

   ![Infos sur l’étape](assets/logprocessing.png)

1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche pour [!DNL Log Processing.cfg] dans le [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* pour enregistrer les modifications apportées localement au profil de travail.

   >[!NOTE]
   >
   >Le jeu de données commence à être retraité immédiatement.

   Pour plus d’informations sur le traitement des journaux et les champs, voir *Guide de configuration des jeux de données*.
