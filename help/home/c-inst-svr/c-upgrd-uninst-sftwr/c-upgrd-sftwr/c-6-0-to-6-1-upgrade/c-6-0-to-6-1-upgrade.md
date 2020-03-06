---
description: Pour effectuer la mise à jour vers la version 6.1 de l’outil de données à partir de votre installation de la version 6.0x, procédez comme suit.
solution: Analytics
title: Mise à niveau des outils de données version 6.0 à 6.1
topic: Data workbench
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Mise à niveau des outils de données version 6.0 à 6.1{#data-workbench-to-upgrade}

Pour effectuer la mise à jour vers la version 6.1 de l’outil de données à partir de votre installation de la version 6.0x, procédez comme suit.

**Étape 1**: Mise à niveau [du serveur](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Étape 2**: Mise à niveau [du serveur de rapports](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Étape 3**: Mise à niveau [du client](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Le serveur, le serveur de rapports et les composants client sont mis à niveau pour s’exécuter sur des systèmes d’exploitation Windows 64 bits.

## Mise à niveau du serveur {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Pour mettre à jour les **[!UICONTROL Server v6.1]** composants, procédez comme suit :

1. A l’aide du **[!UICONTROL Software and Docs]** profil, ouvrez l’ **[!UICONTROL Start Here]** espace de travail et téléchargez tous les packages de serveur nécessaires dans un dossier local.

   * Téléchargez **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** dossiers zip et extrayez tous les fichiers.

      Le package de serveur comprend **[!UICONTROL Lookup]** et **[!UICONTROL Profile]** des dossiers avec **[!UICONTROL Base]** **[!UICONTROL Transform]** et des profils pour mettre à jour le serveur.

      * Téléchargez les **[!UICONTROL Profiles]** dossiers.
      * Téléchargez les **[!UICONTROL Lookup]** dossiers.
      * Téléchargez le **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** package.
      * Téléchargez des fichiers supplémentaires **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]** et **[!UICONTROL Dashboard]** selon les besoins pour votre système.

1. Arrêtez le **[!UICONTROL Adobe Insight Server]** service.

   ![](assets/install_server_download1.png)

1. A partir du **[!UICONTROL Server]** package téléchargé :

   1. Remplacez le [!DNL Server\Bin] dossier pour mettre à jour les fichiers [!DNL InsightServer64.exe] et les fichiers de prise en charge.

   1. Remplacez le [!DNL Server\Profiles] dossier. Vous pouvez remplacer tous les fichiers.
   1. Mettez à jour le [!DNL Server\Lookups] dossier. Vous souhaiterez ajouter les fichiers nouvellement téléchargés aux fichiers personnalisés qui se trouvent déjà dans le dossier.
   1. Remplacez le [!DNL Server\Software] dossier à mettre à jour [!DNL Insight.exe] et [!DNL ReportServer.exe]
   1. Mettez à jour le [!DNL Server\Scripts] dossier à mettre à jour [!DNL TnTSend.exe].

1. Si vous utilisez **[!UICONTROL DeviceAtlas]**, vous devez [mettre à jour le lot](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) situé dans le [!DNL Server\Lookups] dossier.

1. Configurez le [!DNL Profile.cfg] fichier pour vous assurer que le vecteur est mis à jour afin de refléter le nombre d’éléments pour chaque profil.

   Par exemple, pour activer le **[!UICONTROL Predictive Analytics]** profil, vous devez mettre à jour ce paramètre.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configurez et enregistrez le fichier PAServer.cfg pour la fonctionnalité Analyses prédictives.

   Si vous souhaitez envoyer des tâches d’analyse prédictive aux serveurs, vous devez configurer le [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] fichier pour gérer les envois de mise en grappe côté serveur.

   Le profil personnalisé doit hériter des paramètres du profil de configuration d’Analyses prédictives, ce qui vous permet de configurer et d’enregistrer le [!DNL PAServer.cfg] fichier en fonction de l’implémentation de votre site.

1. Définissez les **[!UICONTROL Log Source ID]**.

   L’élément **[!UICONTROL Recording of Rows per Log Source]** a été ajouté **[!UICONTROL v6.04]** et défini dans le fichier [!DNL Log Processing.cfg] du profil personnalisé en ajoutant un nom unique **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Si l&#39;ID de source du journal n&#39;est pas défini, vous obtenez l&#39;erreur suivante :

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. Comme le [!DNL EventMessages.dll] fichier a été mis à jour, vous devez annuler l’enregistrement, puis l’enregistrer dans l’ **[!UICONTROL Adobe Insight Server]** ensemble de la grappe.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Démarrez le **[!UICONTROL Adobe Insight Server]** service sur la grappe.

L’installation du serveur est maintenant terminée.

## Mise à niveau du serveur de rapports {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Avant de procéder à la mise à niveau vers **[!UICONTROL Report Server v6.1]**, vous devez d’abord effectuer la mise à niveau vers **[!UICONTROL Server v6.1]**.

1. A l’aide du **[!UICONTROL Software and Docs]** profil, téléchargez **[!UICONTROL v6.1]** depuis le **[!UICONTROL Report Server]** package vers un dossier local.

1. Copiez **[!UICONTROL Report Server 6.1]** du package téléchargé et remplacez les packages de profil.

   >[!NOTE]
   >
   >Le [!DNL Insight.zbin] fichier du [!DNL install] dossier est un fichier de sauvegarde utilisé pour la localisation et doit être présent dans le [!DNL install] répertoire. Ce fichier ou d&#39;autres [!DNL .zbin] fichiers seront utilisés selon les paramètres de ligne de commande transmis au démarrage.

1. (Facultatif) Les outils de données prennent actuellement en charge l’anglais (-en-us) et le chinois (-zh-cn). Vous devez définir une police pour prendre en charge les caractères codés sur un ou deux octets :

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   Les polices répertoriées doivent également être installées sur le système d’exploitation Windows.

1. Configuration [!DNL Report Server v6.1] pour la localisation.

   1. Arrêtez le **[!UICONTROL Adobe Insight Report Server]** service.
   1. Lancez une invite de commande en tant qu’administrateur.
   1. Accédez au [!DNL install] dossier Serveur de rapports.
   1. Supprimez le service Report Server à l’aide de la commande suivante :

      ```
      ReportServer.exe /unregserver
      ```

   1. Démarrez le service en fonction des paramètres de langue :

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)  
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Pour vérifier que le serveur de rapports est en cours d’exécution avec les paramètres corrects, ouvrez **[!UICONTROL Windows Service Manager]** le serveur et cliquez avec le bouton droit de la souris **[!UICONTROL Adobe Insight Report Server - Properties]**. Le chemin d&#39;accès au fichier exécutable affiche les paramètres de ligne de commande mis à jour.

L’installation du serveur de rapports est maintenant terminée.

## Mise à niveau du client {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Avant de procéder à la mise à niveau vers **[!UICONTROL Client v6.1]**, l’administrateur doit d’abord effectuer la mise à niveau vers **[!UICONTROL Insight Server v6.1.]**

1. Lancez [!DNL Insight.exe] mais ne vous connectez à aucun profil.
1. Modifiez le [!DNL Insight.cfg] fichier.

   ```
   Update Software = bool: true
   ```

1. Connectez-vous à votre profil.

   Permet au client de se synchroniser avec le serveur et votre client sera mis à niveau avec les profils, exécutables et fichiers de configuration v6.1 les plus récents.

   >[!NOTE]
   >
   >Le [!DNL Insight.zbin] fichier du [!DNL install] dossier est un fichier de sauvegarde utilisé pour la localisation et doit être présent. Ce fichier ou d&#39;autres [!DNL .zbin] fichiers seront utilisés selon les paramètres de ligne de commande transmis au démarrage.

   Voir [Configuration de langues](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) localisées pour ajouter un [!DNL insight.zbin] fichier requis pour les paramètres localisés.

**Paramètres client supplémentaires**

Avant de configurer [!DNL Insight.exe] et de prendre en charge les fichiers, vous devez quitter l’application cliente.

Pour installer le chinois simplifié :

1. Créez un raccourci qui transmet le paramètre de ligne de commande au [!DNL Insight.exe] fichier.

   ```
   Insight.exe -zh-cn
   ```

1. Configurez [!DNL Insight.cfg] pour prendre en charge les caractères de police sur un et deux octets.

   Les outils de données prennent actuellement en charge l’anglais et le chinois simplifié. Vous pouvez sélectionner des polices pour prendre en charge les deux langues suivantes :

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

   Les polices demandées doivent également être installées sur le système d’exploitation Windows.

1. Lancez le raccourci que vous avez créé pour synchroniser les profils et la mise à jour. [!DNL zbin] fichier.

Pour utiliser l’éditeur de méthode d’entrée (IME).

IME vous permet de saisir des caractères internationaux.

1. Mettez à jour le [!DNL Insight.cfg] fichier avec les paramètres suivants :

   ```
   Localized IME = bool: true
   ```

1. Lancez le raccourci que vous avez créé pour synchroniser les profils et le [!DNL .zbin] fichier mis à jour.

L’installation du client est maintenant terminée.
