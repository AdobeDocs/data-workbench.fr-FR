---
description: Le fichier de configuration des communications, Communications.cfg, contient les paramètres réseau du serveur Insight et le chemin d’accès au fichier Access Control.cfg.
title: Configuration des communications
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Configuration des communications{#configuring-communications}

{{eol}}

Le fichier de configuration des communications, Communications.cfg, contient les paramètres réseau du serveur Insight et le chemin d’accès au fichier Access Control.cfg.

Ces paramètres vous aident à vous connecter à [!DNL Insight Server].

**Fréquence recommandée :** Lorsque cela est nécessaire

**Pour afficher et modifier les paramètres de communication dans[!DNL Insight]**

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .
1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] vous souhaitez configurer et cliquer sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour afficher son contenu. Le [!DNL Communications.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* column pour [!DNL Communications.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la variable [!DNL Temp] column pour [!DNL Communications.cfg].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans le [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans le [!DNL Communications.cfg] fenêtre, cliquez sur **[!UICONTROL component]** pour afficher son contenu.
1. Modifiez les paramètres, si nécessaire. Pour plus d’informations sur les paramètres disponibles dans ce fichier, voir [Paramètres de configuration des communications](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![Infos sur l’étape](assets/cfg_communications_examplevalues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans le [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
