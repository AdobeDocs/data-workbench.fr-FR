---
description: Les alertes administratives envoient des notifications par courrier électronique aux adresses électroniques spécifiées lorsque des erreurs sont détectées par le serveur Insight au cours du fonctionnement normal.
title: Configuration des alertes administratives
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 2%

---

# Configuration des alertes administratives{#configuring-administrative-alerts}

{{eol}}

Les alertes administratives envoient des notifications par courrier électronique aux adresses électroniques spécifiées lorsque des erreurs sont détectées par le serveur Insight au cours du fonctionnement normal.

**Fréquence recommandée :** Avant production

>[!NOTE]
>
>L’utilisation des alertes administratives requiert que : [!DNL Insight Server] a accès à un serveur SMTP de transfert pour envoyer des alertes par email.

Les destinataires des notifications par e-mail doivent être des membres clés de l’administration du système et des Principaux intervenants.

le fichier des alertes administratives, [!DNL Administrative Alerts.cfg], est utilisé pour configurer les alertes administratives pour [!DNL Insight Server].

>[!NOTE]
>
>Si vous exécutez une grappe, vous devez créer ou modifier des alertes sur le maître. [!DNL Insight Server] dans la grappe.

**Pour créer ou modifier une alerte d’administration**

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .
1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] vous souhaitez configurer et cliquer sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour afficher son contenu. Le [!DNL Administrative Alerts.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit sur la coche dans la colonne *nom du serveur* pour [!DNL Administrative Alerts.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la variable [!DNL Temp] column pour [!DNL Administrative Alerts.cfg].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans le [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans le [!DNL Administrative Alerts.cfg] fenêtre, cliquez sur **[!UICONTROL component]** pour afficher son contenu.
1. Renseignez les paramètres suivant vos besoins. Pour obtenir la liste des paramètres disponibles dans ce fichier, voir [Paramètres de configuration des alertes administratives](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491).

   ![Infos sur l’étape](assets/cfg_adminalerts_examplevalues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans le [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

1. (Facultatif) Si vous travaillez dans une grappe et souhaitez que les mêmes alertes administratives soient appliquées à chaque unité de traitement des données, vous devez copier et coller la mise à jour. [!DNL Administrative Alerts.cfg] dans le fichier [!DNL Components for Processing Servers] dossier dans le maître [!DNL Insight Server] répertoire d’installation.
