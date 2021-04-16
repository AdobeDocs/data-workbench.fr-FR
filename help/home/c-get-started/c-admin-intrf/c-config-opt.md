---
description: L’option Configuration ouvre votre fichier Insight.cfg, qui contrôle vos connexions à divers serveurs.
title: Option de configuration
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 2%

---

# Option de configuration{#configuration-option}

L’option Configuration ouvre votre fichier Insight.cfg, qui contrôle vos connexions à divers serveurs.

![](assets/cfg_Workstation.png)

**Pour modifier le fichier Insight.cfg**

1. Dans la fenêtre [!DNL Insight.cfg], modifiez les paramètres selon vos besoins. Pour obtenir des descriptions détaillées des paramètres du fichier [!DNL Insight.cfg], voir [Paramètres de configuration Insight](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Pour enregistrer vos paramètres de configuration, cliquez avec le bouton droit de la souris sur **[!UICONTROL Insight.cfg (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save as Insight.cfg]**.

**Pour ajouter de nouveaux serveurs**

1. Dans la fenêtre [!DNL Insight.cfg], cliquez avec le bouton droit de la souris sur **[!UICONTROL Servers]** et cliquez sur **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Remplissez ou modifiez les paramètres du serveur pour permettre au Data Workbench d’accéder au serveur de votre choix. Pour obtenir des descriptions détaillées des paramètres du fichier [!DNL Insight.cfg], voir [Paramètres de configuration Insight](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Répétez les étapes 1 et 2 pour chaque serveur auquel vous souhaitez configurer une connexion.
1. Pour enregistrer vos paramètres de configuration, cliquez avec le bouton droit de la souris sur **[!UICONTROL Insight.cfg (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save as Insight.cfg]**.

Le Data Workbench tente de se connecter au ou aux serveurs en utilisant les paramètres que vous avez spécifiés. Si une connexion est établie, un noeud vert apparaît dans le [!DNL Servers Manager] comme illustré ci-dessous. Si le Data Workbench ne peut pas se connecter au serveur, un noeud rouge s’affiche.

![](assets/vis_SysStat_RedGreenDots.png)
