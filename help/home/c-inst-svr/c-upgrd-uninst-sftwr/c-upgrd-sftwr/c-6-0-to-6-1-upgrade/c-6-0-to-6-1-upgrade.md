---
description: Procédez comme suit pour effectuer la mise à jour vers Data Workbench v6.1 à partir de votre installation de Data Workbench v6.0x.
title: Mise à niveau de Data Workbench 6.0 vers 6.1
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
exl-id: 559e1942-561c-4270-9670-550177730cdb,2a337d2e-c70e-4f35-a6c2-c3a7f50a0800
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 1%

---

# Mise à niveau de Data Workbench 6.0 vers 6.1{#data-workbench-to-upgrade}

{{eol}}

Procédez comme suit pour effectuer la mise à jour vers Data Workbench v6.1 à partir de votre installation de Data Workbench v6.0x.

**Étape 1**: [Mise à niveau du serveur](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Étape 2**: [Mise à niveau du serveur de rapports](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Étape 3**: [Mise à niveau du client](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Les composants serveur, serveur de rapports et client sont mis à niveau pour s’exécuter sur des systèmes d’exploitation Windows 64 bits.

## Mise à niveau du serveur {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Procédez comme suit pour mettre à jour la variable **[!UICONTROL Server v6.1]** composants :

1. En utilisant la variable **[!UICONTROL Software and Docs]** , ouvrez le profil **[!UICONTROL Start Here]** workspace et téléchargez tous les packages de serveur nécessaires dans un dossier local.

   * Télécharger **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** fichiers zip et extraire tous les fichiers.

      Le package Serveur comprend **[!UICONTROL Lookup]** et **[!UICONTROL Profile]** dossiers avec **[!UICONTROL Base]** et **[!UICONTROL Transform]** profils pour mettre à jour le serveur.

      * Téléchargez la **[!UICONTROL Profiles]** dossiers.
      * Téléchargez la **[!UICONTROL Lookup]** dossiers.
      * Téléchargez la **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** module.
      * Télécharger d’autres **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]**, et **[!UICONTROL Dashboard]** fichiers selon les besoins de votre système.

1. Arrêtez le **[!UICONTROL Adobe Insight Server]** service.

   ![](assets/install_server_download1.png)

1. À partir du fichier téléchargé **[!UICONTROL Server]** package :

   1. Remplacez la variable [!DNL Server\Bin] pour mettre à jour le dossier [!DNL InsightServer64.exe] et les fichiers annexes.

   1. Remplacez la variable [!DNL Server\Profiles] dossier. Vous pouvez remplacer tous les fichiers.
   1. Mettez à jour le [!DNL Server\Lookups] dossier. Vous souhaiterez ajouter les fichiers nouvellement téléchargés aux fichiers personnalisés déjà situés dans le dossier.
   1. Remplacez la variable [!DNL Server\Software] dossier à mettre à jour [!DNL Insight.exe] et [!DNL ReportServer.exe]
   1. Mettez à jour le [!DNL Server\Scripts] dossier à mettre à jour [!DNL TnTSend.exe].

1. Si vous utilisez **[!UICONTROL DeviceAtlas]**, vous devrez alors [mettre à jour le lot](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md) situé dans le [!DNL Server\Lookups] dossier.

1. Configurez la variable [!DNL Profile.cfg] pour vous assurer que le vecteur est mis à jour afin de refléter le nombre d’éléments pour chaque profil.

   Par exemple, pour activer la fonction **[!UICONTROL Predictive Analytics]** vous devez mettre à jour ce paramètre.

   ```
   Directories = vector: 5 items
       0 = string: Base\\
       1 = string: Geography\\
       2 = string: Predictive Analytics\\
       3 = string: Adobe SC\\
       4 = string: Profile Name\\
   ```

1. Configurez et enregistrez le fichier PAServer.cfg pour la fonctionnalité Analyses prédictives.

   Si vous souhaitez envoyer des tâches Predictive Analytics aux serveurs, vous devez configurer la variable [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] pour gérer les envois de mise en grappe côté serveur.

   Le profil personnalisé doit hériter des paramètres du profil de configuration Analytics prédictif, ce qui vous permet de configurer et d’enregistrer le [!DNL PAServer.cfg] en fonction de l’implémentation de votre site.

1. Définissez les **[!UICONTROL Log Source ID]**.

   Le **[!UICONTROL Recording of Rows per Log Source]** a été ajouté dans **[!UICONTROL v6.04]** et défini dans le [!DNL Log Processing.cfg] en ajoutant un nom unique **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Si l’identifiant de source de journal n’est pas défini, l’erreur suivante s’affiche :

   ```
   Missing Log Source ID in log processing.cfg.
   Log Source ID must be defined for all log sources.
   ```

1. Parce que la variable [!DNL EventMessages.dll] a été mis à jour. il est nécessaire que vous annuliez l’enregistrement, puis que vous inscriviez la variable **[!UICONTROL Adobe Insight Server]** sur l’ensemble de la grappe.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Démarrez le **[!UICONTROL Adobe Insight Server]** sur l’ensemble de la grappe.

L’installation du serveur est maintenant terminée.

## Mise à niveau du serveur de rapports {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Avant la mise à niveau vers **[!UICONTROL Report Server v6.1]**, vous devez d’abord effectuer la mise à niveau vers **[!UICONTROL Server v6.1]**.

1. En utilisant la variable **[!UICONTROL Software and Docs]** profil, téléchargement **[!UICONTROL v6.1]** de la **[!UICONTROL Report Server]** vers un dossier local.

1. Copier **[!UICONTROL Report Server 6.1]** à partir du package téléchargé et remplacez les packages de profil.

   >[!NOTE]
   >
   >Le [!DNL Insight.zbin] dans le fichier [!DNL install] Le dossier est un fichier de sauvegarde utilisé pour la localisation et doit être présent dans la variable [!DNL install] répertoire . Ce fichier ou autre [!DNL .zbin] seront utilisés en fonction des paramètres de ligne de commande transmis lors du démarrage.

1. (facultatif) Data Workbench prend actuellement en charge l’anglais (-en-us) et le chinois (-zh-cn). Vous devez définir une police pour prendre en charge les caractères codés sur un ou deux octets :

   ```
   Report Server.cfg - Add Fonts
      Fonts = vector: 2 items
      0 = string: SimSun
      1 = string: Arial
   ```

   Les polices répertoriées doivent également être installées sur le système d’exploitation Windows.

1. Configurer [!DNL Report Server v6.1] pour la localisation.

   1. Arrêtez le **[!UICONTROL Adobe Insight Report Server]** service.
   1. Lancez une invite de commande en tant qu’&quot;Administrateur&quot;.
   1. Accédez au serveur de rapports [!DNL install] dossier.
   1. Supprimez le service Serveur de rapports à l’aide de la commande suivante :

      ```
      ReportServer.exe /unregserver
      ```

   1. Démarrez le service en fonction des paramètres de langue :

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Pour vérifier que le serveur de rapports s’exécute avec les paramètres appropriés, ouvrez **[!UICONTROL Windows Service Manager]** et cliquez avec le bouton droit **[!UICONTROL Adobe Insight Report Server - Properties]**. Le chemin d’accès au fichier exécutable affiche les paramètres de ligne de commande mis à jour.

L’installation du serveur de rapports est maintenant terminée.

## Mise à niveau client {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Avant la mise à niveau vers **[!UICONTROL Client v6.1]**, l’administrateur doit d’abord effectuer la mise à niveau vers **[!UICONTROL Insight Server v6.1.]**

1. Launch [!DNL Insight.exe] mais ne vous connectez à aucun profil.
1. Modifiez la variable [!DNL Insight.cfg] fichier .

   ```
   Update Software = bool: true
   ```

1. Connectez-vous à votre profil.

   Autoriser le client à se synchroniser avec le serveur et votre client sera mis à niveau avec les derniers profils client v6.1, les exécutables et les fichiers de configuration.

   >[!NOTE]
   >
   >Le [!DNL Insight.zbin] dans le fichier [!DNL install] Le dossier est un fichier de sauvegarde utilisé pour la localisation et doit être présent. Ce fichier ou autre [!DNL .zbin] seront utilisés en fonction des paramètres de ligne de commande transmis lors du démarrage.

   Voir [configuration des langues localisées](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) pour ajouter une [!DNL insight.zbin] fichier requis pour les paramètres localisés.

**Paramètres client supplémentaires**

Avant de configurer [!DNL Insight.exe] et les fichiers annexes, vous devez quitter l’application cliente.

Pour installer le chinois simplifié :

1. Créez un raccourci qui transmet le paramètre de ligne de commande au [!DNL Insight.exe] fichier .

   ```
   Insight.exe -zh-cn
   ```

1. Configurer [!DNL Insight.cfg] pour prendre en charge les caractères de police à un et deux octets.

   Data Workbench prend actuellement en charge le chinois simplifié et l’anglais. Vous pouvez sélectionner des polices pour prendre en charge ces deux langues :

   ```
   Fonts = vector: 2 items
   0 = string: SimSun
   1 = string: Arial
   ```

   Les polices demandées doivent également être installées sur le système d’exploitation Windows.

1. Lancez le raccourci que vous avez créé pour synchroniser les profils et la mise à jour . [!DNL zbin] fichier .

Pour utiliser l’éditeur de méthode d’entrée (IME).

IME vous permet de saisir des caractères internationaux.

1. Mettez à jour le [!DNL Insight.cfg] avec les paramètres suivants :

   ```
   Localized IME = bool: true
   ```

1. Lancer le raccourci créé pour synchroniser les profils et la mise à jour [!DNL .zbin] fichier .

L’installation du client est maintenant terminée.
