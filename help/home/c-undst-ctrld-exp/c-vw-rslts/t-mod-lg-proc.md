---
description: Vous devez ajouter le champ x-experience au fichier Log Processing.cfg, qui sert à créer une dimension étendue.
solution: Insight,Analytics
title: Modification du traitement du journal.cfg
topic: Data workbench
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modification du traitement du journal.cfg{#modifying-log-processing-cfg}

Vous devez ajouter le champ x-experience au fichier Log Processing.cfg, qui sert à créer une dimension étendue.

Voir [Modification du fichier Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Pour modifier Log Processing.cfg**

1. Dans [!DNL Insight]la, ouvrez l’ [!DNL Profile Manager] en cliquant avec le bouton droit dans un espace de travail et en cliquant **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**, ou en ouvrant l’espace de travail Gestion des profils dans l’ [!DNL Admin] onglet.
1. Dans la [!DNL Profile Manager], cliquez **[!UICONTROL Dataset]** pour afficher son contenu.
1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL Log Processing.cfg] , puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La [!DNL Log Processing.cfg] fenêtre s&#39;affiche.
1. Cliquez sur **[!UICONTROL Fields]** pour afficher son contenu.
1. Cliquez avec le bouton droit de la souris sur le dernier champ de la liste active et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Saisissez x-experience dans le champ nouvellement créé, comme illustré dans l’exemple suivant :

   ![Infos sur l’étape](assets/logprocessing.png)

1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
1. Dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Log Processing.cfg] dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* pour enregistrer les modifications apportées localement au profil de travail.

   >[!NOTE]
   >
   >Le jeu de données commence immédiatement à être retraité.

   Pour plus d&#39;informations sur le traitement du journal et les champs, consultez le Guide *de configuration des jeux de* données.

