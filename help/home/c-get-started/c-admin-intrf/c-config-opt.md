---
description: L’option Configuration ouvre votre fichier Insight.cfg, qui contrôle vos connexions à différents serveurs.
title: Option de configuration
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 2%

---

# Option de configuration{#configuration-option}

{{eol}}

L’option Configuration ouvre votre fichier Insight.cfg, qui contrôle vos connexions à différents serveurs.

![](assets/cfg_Workstation.png)

**Modification du fichier Insight.cfg**

1. Dans le [!DNL Insight.cfg] modifiez les paramètres en fonction de vos besoins. Pour des descriptions détaillées des paramètres de la variable [!DNL Insight.cfg] fichier, voir [Paramètres de configuration Insight](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Pour enregistrer vos paramètres de configuration, cliquez avec le bouton droit de la souris **[!UICONTROL Insight.cfg (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save as Insight.cfg]**.

**Ajout de nouveaux serveurs**

1. Dans le [!DNL Insight.cfg] fenêtre, clic droit **[!UICONTROL Servers]** et cliquez sur **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Complétez ou modifiez les paramètres du serveur pour permettre au Data Workbench d’accéder au serveur souhaité. Pour des descriptions détaillées des paramètres de la variable [!DNL Insight.cfg] fichier, voir [Paramètres de configuration Insight](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Répétez les étapes 1 et 2 pour chaque serveur auquel vous souhaitez configurer une connexion.
1. Pour enregistrer vos paramètres de configuration, cliquez avec le bouton droit de la souris **[!UICONTROL Insight.cfg (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save as Insight.cfg]**.

Data Workbench tente de se connecter au ou aux serveurs à l’aide des paramètres que vous avez spécifiés. Si une connexion est établie, un noeud vert apparaît dans la variable [!DNL Servers Manager] comme illustré ci-dessous. Si Data Workbench ne parvient pas à se connecter au serveur, un noeud rouge s’affiche.

![](assets/vis_SysStat_RedGreenDots.png)
