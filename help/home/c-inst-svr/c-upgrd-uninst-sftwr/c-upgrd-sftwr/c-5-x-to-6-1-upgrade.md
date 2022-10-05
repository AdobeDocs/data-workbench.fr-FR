---
description: Suivez ces étapes pour mettre à jour Data Workbench v6.1 à partir de votre installation d’Insight v5.5x.
title: Mise à niveau de Data Workbench 5.5 vers 6.1
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
exl-id: c730f6d5-2171-4d97-a967-509dc2517c86,3f25917b-b929-4e3b-84f0-1a81b30ba641
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 1%

---

# Mise à niveau de Data Workbench 5.5 vers 6.1{#data-workbench-to-upgrade}

{{eol}}

Suivez ces étapes pour mettre à jour Data Workbench v6.1 à partir de votre installation d’Insight v5.5x.

**Étape 1**: [Mise à niveau du serveur](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**Étape 2**: [Mise à niveau du serveur de rapports](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Étape 3**: [Mise à niveau client](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Les composants serveur, serveur de rapports et client sont mis à niveau pour s’exécuter sur des systèmes d’exploitation Windows 64 bits.

## Mise à niveau du serveur {#section-08bd6fe3da8740fcb19688e8cac6f223}

Procédez comme suit pour mettre à jour la variable **[!UICONTROL Server v6.1]** composants :

1. En utilisant la variable **[!UICONTROL Software and Docs]** , ouvrez le profil **[!UICONTROL Start Here]** workspace et téléchargez tous les packages de serveur nécessaires dans un dossier local.

   * Télécharger **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** fichiers zip et extraire tous les fichiers.

      Le **[!UICONTROL Server]** package comprend **[!UICONTROL Lookup]** et **[!UICONTROL Profile]** avec la propriété **[!UICONTROL Base]** et **[!UICONTROL Transform]** fichiers de recherche à ajouter et à remplacer pour mettre à jour le serveur.

   * Télécharger **[!UICONTROL Profiles]** dossiers.
   * Télécharger mis à jour **[!UICONTROL Lookup]** dossiers.
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
1. Définir [!DNL Directories] dans le [!DNL Profile.cfg] pour vous assurer que le vecteur est mis à jour afin de refléter le nombre d’éléments pour chaque profil.

   Par exemple, pour activer la fonction **[!UICONTROL Predictive Analytics]** vous devez mettre à jour ce paramètre.

   ```
   Directories = vector: 5 items
       0 = string: Base\\
       1 = string: Geography\\
       2 = string: Predictive Analytics\\
       3 = string: Adobe SC\\
       4 = string: Profile Name\\
   ```

1. Configurez et enregistrez le [!DNL PAServer.cfg] pour mettre à niveau la fonctionnalité Analytics prédictif.

   Si vous souhaitez envoyer des tâches Predictive Analytics aux serveurs, vous devez configurer la variable [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] pour gérer les envois de mise en grappe côté serveur.

   Le profil personnalisé doit hériter des paramètres du profil de configuration Analytics prédictif, ce qui vous permet de configurer et d’enregistrer le [!DNL PAServer.cfg] en fonction de la mise en oeuvre de votre site.

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

1. (Facultatif) Modifiez le fichier de configuration du serveur de rapports pour prendre en charge les caractères codés sur deux octets.

   Data Workbench prend actuellement en charge l’anglais (-en-us) et le chinois (-zh-cn). Vous devez définir une police pour prendre en charge les caractères codés sur un ou deux octets :

   ```
   Report Server.cfg - Add Fonts
      Fonts = vector: 2 items
      0 = string: SimSun
      1 = string: Arial
   ```

   Les polices répertoriées doivent également être installées sur le système d’exploitation Windows.

1. Configuration [!DNL Report Server v6.1].

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
>Avant la mise à niveau vers **[!UICONTROL Client v6.1]**, l’administrateur doit d’abord effectuer la mise à niveau vers **[!UICONTROL Server v6.1.]**

1. Launch [!DNL Insight.exe] mais NE vous connectez à aucun profil.
1. Modifiez la variable [!DNL Insight.cfg] pour ne pas mettre automatiquement à jour le logiciel.

   ```
   Update Software = bool: false
   ```

1. Se connecter à **[!UICONTROL Software and Docs]** profile (softdocs).
1. Télécharger [!DNL Software\Insight Client\v6.10].
1. (facultatif) Modifier [!DNL insight.cfg] pour prendre en charge les caractères codés sur deux octets.

   Data Workbench prend actuellement en charge le chinois simplifié et l’anglais. Sélectionnez les polices pour prendre en charge ces deux langues :

   ```
   Fonts = vector: 2 items
   0 = string: SimSun
   1 = string: Arial
   ```

1. Quittez le client.
1. Copiez les fichiers du fichier téléchargé. **v6.1** du module client au [!DNL Install] dossier.

   >[!NOTE]
   >
   >Le [!DNL Insight.zbin] Le fichier du dossier d’installation est un fichier de sauvegarde utilisé pour la localisation et doit être présent dans le répertoire d’installation. Ce fichier ou autre [!DNL .zbin] seront utilisés en fonction des paramètres de ligne de commande transmis lors du démarrage.
   >
   >Par exemple, pour lancer le chinois simplifié, créez un raccourci qui passe dans le paramètre de ligne de commande.
   >
   >
   ```
   >Insight.exe -zh-cn
   >```
   >
   >Si vous souhaitez lancer en anglais (par défaut), aucun changement de ligne de commande n’est nécessaire.

1. Launch [!DNL Insight.exe] pour l’anglais ou le raccourci que vous avez créé pour une autre langue.
1. Connectez-vous à votre profil et autorisez le client à se synchroniser avec le serveur.
1. (Facultatif) Pour utiliser l’IME, apportez ces modifications à la variable [!DNL Insight.cfg] fichier :

   ```
   Localized IME = bool: true
   ```

   L’éditeur de méthode d’entrée (IME) vous permet de saisir des caractères internationaux.

1. (facultatif) Modifiez la variable [!DNL Insight.cfg] pour mettre automatiquement à jour le logiciel :

   ```
   Update Software = bool: true
   ```

   Voir les instructions pour la mise en oeuvre de l’IME.
1. Redémarrez après la synchronisation des profils pour utiliser la plus récente [!DNL .zbin] fichier .

L’installation du client est maintenant terminée.
