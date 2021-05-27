---
description: Le fichier de configuration DPU, DPU.cfg, spécifie divers paramètres de performances pour Insight Server.
title: Configuration de DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# Configuration de DPU.cfg{#configuring-dpu-cfg}

Le fichier de configuration DPU, DPU.cfg, spécifie divers paramètres de performances pour Insight Server.

La manière dont vous définissez ces paramètres dépend de la taille de votre jeu de données et de nombreux autres facteurs. Veuillez contacter les services de conseil d’Adobe pour obtenir de l’aide sur l’optimisation des performances.

**Fréquence recommandée :** uniquement si nécessaire

**Pour modifier les paramètres de performances  [!DNL Insight Server] DPU**

1. Dans [!DNL Insight], dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l’espace de travail Gestionnaire de serveurs.
1. Cliquez avec le bouton droit de la souris sur l’icône [!DNL Insight Server] que vous souhaitez configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans la balise [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour en visualiser le contenu. Le fichier [!DNL DPU.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit sur la coche dans la colonne *nom du serveur* pour [!DNL DPU.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche s’affiche dans la colonne [!DNL Temp] pour [!DNL DPU.cfg].
1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans la fenêtre [!DNL DPU.cfg] , cliquez sur le composant pour en afficher le contenu.
1. Modifiez les paramètres de performances et de chemin, si nécessaire. Pour obtenir la liste des paramètres disponibles dans ce fichier, voir [Paramètres de performance DPU](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1).

   >[!NOTE]
   >
   >Veuillez contacter Adobe avant de modifier les paramètres de ce fichier.

   ![](assets/cfg_DPU_egvalues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans la balise [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]***.
