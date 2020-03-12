---
description: Pour effectuer une mise à jour vers la version 6.1 de l’outil de données à partir de votre installation d’Insight v5.5x, procédez comme suit.
solution: Analytics
title: Mise à niveau des outils de données 5.5 vers 6.1
topic: Data workbench
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Mise à niveau des outils de données 5.5 vers 6.1{#data-workbench-to-upgrade}

Pour effectuer une mise à jour vers la version 6.1 de l’outil de données à partir de votre installation d’Insight v5.5x, procédez comme suit.

**Étape 1**: Mise à niveau [du serveur](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**Étape 2**: Mise à niveau du serveur de [rapports](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Étape 3**: Mise à niveau [du client](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Le serveur, le serveur de rapports et les composants client sont mis à niveau pour s’exécuter sur des systèmes d’exploitation Windows 64 bits.

## Mise à niveau du serveur {#section-08bd6fe3da8740fcb19688e8cac6f223}

Pour mettre à jour les **[!UICONTROL Server v6.1]** composants, procédez comme suit :

1. A l’aide du **[!UICONTROL Software and Docs]** profil, ouvrez l’ **[!UICONTROL Start Here]** espace de travail et téléchargez tous les packages de serveur nécessaires dans un dossier local.

   * Téléchargez **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** dossiers zip et extrayez tous les fichiers.

      Le **[!UICONTROL Server]** package comprend **[!UICONTROL Lookup]** et **[!UICONTROL Profile]** des dossiers avec les fichiers **[!UICONTROL Base]** **[!UICONTROL Transform]** et de recherche à ajouter et à remplacer pour mettre à jour le serveur.

   * Téléchargez de nouveaux **[!UICONTROL Profiles]** dossiers.
   * Téléchargez des **[!UICONTROL Lookup]** dossiers mis à jour.
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
1. Définissez [!DNL Directories] dans le fichier [!DNL Profile.cfg] pour vous assurer que le vecteur est mis à jour afin de refléter le nombre d’éléments pour chaque profil.

   Par exemple, pour activer le **[!UICONTROL Predictive Analytics]** profil, vous devez mettre à jour ce paramètre.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configurez et enregistrez le [!DNL PAServer.cfg] fichier pour mettre à niveau la fonctionnalité Analyses prédictives.

   Si vous souhaitez envoyer des tâches d’analyse prédictive aux serveurs, vous devez configurer le [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] fichier pour gérer les envois de mise en grappe côté serveur.

   Le profil personnalisé doit hériter des paramètres du profil de configuration d’Analyses prédictives, ce qui vous permet de configurer et d’enregistrer les paramètres [!DNL PAServer.cfg] en fonction de l’implémentation de votre site.

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

1. (Facultatif) Modifiez le fichier de configuration du serveur de rapports afin qu’il prenne en charge les caractères codés sur deux octets.

   Les outils de données prennent actuellement en charge l’anglais (-en-us) et le chinois (-zh-cn). Vous devez définir une police pour prendre en charge les caractères codés sur un ou deux octets :

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   Les polices répertoriées doivent également être installées sur le système d’exploitation Windows.

1. Configurez le [!DNL Report Server v6.1].

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
>Avant de procéder à la mise à niveau vers **[!UICONTROL Client v6.1]**, l’administrateur doit d’abord effectuer la mise à niveau vers **[!UICONTROL Server v6.1.]**

1. Lancez [!DNL Insight.exe] mais NE vous connectez à aucun profil.
1. Modifiez le [!DNL Insight.cfg] fichier pour ne pas mettre automatiquement à jour le logiciel.

   ```
   Update Software = bool: false
   ```

1. Se connecter au **[!UICONTROL Software and Docs]** profil (logiciels).
1. Télécharger [!DNL Software\Insight Client\v6.10].
1. (Facultatif) Modifiez [!DNL insight.cfg] pour prendre en charge les caractères codés sur deux octets.

   Les outils de données prennent actuellement en charge l’anglais et le chinois simplifié. Sélectionnez des polices pour prendre en charge les deux langues suivantes :

   ```
   Fonts = vector: 2 items  
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Quittez le client.
1. Copiez les fichiers du package client **v6.1** téléchargé dans le [!DNL Install] dossier.

   >[!NOTE]
   >
   >Le [!DNL Insight.zbin] fichier du dossier d’installation est un fichier de sauvegarde utilisé pour la localisation et doit être présent dans le répertoire d’installation. Ce fichier ou d&#39;autres [!DNL .zbin] fichiers seront utilisés selon les paramètres de ligne de commande transmis au démarrage.
   >
   >Par exemple, pour lancer le chinois simplifié, créez un raccourci qui passe dans le paramètre de ligne de commande.
   >
   >```
   >Insight.exe -zh-cn
   >```
   >
   >Si vous souhaitez lancer en anglais (par défaut), aucun changement de ligne de commande n’est nécessaire.

1. Lancez [!DNL Insight.exe] pour l’anglais ou le raccourci que vous avez créé pour une autre langue.
1. Connectez-vous à votre profil et permettez au client de vous synchroniser avec le serveur.
1. (Facultatif) Pour utiliser l’IME, effectuez les modifications suivantes dans le [!DNL Insight.cfg] fichier :

   ```
   Localized IME = bool: true
   ```

   L’éditeur de méthode d’entrée (IME) vous permet de saisir des caractères internationaux.

1. (Facultatif) Modifiez le [!DNL Insight.cfg] fichier pour mettre automatiquement à jour le logiciel :

   ```
   Update Software = bool: true
   ```

   Voir les instructions pour la mise en oeuvre de l’IME.
1. Redémarrez après la synchronisation du profil pour utiliser le [!DNL .zbin] fichier le plus récent.

L’installation du client est maintenant terminée.
