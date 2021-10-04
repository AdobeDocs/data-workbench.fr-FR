---
description: Procédez comme suit pour effectuer la mise à jour vers Data Workbench v6.1 à partir de votre installation de Data Workbench v6.0x.
title: Mise à niveau de Data Workbench 6.0 vers 6.1
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
exl-id: 559e1942-561c-4270-9670-550177730cdb,2a337d2e-c70e-4f35-a6c2-c3a7f50a0800
source-git-commit: b21da6d12175fa8570b1b366049baa9c8e8ea862
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 1%

---

# Mise à niveau de Data Workbench 6.0 vers 6.1{#data-workbench-to-upgrade}

Procédez comme suit pour effectuer la mise à jour vers Data Workbench v6.1 à partir de votre installation de Data Workbench v6.0x.

**Étape 1** :  [Mise à niveau du serveur](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Étape 2** :  [Mise à niveau du serveur de rapports](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Étape 3** :  [Mise à niveau du client](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Les composants serveur, serveur de rapports et client sont mis à niveau pour s’exécuter sur des systèmes d’exploitation Windows 64 bits.

## Mise à niveau du serveur {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Pour mettre à jour les composants **[!UICONTROL Server v6.1]**, procédez comme suit :

1. À l’aide du profil **[!UICONTROL Software and Docs]**, ouvrez l’espace de travail **[!UICONTROL Start Here]** et téléchargez tous les packages de serveur nécessaires dans un dossier local.

   * Téléchargez **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** dossiers zip et extrayez tous les fichiers.

      Le package Serveur comprend les dossiers **[!UICONTROL Lookup]** et **[!UICONTROL Profile]** avec les profils **[!UICONTROL Base]** et **[!UICONTROL Transform]** pour mettre à jour le serveur.

      * Téléchargez les dossiers **[!UICONTROL Profiles]**.
      * Téléchargez les dossiers **[!UICONTROL Lookup]**.
      * Téléchargez le package **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** .
      * Téléchargez des fichiers **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]** et **[!UICONTROL Dashboard]** supplémentaires si nécessaire pour votre système.

1. Arrêtez le service **[!UICONTROL Adobe Insight Server]**.

   ![](assets/install_server_download1.png)

1. À partir du package **[!UICONTROL Server]** téléchargé :

   1. Remplacez le dossier [!DNL Server\Bin] pour mettre à jour les fichiers [!DNL InsightServer64.exe] et les fichiers annexes.

   1. Remplacez le dossier [!DNL Server\Profiles]. Vous pouvez remplacer tous les fichiers.
   1. Mettez à jour le dossier [!DNL Server\Lookups]. Vous souhaiterez ajouter les fichiers nouvellement téléchargés aux fichiers personnalisés déjà situés dans le dossier.
   1. Remplacez le dossier [!DNL Server\Software] pour mettre à jour [!DNL Insight.exe] et [!DNL ReportServer.exe].
   1. Mettez à jour le dossier [!DNL Server\Scripts] pour mettre à jour [!DNL TnTSend.exe].

1. Si vous utilisez **[!UICONTROL DeviceAtlas]**, vous devez [mettre à jour le lot](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md) situé dans le dossier [!DNL Server\Lookups].

1. Configurez le fichier [!DNL Profile.cfg] pour vous assurer que le vecteur est mis à jour pour refléter le nombre d’éléments pour chaque profil.

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

   Si vous souhaitez envoyer des tâches Predictive Analytics aux serveurs, vous devez configurer le fichier [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] pour gérer les envois de mise en grappe côté serveur.

   Le profil personnalisé doit hériter des paramètres du profil de configuration Analytics prédictif, ce qui vous permet de configurer et d’enregistrer le fichier [!DNL PAServer.cfg] en fonction de l’implémentation de votre site.

1. Définissez les **[!UICONTROL Log Source ID]**.

   **[!UICONTROL Recording of Rows per Log Source]** a été ajouté dans **[!UICONTROL v6.04]** et défini dans le fichier [!DNL Log Processing.cfg] du profil personnalisé en ajoutant un nom unique **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Si l’identifiant de source de journal n’est pas défini, l’erreur suivante s’affiche :

   ```
   Missing Log Source ID in log processing.cfg.
   Log Source ID must be defined for all log sources.
   ```

1. Comme la balise [!DNL EventMessages.dll] a été mise à jour, vous devez annuler l’enregistrement, puis enregistrer la balise **[!UICONTROL Adobe Insight Server]** dans la grappe.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Démarrez le service **[!UICONTROL Adobe Insight Server]** sur l’ensemble de la grappe.

L’installation du serveur est maintenant terminée.

## Mise à niveau du serveur de rapports {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Avant de procéder à la mise à niveau vers **[!UICONTROL Report Server v6.1]**, vous devez d’abord effectuer la mise à niveau vers **[!UICONTROL Server v6.1]**.

1. À l’aide du profil **[!UICONTROL Software and Docs]**, téléchargez **[!UICONTROL v6.1]** du package **[!UICONTROL Report Server]** dans un dossier local.

1. Copiez **[!UICONTROL Report Server 6.1]** du package téléchargé et remplacez les packages de profil.

   >[!NOTE]
   >
   >Le fichier [!DNL Insight.zbin] du dossier [!DNL install] est un fichier de sauvegarde utilisé pour la localisation et doit être présent dans le répertoire [!DNL install]. Ce fichier ou d’autres fichiers [!DNL .zbin] seront utilisés en fonction des paramètres de ligne de commande transmis lors du démarrage.

1. (facultatif) Data Workbench prend actuellement en charge l’anglais (-en-us) et le chinois (-zh-cn). Vous devez définir une police pour prendre en charge les caractères codés sur un ou deux octets :

   ```
   Report Server.cfg - Add Fonts
      Fonts = vector: 2 items
      0 = string: SimSun
      1 = string: Arial
   ```

   Les polices répertoriées doivent également être installées sur le système d’exploitation Windows.

1. Configurez [!DNL Report Server v6.1] pour la localisation.

   1. Arrêtez le service **[!UICONTROL Adobe Insight Report Server]**.
   1. Lancez une invite de commande en tant qu’&quot;Administrateur&quot;.
   1. Accédez au dossier Serveur de rapports [!DNL install] .
   1. Supprimez le service Serveur de rapports à l’aide de la commande suivante :

      ```
      ReportServer.exe /unregserver
      ```

   1. Démarrez le service en fonction des paramètres de langue :

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Pour vérifier que le serveur de rapports s’exécute avec les paramètres appropriés, ouvrez **[!UICONTROL Windows Service Manager]** et cliquez avec le bouton droit de la souris sur **[!UICONTROL Adobe Insight Report Server - Properties]**. Le chemin d’accès au fichier exécutable affiche les paramètres de ligne de commande mis à jour.

L’installation du serveur de rapports est maintenant terminée.

## Mise à niveau client {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Avant la mise à niveau vers **[!UICONTROL Client v6.1]**, l’administrateur doit d’abord effectuer la mise à niveau vers **[!UICONTROL Insight Server v6.1.]**

1. Lancez [!DNL Insight.exe] mais ne vous connectez à aucun profil.
1. Modifiez le fichier [!DNL Insight.cfg] .

   ```
   Update Software = bool: true
   ```

1. Connectez-vous à votre profil.

   Autoriser le client à se synchroniser avec le serveur et votre client sera mis à niveau avec les derniers profils client v6.1, les exécutables et les fichiers de configuration.

   >[!NOTE]
   >
   >Le fichier [!DNL Insight.zbin] du dossier [!DNL install] est un fichier de sauvegarde utilisé pour la localisation et doit être présent. Ce fichier ou d’autres fichiers [!DNL .zbin] seront utilisés en fonction des paramètres de ligne de commande transmis lors du démarrage.

   Voir [configuration des langues localisées](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) pour ajouter un fichier [!DNL insight.zbin] requis pour les paramètres localisés.

**Paramètres client supplémentaires**

Avant de configurer [!DNL Insight.exe] et les fichiers annexes, vous devez quitter l’application cliente.

Pour installer le chinois simplifié :

1. Créez un raccourci qui transmet le paramètre de ligne de commande au fichier [!DNL Insight.exe].

   ```
   Insight.exe -zh-cn
   ```

1. Configurez [!DNL Insight.cfg] pour prendre en charge les caractères de police à un et deux octets.

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

1. Mettez à jour le fichier [!DNL Insight.cfg] avec les paramètres suivants :

   ```
   Localized IME = bool: true
   ```

1. Lancez le raccourci que vous avez créé pour synchroniser les profils et le fichier [!DNL .zbin] mis à jour.

L’installation du client est maintenant terminée.
