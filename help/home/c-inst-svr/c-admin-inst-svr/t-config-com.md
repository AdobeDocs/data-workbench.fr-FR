---
description: Le fichier de configuration des communications, Communications.cfg, contient les paramètres réseau du serveur Insight et le chemin d’accès au fichier Access Control.cfg.
title: Configuration des communications
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Configuration des communications{#configuring-communications}

Le fichier de configuration des communications, Communications.cfg, contient les paramètres réseau du serveur Insight et le chemin d’accès au fichier Access Control.cfg.

Ces paramètres vous aident à vous connecter à [!DNL Insight Server].

**Fréquence recommandée :** uniquement si nécessaire

**Pour afficher et modifier les paramètres de communication dans[!DNL Insight]**

1. Dans [!DNL Insight], dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l’espace de travail Gestionnaire de serveurs.
1. Cliquez avec le bouton droit de la souris sur l’icône [!DNL Insight Server] que vous souhaitez configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans la balise [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour en visualiser le contenu. Le fichier [!DNL Communications.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit sur la coche dans la colonne *nom du serveur* pour [!DNL Communications.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche s’affiche dans la colonne [!DNL Temp] pour [!DNL Communications.cfg].
1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans la fenêtre [!DNL Communications.cfg], cliquez sur **[!UICONTROL component]** pour en visualiser le contenu.
1. Modifiez les paramètres, si nécessaire. Pour plus d’informations sur les paramètres disponibles dans ce fichier, voir [Paramètres de configuration des communications](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![Infos sur l’étape](assets/cfg_communications_examplevalues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans la balise [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]***.
