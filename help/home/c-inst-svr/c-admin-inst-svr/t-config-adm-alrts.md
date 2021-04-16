---
description: Les alertes administratives envoient des notifications par courrier électronique aux adresses électroniques spécifiées lorsque des erreurs sont détectées par le serveur Insight au cours d’une opération normale.
title: Configuration des alertes administratives
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 2%

---

# Configuration des alertes administratives{#configuring-administrative-alerts}

Les alertes administratives envoient des notifications par courrier électronique aux adresses électroniques spécifiées lorsque des erreurs sont détectées par le serveur Insight au cours d’une opération normale.

**Fréquence recommandée :** avant production

>[!NOTE]
>
>L&#39;utilisation d&#39;alertes administratives requiert que [!DNL Insight Server] ait accès à un serveur SMTP de transfert pour envoyer des alertes par courrier électronique.

Les destinataires des notifications par courrier électronique doivent être les principaux responsables de l&#39;administration des systèmes et les Principaux intervenants.

Le fichier Alertes d&#39;administration, [!DNL Administrative Alerts.cfg], est utilisé pour configurer les alertes d&#39;administration pour [!DNL Insight Server].

>[!NOTE]
>
>Si vous exécutez un cluster, vous devez créer ou modifier des alertes sur le maître [!DNL Insight Server] du cluster.

**Pour créer ou modifier une alerte administrative**

1. Dans [!DNL Insight], sur l&#39;onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l&#39;espace de travail Servers Manager.
1. Cliquez avec le bouton droit de la souris sur l&#39;icône [!DNL Insight Server] que vous souhaitez configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour en vue le contenu. Le fichier [!DNL Administrative Alerts.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche de la colonne *nom du serveur *pour [!DNL Administrative Alerts.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la colonne [!DNL Temp] pour [!DNL Administrative Alerts.cfg].
1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans la fenêtre [!DNL Administrative Alerts.cfg], cliquez sur **[!UICONTROL component]** pour en vue le contenu.
1. Renseignez les paramètres selon vos besoins. Pour une liste des paramètres disponibles dans ce fichier, voir [Paramètres de configuration des alertes administratives](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491).

   ![Infos sur l’étape](assets/cfg_adminalerts_examplevalues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la colonne [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

1. (Facultatif) Si vous travaillez dans une grappe et souhaitez que les mêmes alertes administratives soient appliquées à chaque unité de traitement des données, vous devez copier et coller le fichier [!DNL Administrative Alerts.cfg] mis à jour dans le dossier [!DNL Components for Processing Servers] du répertoire d&#39;installation maître [!DNL Insight Server].
