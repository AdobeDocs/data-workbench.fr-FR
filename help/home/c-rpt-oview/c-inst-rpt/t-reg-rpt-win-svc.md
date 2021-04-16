---
description: Procédure d’enregistrement et d’exécution de Report Server.
title: Enregistrement du serveur de rapports en tant que service Windows
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Enregistrement du serveur de rapports en tant que service Windows{#registering-report-server-as-a-windows-service}

Procédure d’enregistrement et d’exécution de Report Server.

Avant d&#39;effectuer cette procédure, identifiez le compte Windows sous lequel le service [!DNL Report Server] s&#39;exécutera. Assurez-vous que ce compte dispose des autorisations appropriées pour accéder à l&#39;emplacement où les rapports générés sont stockés (c&#39;est-à-dire, n&#39;utilisez pas le [!DNL Local System Account]).

Suivez la procédure ci-dessous pour début [!DNL Report Server]. Lorsque vous début [!DNL Report Server] pour la première fois, il s&#39;enregistre automatiquement en tant que service Windows.

Lorsque vous début [!DNL Report Server] pour la première fois, il se connecte automatiquement au serveur de licence d’Adobe pour enregistrer votre certificat numérique. Pour que le processus d’enregistrement soit terminé, votre ordinateur doit être connecté à Internet lorsque vous exécutez les étapes suivantes.

1. Sous Windows, accédez au répertoire dans lequel vous avez installé [!DNL Report Server].

   Exemple : D:\Adobe\Report

1. Doublon-clic **[!UICONTROL ReportServer.exe]**.
1. Pour vérifier que [!DNL Report Server] s’exécute correctement, cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Cette séquence de commandes peut varier en fonction de la version de Windows que vous utilisez.
1. Dans la liste de service, recherchez l’entrée [!DNL Report Server] et vérifiez que son état est Démarré et que son type de démarrage est Automatique.
1. Procédez comme suit pour spécifier le compte utilisateur sous lequel [!DNL Report Server] s&#39;exécutera :

   1. Cliquez sur **[!UICONTROL Report Server]** doublon pour ouvrir la fenêtre [!DNL Properties].

   1. Sélectionnez l&#39;onglet **[!UICONTROL Log On]**.
   1. Sélectionnez le bouton radio **[!UICONTROL This account]**.
   1. Tapez ou recherchez le nom du compte. Ce compte doit avoir l&#39;autorisation d&#39;accéder à l&#39;emplacement où les rapports générés sont stockés.

      >[!NOTE]
      >
      >Si [!DNL Report Server] distribue des rapports sous la forme de fichiers Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx]), assurez-vous que le compte est également autorisé à exécuter Microsoft Excel.

   1. Saisissez et confirmez le mot de passe du compte.
   1. Cliquez sur **[!UICONTROL OK]**.

1. Cliquez avec le bouton droit sur le service [!DNL Report Server] et sélectionnez **[!UICONTROL Restart]** pour redémarrer le service sous le compte que vous avez spécifié.
1. Pour vérifier si [!DNL Report Server] a rencontré des erreurs au cours du début, cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Cette séquence de commandes peut varier en fonction de la version de Windows que vous utilisez.

   1. Dans le volet gauche de la fenêtre [!DNL Event Viewer], sélectionnez le journal des applications.
   1. Dans le volet de droite, recherchez des événements avec Adobe dans la colonne [!DNL Source].
   1. Si vous trouvez une erreur de l&#39;Adobe, doublon-cliquez sur l&#39;erreur pour afficher la fenêtre [!DNL Event Properties]. Cette fenêtre fournit des informations détaillées sur l&#39;erreur.

      >[!NOTE]
      >
      >Après les débuts de service [!DNL Report Server], le fichier [!DNL ReportServer.log] est créé dans le répertoire Report Server [!DNL Trace]. Ce fichier est également utile pour résoudre les problèmes liés à [!DNL Report Server].

Vous avez terminé l&#39;installation de [!DNL Report Server]. [!DNL Report Server] est conçu pour fonctionner en continu. Si vous redémarrez l&#39;ordinateur, [!DNL Report Server] redémarre automatiquement. Si vous devez début et arrêter [!DNL Report Server] manuellement, vous pouvez le faire à l&#39;aide du panneau de configuration [!DNL Services] de Windows.
