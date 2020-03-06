---
description: Les alertes d’administration envoient des notifications par courrier électronique aux adresses électroniques spécifiées lorsque des erreurs sont détectées par le serveur Insight au cours d’une opération normale.
solution: Insight
title: Configuration des alertes administratives
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration des alertes administratives{#configuring-administrative-alerts}

Les alertes d’administration envoient des notifications par courrier électronique aux adresses électroniques spécifiées lorsque des erreurs sont détectées par le serveur Insight au cours d’une opération normale.

**Fréquence recommandée :** Avant la production

>[!NOTE]
>
>L’utilisation d’alertes d’administration requiert que [!DNL Insight Server] vous ayez accès à un serveur SMTP de transfert pour envoyer des alertes par courrier électronique.

Les destinataires des notifications par courrier électronique doivent être des administrateurs système clés et des parties prenantes principales.

Le fichier Alertes d’administration [!DNL Administrative Alerts.cfg]sert à configurer les alertes d’administration pour [!DNL Insight Server].

>[!NOTE]
>
>Si vous exécutez une grappe, vous devez créer ou modifier des alertes sur le maître [!DNL Insight Server] de la grappe.

**Pour créer ou modifier une alerte administrative**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** vignette pour ouvrir l’espace de travail Gestionnaire de serveurs.
1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] fichier à configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans la [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en afficher le contenu. Le [!DNL Administrative Alerts.cfg] fichier se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne *nom du serveur * [!DNL Administrative Alerts.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Administrative Alerts.cfg].
1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans la [!DNL Administrative Alerts.cfg] fenêtre, cliquez **[!UICONTROL component]** pour en afficher le contenu.
1. Renseignez les paramètres suivant vos besoins. Pour obtenir la liste des paramètres disponibles dans ce fichier, voir Paramètres [de configuration des alertes](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491)d’administration.

   ![Infos sur l’étape](assets/cfg_adminalerts_examplevalues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL Temp] colonne et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

1. (Facultatif) Si vous travaillez dans une grappe et souhaitez que les mêmes alertes administratives soient appliquées à chaque unité de traitement des données, vous devez copier et coller le [!DNL Administrative Alerts.cfg] fichier mis à jour dans le [!DNL Components for Processing Servers] dossier du répertoire [!DNL Insight Server] d’installation maître.