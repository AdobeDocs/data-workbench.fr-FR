---
description: Procédez comme suit pour mettre à jour l’outil de données v6.1 à partir de votre installation v6.0x.
title: Mise à niveau de Data Workbench 6.0 vers 6.1
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
exl-id: 559e1942-561c-4270-9670-550177730cdb,2a337d2e-c70e-4f35-a6c2-c3a7f50a0800
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 1%

---

# Mise à niveau de Data Workbench 6.0 vers 6.1{#data-workbench-to-upgrade}

Procédez comme suit pour mettre à jour l’outil de données v6.1 à partir de votre installation v6.0x.

**Étape 1** :  [Mise à niveau du serveur](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Étape 2** :  [Mise à niveau du serveur de rapports](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Étape 3** :  [Mise à niveau du client](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Les composants serveur, serveur de rapports et client sont mis à niveau pour s’exécuter sur des systèmes d’exploitation Windows 64 bits.

## Mise à niveau du serveur {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Pour mettre à jour les composants **[!UICONTROL Server v6.1]**, procédez comme suit :

1. A l&#39;aide du profil **[!UICONTROL Software and Docs]**, ouvrez l&#39;espace de travail **[!UICONTROL Start Here]** et téléchargez tous les packages de serveur nécessaires dans un dossier local.

   * Téléchargez **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** dossiers zip et extrayez tous les fichiers.

      Le package de serveur comprend des dossiers **[!UICONTROL Lookup]** et **[!UICONTROL Profile]** avec des profils **[!UICONTROL Base]** et **[!UICONTROL Transform]** pour mettre à jour le serveur.

      * Téléchargez les dossiers **[!UICONTROL Profiles]**.
      * Téléchargez les dossiers **[!UICONTROL Lookup]**.
      * Téléchargez le package **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]**.
      * Téléchargez d’autres fichiers **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]** et **[!UICONTROL Dashboard]** si nécessaire pour votre système.

1. Arrêtez le service **[!UICONTROL Adobe Insight Server]**.

   ![](assets/install_server_download1.png)

1. A partir du package **[!UICONTROL Server]** téléchargé :

   1. Remplacez le dossier [!DNL Server\Bin] pour mettre à jour [!DNL InsightServer64.exe] et les fichiers associés.

   1. Remplacez le dossier [!DNL Server\Profiles]. Vous pouvez remplacer tous les fichiers.
   1. Mettez à jour le dossier [!DNL Server\Lookups]. Vous souhaitez ajouter les fichiers nouvellement téléchargés aux fichiers personnalisés qui se trouvent déjà dans le dossier.
   1. Remplacez le dossier [!DNL Server\Software] par [!DNL Insight.exe] et [!DNL ReportServer.exe].
   1. Mettez à jour le dossier [!DNL Server\Scripts] pour mettre à jour [!DNL TnTSend.exe].

1. Si vous utilisez **[!UICONTROL DeviceAtlas]**, vous devrez [mettre à jour le lot](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) situé dans le dossier [!DNL Server\Lookups].

1. Configurez le fichier [!DNL Profile.cfg] pour vous assurer que le vecteur est mis à jour afin de refléter le nombre d’éléments pour chaque profil.

   Par exemple, pour activer le profil **[!UICONTROL Predictive Analytics]**, vous devez mettre à jour ce paramètre.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configurez et enregistrez le fichier PAServer.cfg pour la fonctionnalité Analyses prédictives.

   Si vous souhaitez envoyer des tâches d’analyse prédictive aux serveurs, vous devez configurer le fichier [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] pour gérer les envois de mise en grappe côté serveur.

   Le profil personnalisé doit hériter des paramètres du profil de configuration d’Analyses prédictives, ce qui vous permet de configurer et d’enregistrer le fichier [!DNL PAServer.cfg] en fonction de l’implémentation de votre site.

1. Définissez les **[!UICONTROL Log Source ID]**.

   Le **[!UICONTROL Recording of Rows per Log Source]** a été ajouté dans **[!UICONTROL v6.04]** et défini dans le fichier [!DNL Log Processing.cfg] du profil personnalisé en ajoutant un nom unique **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Si l&#39;ID de source du journal n&#39;est pas défini, vous obtenez l&#39;erreur suivante :

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. Comme [!DNL EventMessages.dll] a été mis à jour, vous devez annuler l&#39;enregistrement, puis enregistrer **[!UICONTROL Adobe Insight Server]** dans la grappe.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Début du service **[!UICONTROL Adobe Insight Server]** sur l’ensemble de la grappe.

L&#39;installation du serveur est maintenant terminée.

## Mise à niveau du serveur de rapports {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Avant de procéder à la mise à niveau vers **[!UICONTROL Report Server v6.1]**, vous devez d’abord effectuer la mise à niveau vers **[!UICONTROL Server v6.1]**.

1. A l’aide du profil **[!UICONTROL Software and Docs]**, téléchargez **[!UICONTROL v6.1]** du package **[!UICONTROL Report Server]** dans un dossier local.

1. Copiez **[!UICONTROL Report Server 6.1]** du package téléchargé et remplacez les packages de profil.

   >[!NOTE]
   >
   >Le fichier [!DNL Insight.zbin] du dossier [!DNL install] est un fichier de sauvegarde utilisé pour la localisation et doit être présent dans le répertoire [!DNL install]. Ce fichier ou d&#39;autres fichiers [!DNL .zbin] seront utilisés en fonction des paramètres de ligne de commande transmis au démarrage.

1. (Facultatif) Les outils de données prennent actuellement en charge l’anglais (-en-us) et le chinois (-zh-cn). Vous devez définir une police pour prendre en charge les caractères simples et doublon-octets :

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   Les polices répertoriées doivent également être installées sur le système d’exploitation Windows.

1. Configurer [!DNL Report Server v6.1] pour la localisation.

   1. Arrêtez le service **[!UICONTROL Adobe Insight Report Server]**.
   1. Lancez une invite de commande en tant qu&#39;&quot;administrateur&quot;.
   1. Accédez au dossier Serveur de rapports [!DNL install].
   1. Supprimez le service Report Server à l’aide de la commande suivante :

      ```
      ReportServer.exe /unregserver
      ```

   1. Début du service en fonction des paramètres de langue :

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)  
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Pour vérifier que le serveur de rapports fonctionne avec les paramètres appropriés, ouvrez **[!UICONTROL Windows Service Manager]** et cliquez avec le bouton droit de la souris sur **[!UICONTROL Adobe Insight Report Server - Properties]**. Le chemin d&#39;accès à l&#39;exécutable affiche les paramètres de ligne de commande mis à jour.

L’installation du serveur de rapports est maintenant terminée.

## Mise à niveau du client {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Avant la mise à niveau vers **[!UICONTROL Client v6.1]**, l’administrateur doit d’abord effectuer la mise à niveau vers **[!UICONTROL Insight Server v6.1.]**

1. Lancez [!DNL Insight.exe] mais ne vous connectez à aucun profil.
1. Modifiez le fichier [!DNL Insight.cfg].

   ```
   Update Software = bool: true
   ```

1. Connectez-vous à votre profil.

   Permettre au client de se synchroniser avec le serveur et mettre à niveau votre client avec les derniers profils client v6.1, les exécutables et les fichiers de configuration.

   >[!NOTE]
   >
   >Le fichier [!DNL Insight.zbin] du dossier [!DNL install] est un fichier de sauvegarde utilisé pour la localisation et doit être présent. Ce fichier ou d&#39;autres fichiers [!DNL .zbin] seront utilisés en fonction des paramètres de ligne de commande transmis au démarrage.

   Voir [configuration des langues localisées](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) pour ajouter un fichier [!DNL insight.zbin] requis pour les paramètres localisés.

**Paramètres client supplémentaires**

Avant de configurer [!DNL Insight.exe] et les fichiers de prise en charge, vous devez quitter l’application cliente.

Pour installer le chinois simplifié :

1. Créez un raccourci qui passe dans le paramètre de ligne de commande au fichier [!DNL Insight.exe].

   ```
   Insight.exe -zh-cn
   ```

1. Configurez [!DNL Insight.cfg] pour qu’il prenne en charge les caractères de police sur un et doublon octet.

   Les outils de données prennent actuellement en charge l’anglais et le chinois simplifié. Vous pouvez sélectionner des polices pour les deux langues suivantes :

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

   Les polices demandées doivent également être installées sur le système d’exploitation Windows.

1. Lancez le raccourci que vous avez créé pour synchroniser les profils et la mise à jour. [!DNL zbin] fichier.

Pour utiliser l’éditeur de méthode d’entrée (IME).

IME vous permet de saisir des caractères internationaux.

1. Mettez à jour le fichier [!DNL Insight.cfg] avec les paramètres suivants :

   ```
   Localized IME = bool: true
   ```

1. Lancez le raccourci que vous avez créé pour synchroniser les profils et le fichier [!DNL .zbin] mis à jour.

L’installation du client est maintenant terminée.
