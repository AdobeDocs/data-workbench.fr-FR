---
description: Procédure d’enregistrement et d’exécution du serveur de rapports.
solution: Analytics
title: Enregistrement du serveur de rapports en tant que service Windows
topic: Data workbench
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Enregistrement du serveur de rapports en tant que service Windows{#registering-report-server-as-a-windows-service}

Procédure d’enregistrement et d’exécution du serveur de rapports.

Avant d’effectuer cette procédure, identifiez le compte Windows sous lequel le [!DNL Report Server] service s’exécutera. Assurez-vous que ce compte dispose des autorisations appropriées pour accéder à l’emplacement où les rapports générés sont stockés (c’est-à-dire, n’utilisez pas le [!DNL Local System Account]).

Suivez la procédure ci-dessous pour commencer [!DNL Report Server]. Lorsque vous démarrez [!DNL Report Server] pour la première fois, il s’enregistre automatiquement en tant que service Windows.

Lorsque vous démarrez [!DNL Report Server] pour la première fois, il se connecte automatiquement au serveur de licences Adobe pour enregistrer votre certificat numérique. Pour réussir le processus d’enregistrement, votre ordinateur doit être connecté à Internet lorsque vous exécutez les étapes suivantes.

1. Sous Windows, accédez au répertoire dans lequel vous avez installé [!DNL Report Server].

   Exemple : D:\Adobe\Report

1. Double-click **[!UICONTROL ReportServer.exe]**.
1. Pour vérifier que [!DNL Report Server] l’exécution est correcte, cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Cette séquence de commandes peut varier selon la version de Windows utilisée.
1. Dans la liste des services, recherchez l’entrée correspondant [!DNL Report Server] et vérifiez que son état est Démarré et que son type de démarrage est Automatique.
1. Procédez comme suit pour spécifier le compte utilisateur sous lequel [!DNL Report Server] s’exécutera :

   1. Cliquez deux fois **[!UICONTROL Report Server]** pour ouvrir la [!DNL Properties] fenêtre.

   1. Sélectionnez l’ **[!UICONTROL Log On]** onglet.
   1. Sélectionnez le bouton **[!UICONTROL This account]** radio.
   1. Tapez ou recherchez le nom du compte. Ce compte doit avoir l’autorisation d’accéder à l’emplacement de stockage des rapports générés.

      >[!NOTE]
      >
      >Si [!DNL Report Server] les rapports sont distribués sous la forme de fichiers Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx]), assurez-vous que le compte est également autorisé à exécuter Microsoft Excel.

   1. Saisissez et confirmez le mot de passe du compte.
   1. Cliquez sur **[!UICONTROL OK]**.

1. Cliquez avec le bouton droit sur le [!DNL Report Server] service et sélectionnez **[!UICONTROL Restart]** pour redémarrer le service sous le compte que vous avez spécifié.
1. Pour vérifier si [!DNL Report Server] des erreurs ont eu lieu au démarrage, cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Cette séquence de commandes peut varier selon la version de Windows utilisée.

   1. Dans le volet gauche de la [!DNL Event Viewer] fenêtre, sélectionnez le journal des applications.
   1. Dans le volet de droite, recherchez des événements avec Adobe dans la [!DNL Source] colonne.
   1. Si vous trouvez une erreur d’Adobe, cliquez deux fois sur l’erreur pour afficher la [!DNL Event Properties] fenêtre. Cette fenêtre fournit des informations détaillées sur l’erreur.

      >[!NOTE]
      >
      >Une fois le [!DNL Report Server] service démarré, le fichier [!DNL ReportServer.log] est créé dans le répertoire du serveur de rapports [!DNL Trace] . Ce fichier est également utile pour résoudre les problèmes liés à [!DNL Report Server].

Vous avez terminé l&#39;installation de [!DNL Report Server]. [!DNL Report Server] est conçue pour fonctionner en continu. Si vous redémarrez l’ordinateur, [!DNL Report Server] redémarre automatiquement. Si vous devez démarrer et arrêter [!DNL Report Server] manuellement, vous pouvez le faire à l’aide du panneau de [!DNL Services] contrôle de Windows.
