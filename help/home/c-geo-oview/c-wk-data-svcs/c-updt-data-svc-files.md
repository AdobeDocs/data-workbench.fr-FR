---
description: Si vous vous abonnez à l’un ou l’autre service de données, vous devez régulièrement mettre à jour les fichiers de service de données fournis par Adobe.
solution: Analytics
title: Mise à jour des fichiers du service de données
topic: Data workbench
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mise à jour des fichiers du service de données{#updating-data-service-files}

Si vous vous abonnez à l’un ou l’autre service de données, vous devez régulièrement mettre à jour les fichiers de service de données fournis par Adobe.

Pour ce faire, vous devez avoir accès aux fichiers sur le serveur de l’outil de données.

Pour charger [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] des fichiers de données, vous devez exécuter les procédures suivantes.

## Remplacement du fichier de données {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. Dans l’outil de données, dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** vignette pour ouvrir l’ [!DNL Servers Manager] espace de travail.

1. Dans la [!DNL Servers Manager] fenêtre, cliquez avec le bouton droit de la souris sur l’icône du serveur de l’outil de données sur lequel vous souhaitez charger les fichiers, puis cliquez sur **[!UICONTROL Server Files]**.

1. Dans la [!DNL Server Files Manager], cliquez avec le bouton droit de la souris dans la **[!UICONTROL Temp]** colonne **[!UICONTROL Lookups\IP Geo-location]** ou **[!UICONTROL Lookups\IP Geo-intelligence]** , puis cliquez sur **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>.*

1. Copiez le fichier [!DNL .bin] de données fourni par Adobe dans la fenêtre du dossier Recherches\Géolocalisation IP ou Recherches\Géo-intelligence IP.
1. Enregistrez le fichier sur l’ordinateur du serveur de l’outil de données en cliquant avec le bouton droit sur la [!DNL Temp] colonne du fichier de données et en cliquant sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   Si vous exécutez une grappe, téléchargez les fichiers sur le serveur maître de l’outil de données de la grappe.

## Mise à jour de la transformation IPLookup {#section-a8b99afe3eb04afabe88e15bd465f935}

1. Dans la [!DNL Profile Manager], cliquez sur **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** et **[!UICONTROL Geography]**.

1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL IP Lookup.cfg] , puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.

1. Cliquez avec le bouton droit de la souris sur la nouvelle coche, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Une fenêtre de configuration de transformation s’affiche.

1. Dans la fenêtre, cliquez sur **[!UICONTROL Transformation]**, puis sur **[!UICONTROL Transformations]**.

1. Recherchez et cliquez sur **[!UICONTROL IPLookup Quova]** ou **[!UICONTROL IPLookup Digital Envoy]**.

1. Pour le paramètre Fichier, mettez à jour le nom du fichier afin qu’il corresponde au nom du nouveau fichier de données ( [!DNL .bin]) fourni par Adobe.
1. Enregistrez le fichier de configuration de transformation en cliquant avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre de configuration et en cliquant sur **[!UICONTROL Save]**.

1. Enregistrez le fichier de configuration modifié dans chaque profil qui utilise le service de données en cliquant avec le bouton droit de la souris sur la coche située en regard de [!DNL IP Lookup.cfg] la [!DNL User] colonne et en cliquant sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. La retransformation des données commence après la synchronisation du profil du jeu de données.

   Pour plus d’informations sur la retransformation de votre jeu de données, voir le chapitre Retraitement et retransformation du Guide *de configuration des jeux de* données.

   >[!NOTE]
   >
   >N’enregistrez pas le fichier de configuration modifié dans l’un des profils internes fournis par Adobe (y compris le [!DNL IP Geo-location] profil ou le [!DNL IP Geo-intelligence] profil), car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

Si vous avez installé le service [!DNL IP Geo-intelligence] et le service de données [!DNL IP Geo-location] pour la version 5.1 ou ultérieure, vous avez terminé la mise à jour du service de données. Toutefois, si vous avez installé le service [!DNL IP Geo-intelligence] et [!DNL IP Geo-location] de données avant la version 5.1, vous devez effectuer les procédures supplémentaires suivantes.

## Remplacement du fichier de recherche {#section-ced1efa38a76419d812edd35423dbff7}

Suivez les étapes ci-après uniquement si vous avez installé le service [!DNL IP Geo-intelligence] et le service [!DNL IP Geo-location] de données avant la version 5.1.

1. Dans la [!DNL Server Files Manager], cliquez sur **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** ou **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**, puis cliquez **[!UICONTROL Maps]** pour en afficher le contenu.

1. Cliquez avec le bouton droit de la souris dans la **[!UICONTROL Temp]** colonne **[!UICONTROL Maps]** , puis cliquez sur **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copiez le nouveau [!DNL .txt] fichier fourni par Adobe dans la fenêtre du dossier Maps.
1. Enregistrez le fichier sur l’ordinateur du serveur de l’outil de données en cliquant avec le bouton droit de la souris sur la coche de la [!DNL Temp] colonne du [!DNL .txt] fichier et en cliquant sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Si vous exécutez une grappe, téléchargez les fichiers sur le serveur maître de l’outil de données de la grappe.

## Mise à jour des fichiers de calque {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Suivez les étapes ci-après uniquement si vous avez installé le service [!DNL IP Geo-intelligence] et le service [!DNL IP Geo-location] de données avant la version 5.1.

Effectuez les étapes suivantes pour chaque fichier de calque ( [!DNL .layer]) qui fait référence au fichier [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] de recherche ( [!DNL .txt]).

1. Dans le dossier Profils\*nom du service de données*\Maps du répertoire d’installation du serveur de l’outil de données, ouvrez le [!DNL .layer] fichier dans un éditeur de texte tel que le Bloc-notes.

1. Dans le [!DNL Data Paths] vecteur, mettez à jour le nom du fichier de [!DNL .txt] recherche pour qu’il corresponde au nom du nouveau [!DNL .txt] fichier fourni par Adobe, comme indiqué dans l’exemple de fichier suivant :

   ```
   Layer = ElementPointLayer:
     Data Paths = vector: 1 items
       0 = Path: Maps\\LookupFileName.txt
     Longitude Column = string: LongitudeColumnName
     Latitude Column = string: LatitudeColumnName
     Name Column = string: LocationColumnName
     Key Column = string: KeyColumnName
     Dimension = ref: wdata/model/dim/DimensionName
     Metric = ref: wdata/model/metric/MetricName
   ```

1. Enregistrez le fichier de calque mis à jour.
1. Répétez les étapes 2 et 3 pour chaque [!DNL .layer] fichier faisant référence au [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] au [!DNL .txt] fichier.

