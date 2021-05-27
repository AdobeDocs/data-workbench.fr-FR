---
description: Procédure d’enregistrement et d’exécution du serveur de rapports.
title: Enregistrement du serveur de rapports en tant que service Windows
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Enregistrement du serveur de rapports en tant que service Windows{#registering-report-server-as-a-windows-service}

Procédure d’enregistrement et d’exécution du serveur de rapports.

Avant d’effectuer cette procédure, identifiez le compte Windows sous lequel le service [!DNL Report Server] s’exécutera. Assurez-vous que ce compte dispose des autorisations appropriées pour accéder à l’emplacement de stockage des rapports générés (c’est-à-dire, n’utilisez pas la balise [!DNL Local System Account]).

Suivez la procédure ci-dessous pour démarrer [!DNL Report Server]. Lorsque vous démarrez [!DNL Report Server] pour la première fois, il s’enregistre automatiquement en tant que service Windows.

Lorsque vous démarrez [!DNL Report Server] pour la première fois, il se connecte automatiquement au serveur de licences d’Adobe pour enregistrer votre certificat numérique. Pour que le processus d’enregistrement soit terminé, votre machine doit être connectée à Internet lorsque vous exécutez les étapes suivantes.

1. Sous Windows, accédez au répertoire dans lequel vous avez installé [!DNL Report Server].

   Exemple : D:\Adobe\Report

1. Double-cliquez sur **[!UICONTROL ReportServer.exe]**.
1. Pour vérifier que [!DNL Report Server] s’exécute correctement, cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Cette séquence de commandes peut varier en fonction de la version de Windows utilisée.
1. Dans la liste des services, recherchez l’entrée [!DNL Report Server] et vérifiez que son état est Démarré et que son type de démarrage est Automatique.
1. Procédez comme suit pour spécifier le compte utilisateur sous lequel [!DNL Report Server] s’exécutera :

   1. Double-cliquez sur **[!UICONTROL Report Server]** pour ouvrir la fenêtre [!DNL Properties].

   1. Sélectionnez l’onglet **[!UICONTROL Log On]** .
   1. Sélectionnez le bouton radio **[!UICONTROL This account]** .
   1. Saisissez ou recherchez le nom du compte. Ce compte doit disposer des autorisations nécessaires pour accéder à l’emplacement de stockage des rapports générés.

      >[!NOTE]
      >
      >Si [!DNL Report Server] distribue les rapports sous la forme de fichiers Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx]), assurez-vous que le compte dispose également des autorisations nécessaires pour exécuter Microsoft Excel.

   1. Saisissez et confirmez le mot de passe du compte.
   1. Cliquez sur **[!UICONTROL OK]**.

1. Cliquez avec le bouton droit sur le service [!DNL Report Server] et sélectionnez **[!UICONTROL Restart]** pour redémarrer le service sous le compte que vous avez spécifié.
1. Pour vérifier si [!DNL Report Server] a rencontré des erreurs au démarrage, cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Cette séquence de commandes peut varier en fonction de la version de Windows utilisée.

   1. Dans le volet gauche de la fenêtre [!DNL Event Viewer], sélectionnez le Journal des applications.
   1. Dans le volet de droite, recherchez les événements avec Adobe dans la colonne [!DNL Source].
   1. Si vous trouvez une erreur provenant d&#39;Adobe, double-cliquez sur l&#39;erreur pour afficher la fenêtre [!DNL Event Properties]. Cette fenêtre fournit des informations détaillées sur l’erreur.

      >[!NOTE]
      >
      >Une fois le service [!DNL Report Server] démarré, le fichier [!DNL ReportServer.log] est créé dans le répertoire Serveur de rapports [!DNL Trace] . Ce fichier est également utile pour résoudre les problèmes liés à [!DNL Report Server].

Vous avez terminé l’installation de [!DNL Report Server]. [!DNL Report Server] est conçu pour fonctionner en continu. Si vous redémarrez la machine, [!DNL Report Server] redémarre automatiquement. Si vous devez démarrer et arrêter [!DNL Report Server] manuellement, vous pouvez le faire à l’aide du panneau de configuration [!DNL Services] sous Windows.
