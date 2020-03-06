---
description: Le fichier de configuration DPU, DPU.cfg, spécifie divers paramètres de performances pour Insight Server.
solution: Insight
title: Configuration de DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration de DPU.cfg{#configuring-dpu-cfg}

Le fichier de configuration DPU, DPU.cfg, spécifie divers paramètres de performances pour Insight Server.

La manière dont vous définissez ces paramètres dépend de la taille de votre jeu de données et de nombreux autres facteurs. Contactez les services de conseil Adobe pour obtenir de l’aide sur l’optimisation des performances.

**Fréquence recommandée :** Uniquement si nécessaire

**Pour modifier les paramètres de performances[!DNL Insight Server]DPU**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** vignette pour ouvrir l’espace de travail Gestionnaire de serveurs.
1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] fichier à configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans la [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en afficher le contenu. Le [!DNL DPU.cfg] fichier se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom *du* serveur [!DNL DPU.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL DPU.cfg].
1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans la [!DNL DPU.cfg] fenêtre, cliquez sur le composant pour en afficher le contenu.
1. Modifiez les paramètres de performances et de chemin, le cas échéant. Pour obtenir la liste des paramètres disponibles dans ce fichier, voir Paramètres [de performance](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1)DPU.

   >[!NOTE]
   >
   >Veuillez contacter Adobe avant de modifier les paramètres de ce fichier.

   ![](assets/cfg_DPU_egvalues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL Temp] colonne et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

