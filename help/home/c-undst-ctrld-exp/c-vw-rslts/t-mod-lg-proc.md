---
description: Vous devez ajouter le champ x-experience au fichier Log Processing.cfg, qui sert à créer une dimension étendue.
solution: Analytics,Analytics
title: Modification du journal de traitement.cfg
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# Modification du journal de traitement.cfg{#modifying-log-processing-cfg}

Vous devez ajouter le champ x-experience au fichier Log Processing.cfg, qui sert à créer une dimension étendue.

Voir [Modification de Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Pour modifier Log Processing.cfg**

1. Dans [!DNL Insight], ouvrez [!DNL Profile Manager] en cliquant avec le bouton droit dans un espace de travail et en cliquant sur **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**, ou en ouvrant l&#39;espace de travail Gestion de Profil sous l&#39;onglet [!DNL Admin].
1. Dans le [!DNL Profile Manager], cliquez sur **[!UICONTROL Dataset]** pour afficher son contenu.
1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL Log Processing.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La fenêtre [!DNL Log Processing.cfg] s&#39;affiche.
1. Cliquez sur **[!UICONTROL Fields]** pour afficher son contenu.
1. Cliquez avec le bouton droit sur le dernier champ de la liste active et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Tapez x-experience dans le nouveau champ, comme illustré dans l&#39;exemple suivant :

   ![Infos sur l’étape](assets/logprocessing.png)

1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
1. Dans la colonne [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Log Processing.cfg] de la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]*** pour enregistrer les modifications apportées localement au profil de travail.

   >[!NOTE]
   >
   >Le jeu de données commence à être retraité immédiatement.

   Pour plus d&#39;informations sur le traitement du journal et les champs, consultez le *Guide de configuration des jeux de données*.
