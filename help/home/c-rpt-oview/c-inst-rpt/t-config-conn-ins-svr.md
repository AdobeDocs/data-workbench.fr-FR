---
description: Avant de pouvoir générer des rapports et des alertes, vous devez configurer le serveur de rapports pour spécifier l’adresse du serveur Insight et identifier les profils sur lesquels vous souhaitez qu’il effectue des rapports.
title: Configuration de la connexion à Insight Server
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
exl-id: a398a665-fe09-448a-977c-b0f9de4add09
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---

# Configuration de la connexion à Insight Server{#configuring-the-connection-to-the-insight-server}

{{eol}}

Avant de pouvoir générer des rapports et des alertes, vous devez configurer le serveur de rapports pour spécifier l’adresse du serveur Insight et identifier les profils sur lesquels vous souhaitez qu’il effectue des rapports.

>[!NOTE]
>
>Tant que vous n’avez pas configuré le serveur de rapports comme décrit ci-dessous, vous ne pouvez pas exécuter correctement le serveur de rapports. Si vous tentez d’exécuter Report Server avec le fichier non configuré installé avec le programme, Report Server génère un flux d’erreurs.

**Pour configurer le serveur de rapports**

1. Avec l’Explorateur Windows, accédez au répertoire dans lequel vous avez installé le serveur de rapports.
1. Ouvrez le [!DNL ReportServer.cfg] dans le Bloc-notes et modifiez le fichier suivant vos besoins.

   L’exemple suivant [!DNL Report Server.cfg] contient uniquement les paramètres inclus dans la variable [!DNL Report Server.cfg] par défaut (et met en surbrillance les paramètres requis). Si vous contactez le serveur de licences d’Adobe via un serveur proxy, vous devez ajouter le vecteur de licences et ses paramètres. Voir [Paramètres Report Server.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) pour obtenir une description détaillée.

   ```
   Fonts = vector: 0 items
   Gamma = float: 1.6
   Network Location = string: NetworkLocationName
   Servers = vector: 1 items
     0 = serverInfo:
       Address = string: ServerIPAddress
       Name = string: 
       Port = int: 443
       Proxy Address = string:
       Proxy Password = string:
       Proxy Port = int: 8080
       Proxy User Name = string:
       SSL Client Certificate = string: ReportCertFileName.pem
       SSL Server Common Name = string: ServerCommonName
       Use SSL = bool: true
   Result Memory Limit (KB) = double: 100000
   Maximum Slice Size = int: 30
   Use OpenGL Hardware Rendering = bool: true
   Reporting = :
     Profiles = vector: 1 items
       0 = ReportProfile:
         Server = string: ServerCommonName
         Profile = string: ProfileName
     Update Interval (minutes) = int: 10
     Completion Message Interval (seconds) = int: 600
     Status interval (seconds) = int: 600
     SMTP Server for Errors = string: SMTPServerHostName
     SMTP Server for Errors Username = string: SMTPServerUsername
     SMTP Server for Errors Password = string: SMTPServerPassword
     SMTP Server for Errors Send From = string: SenderAddress
     SMTP Server for Errors Send To = string: RecipientAddresses
   ```

1. Enregistrez le fichier, puis fermez-le.
