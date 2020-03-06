---
description: Le fichier de configuration Communications, Communications.cfg, contient les paramètres réseau du serveur Insight et le chemin d’accès au fichier Access Control.cfg.
solution: Insight
title: Configuration des communications
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration des communications{#configuring-communications}

Le fichier de configuration Communications, Communications.cfg, contient les paramètres réseau du serveur Insight et le chemin d’accès au fichier Access Control.cfg.

Ces paramètres vous aident à vous connecter à [!DNL Insight Server].

**Fréquence recommandée :** Uniquement si nécessaire

**Pour afficher et modifier les paramètres de communication dans[!DNL Insight]**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs.
1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] fichier à configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans la [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en afficher le contenu. Le [!DNL Communications.cfg] fichier se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom *du* serveur [!DNL Communications.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Communications.cfg].
1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans la [!DNL Communications.cfg] fenêtre, cliquez **[!UICONTROL component]** pour en afficher le contenu.
1. Modifiez les paramètres, le cas échéant. Pour plus d’informations sur les paramètres disponibles dans ce fichier, voir Paramètres [de configuration des](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1)communications.

   ![Infos sur l’étape](assets/cfg_communications_examplevalues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL Temp] colonne et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

