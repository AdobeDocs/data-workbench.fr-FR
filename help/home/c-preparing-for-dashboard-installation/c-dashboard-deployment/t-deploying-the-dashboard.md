---
description: Procédure de déploiement du tableau de bord dans IIS.
solution: Analytics
title: Déploiement du tableau de bord
topic: Data workbench
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Déploiement du tableau de bord{#deploying-the-dashboard}

Procédure de déploiement du tableau de bord dans IIS.

1. Créez un dossier d’installation pour installer le tableau de bord, par exemple [!DNL c:\inetpub\wwwroot\dashboard].
1. Créez le pool d’applications du tableau de bord dans IIS.
1. Ouvrez la console du Gestionnaire IIS.
1. Accédez à **[!UICONTROL Application Pools]**.
1. Sélectionnez **[!UICONTROL Add Application Pool…]**dans le **[!UICONTROL Actions]** menu à droite.
1. Dans le **[!UICONTROL Add Application Pool]** formulaire, utilisez le tableau de bord pour le nom et sélectionnez .NET Framework v.4.0.xxxx comme version du .NET Framework.
1. Laissez les autres champs comme champs par défaut et cliquez sur **[!UICONTROL OK]** pour créer le pool d’applications.
1. Déployez l’application du tableau de bord.
1. Ouvrez la console du Gestionnaire IIS.
1. Développez le dossier **[!UICONTROL Default Web Site]**, vous devriez voir le dossier que vous avez créé dans c:\inetpub\wwwroot\dashboard by default.
1. Cliquez avec le bouton droit sur le dossier et sélectionnez **[!UICONTROL Convert to Application]**.
1. Sélectionnez le **[!UICONTROL Application Pool]**créé à l’étape 2 (par exemple, &quot;Tableau de bord&quot;).
1. Sous **[!UICONTROL Sites]**, cliquez avec le bouton droit sur le site Web sur lequel vous souhaitez effectuer le déploiement (par exemple, &quot;Site Web par défaut&quot;).
1. Select **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Recherchez et sélectionnez le fichier de déploiement du tableau de bord fourni par Adobe.
1. Cliquez **[!UICONTROL Next]** deux fois pour accéder à l’écran Saisir les informations sur l’application.
1. Dans cet écran, vous pouvez choisir de personnaliser le déploiement de votre tableau de bord.
1. Pour **[!UICONTROL Application Path]** cela, saisissez le nom du dossier précédemment sélectionné.
1. Sous **[!UICONTROL Disable Automatic Database Upgrade]**, entrez `False`, puisqu’il s’agit d’une nouvelle installation.
1. Personnalisez votre chaîne de connexion, si nécessaire. Par exemple :

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Cliquez sur **[!UICONTROL Next]** et IIS commencera à installer l’application.
1. Une fois l’installation terminée, aucune erreur ne doit s’afficher dans le journal d’installation.
