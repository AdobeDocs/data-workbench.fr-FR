---
description: Le fichier de configuration Communications, Communications.cfg, contient les paramètres réseau du serveur Insight et le chemin d’accès au fichier Contrôle d'accès.cfg.
solution: Analytics
title: Configuration des communications
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---


# Configuration des communications{#configuring-communications}

Le fichier de configuration Communications, Communications.cfg, contient les paramètres réseau du serveur Insight et le chemin d’accès au fichier Contrôle d&#39;accès.cfg.

Ces paramètres vous aident à vous connecter à [!DNL Insight Server].

**Fréquence recommandée :** Uniquement si nécessaire

**Pour vue et modifier les paramètres de communication dans[!DNL Insight]**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Servers Manager.
1. Cliquez avec le bouton droit de la souris sur l’icône de la [!DNL Insight Server] fenêtre à configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en vue le contenu. Le [!DNL Communications.cfg] fichier se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche de la colonne du nom *du* serveur [!DNL Communications.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Communications.cfg].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans la [!DNL Communications.cfg] fenêtre, cliquez **[!UICONTROL component]** pour en vue le contenu.
1. Modifiez les paramètres, si nécessaire. Pour plus d’informations sur les paramètres disponibles dans ce fichier, voir Paramètres [de configuration des](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1)communications.

   ![Infos sur l’étape](assets/cfg_communications_examplevalues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** de la souris en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL Temp] colonne et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

