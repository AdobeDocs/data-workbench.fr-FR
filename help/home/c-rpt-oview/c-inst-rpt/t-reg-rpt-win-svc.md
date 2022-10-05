---
description: Procédure d’enregistrement et d’exécution du serveur de rapports.
title: Enregistrement du serveur de rapports en tant que service Windows
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Enregistrement du serveur de rapports en tant que service Windows{#registering-report-server-as-a-windows-service}

{{eol}}

Procédure d’enregistrement et d’exécution du serveur de rapports.

Avant d’effectuer cette procédure, identifiez le compte Windows sous lequel la variable [!DNL Report Server] s’exécute. Assurez-vous que ce compte dispose des autorisations appropriées pour accéder à l’emplacement de stockage des rapports générés (c’est-à-dire, n’utilisez pas la variable [!DNL Local System Account]).

Suivez la procédure ci-dessous pour commencer. [!DNL Report Server]. Lorsque vous commencez [!DNL Report Server] pour la première fois, il s’enregistre automatiquement en tant que service Windows.

Lorsque vous commencez [!DNL Report Server] pour la première fois, il se connecte automatiquement au serveur de licences Adobe pour enregistrer votre certificat numérique. Pour que le processus d’enregistrement soit terminé, votre machine doit être connectée à Internet lorsque vous exécutez les étapes suivantes.

1. Sous Windows, accédez au répertoire dans lequel vous avez installé [!DNL Report Server].

   Exemple : D:\Adobe\Report

1. Double-cliquez **[!UICONTROL ReportServer.exe]**.
1. Pour confirmer que [!DNL Report Server] s’exécute correctement, cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Cette séquence de commandes peut varier en fonction de la version de Windows utilisée.
1. Dans la liste des services, recherchez l’entrée pour [!DNL Report Server] et vérifiez que son état est Démarré et que son type de démarrage est Automatique.
1. Procédez comme suit pour spécifier le compte d’utilisateur sous lequel [!DNL Report Server] s’exécutera :

   1. Double-cliquez **[!UICONTROL Report Server]** pour ouvrir le [!DNL Properties] fenêtre.

   1. Sélectionnez la **[!UICONTROL Log On]** .
   1. Sélectionnez la **[!UICONTROL This account]** bouton radio.
   1. Saisissez ou recherchez le nom du compte. Ce compte doit disposer des autorisations nécessaires pour accéder à l’emplacement de stockage des rapports générés.

      >[!NOTE]
      >
      >If [!DNL Report Server] distribue les rapports sous la forme Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx]), assurez-vous que le compte dispose également des autorisations nécessaires pour exécuter Microsoft Excel.

   1. Saisissez et confirmez le mot de passe du compte.
   1. Cliquez sur **[!UICONTROL OK]**.

1. Cliquez avec le bouton droit de la souris sur le [!DNL Report Server] service et sélectionnez **[!UICONTROL Restart]** pour redémarrer le service sous le compte que vous avez spécifié.
1. Pour vérifier si [!DNL Report Server] a rencontré des erreurs au démarrage, cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Cette séquence de commandes peut varier en fonction de la version de Windows utilisée.

   1. Dans le volet de gauche de la [!DNL Event Viewer] , sélectionnez le journal des applications.
   1. Dans le volet de droite, recherchez les événements avec Adobe dans la variable [!DNL Source] colonne .
   1. Si vous trouvez une erreur provenant d’Adobe, double-cliquez sur l’erreur pour afficher la variable [!DNL Event Properties] fenêtre. Cette fenêtre fournit des informations détaillées sur l’erreur.

      >[!NOTE]
      >
      >Après la [!DNL Report Server] Le service démarre, le fichier [!DNL ReportServer.log] est créé dans le serveur de rapports. [!DNL Trace] répertoire . Ce fichier est également utile pour résoudre les problèmes liés à [!DNL Report Server].

Vous avez terminé l’installation de [!DNL Report Server]. [!DNL Report Server] est conçu pour fonctionner en continu. Si vous redémarrez la machine, [!DNL Report Server] redémarre automatiquement. Si vous devez démarrer et arrêter [!DNL Report Server] manuellement, vous pouvez le faire à l’aide de la variable [!DNL Services] panneau de contrôle sous Windows.
