---
description: Le fichier de configuration DPU, DPU.cfg, spécifie divers paramètres de performances pour Insight Server.
title: Configuration de DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# Configuration de DPU.cfg{#configuring-dpu-cfg}

{{eol}}

Le fichier de configuration DPU, DPU.cfg, spécifie divers paramètres de performances pour Insight Server.

La manière dont vous définissez ces paramètres dépend de la taille de votre jeu de données et de nombreux autres facteurs. Veuillez contacter les services de conseil d’Adobe pour obtenir de l’aide sur l’optimisation des performances.

**Fréquence recommandée :** Lorsque cela est nécessaire

**Pour changer [!DNL Insight Server] Paramètres des performances DPU**

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .
1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] vous souhaitez configurer et cliquer sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour afficher son contenu. Le [!DNL DPU.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* column pour [!DNL DPU.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la variable [!DNL Temp] column pour [!DNL DPU.cfg].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans le [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans le [!DNL DPU.cfg] , cliquez sur le composant pour en afficher le contenu.
1. Modifiez les paramètres de performances et de chemin, si nécessaire. Pour obtenir la liste des paramètres disponibles dans ce fichier, voir [Paramètres des performances DPU](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1).

   >[!NOTE]
   >
   >Veuillez contacter Adobe avant de modifier les paramètres de ce fichier.

   ![](assets/cfg_DPU_egvalues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans le [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
