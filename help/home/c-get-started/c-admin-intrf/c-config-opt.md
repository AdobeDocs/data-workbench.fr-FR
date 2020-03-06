---
description: L’option Configuration ouvre votre fichier Insight.cfg, qui contrôle vos connexions aux différents serveurs.
solution: Analytics
title: Option de configuration
topic: Data workbench
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Option de configuration{#configuration-option}

L’option Configuration ouvre votre fichier Insight.cfg, qui contrôle vos connexions aux différents serveurs.

![](assets/cfg_Workstation.png)

**Pour modifier le fichier Insight.cfg**

1. Dans la [!DNL Insight.cfg] fenêtre, modifiez les paramètres selon vos besoins. Pour obtenir des descriptions détaillées des paramètres du [!DNL Insight.cfg] fichier, voir Paramètres [de configuration d’](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)Insight.
1. Pour enregistrer vos paramètres de configuration, cliquez avec le bouton droit **[!UICONTROL Insight.cfg (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save as Insight.cfg]**.

**Pour ajouter de nouveaux serveurs**

1. Dans la [!DNL Insight.cfg] fenêtre, cliquez avec le bouton droit **[!UICONTROL Servers]** et cliquez sur **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Remplissez ou modifiez les paramètres du serveur pour permettre aux outils de données d’accéder au serveur souhaité. Pour obtenir des descriptions détaillées des paramètres du [!DNL Insight.cfg] fichier, voir Paramètres [de configuration d’](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)Insight.
1. Répétez les étapes 1 et 2 pour chaque serveur auquel vous souhaitez configurer une connexion.
1. Pour enregistrer vos paramètres de configuration, cliquez avec le bouton droit **[!UICONTROL Insight.cfg (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save as Insight.cfg]**.

Les outils de données tentent de se connecter au(x) serveur(s) à l’aide des paramètres que vous avez spécifiés. Si une connexion est établie, un noeud vert s’affiche dans le [!DNL Servers Manager] comme illustré ci-dessous. Si les outils de données ne peuvent pas se connecter au serveur, un noeud rouge s’affiche.

![](assets/vis_SysStat_RedGreenDots.png)

