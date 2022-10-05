---
description: Si vous vous abonnez à l’un des services de données, vous devez périodiquement mettre à jour les fichiers de services de données fournis par Adobe.
title: Mise à jour des fichiers de service de données
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 1%

---

# Mise à jour des fichiers de service de données{#updating-data-service-files}

{{eol}}

Si vous vous abonnez à l’un des services de données, vous devez périodiquement mettre à jour les fichiers de services de données fournis par Adobe.

Pour ce faire, vous devez avoir accès aux fichiers sur le serveur Data Workbench.

Pour charger [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] fichiers de données, vous devez effectuer les procédures suivantes.

## Remplacement du fichier de données {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. Dans Data Workbench, sur la [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir la [!DNL Servers Manager] workspace.

1. Dans le [!DNL Servers Manager] cliquez avec le bouton droit de la souris sur l’icône du serveur data workbench sur lequel vous souhaitez charger les fichiers, puis cliquez sur **[!UICONTROL Server Files]**.

1. Dans le [!DNL Server Files Manager], cliquez avec le bouton droit de la souris dans le **[!UICONTROL Temp]** column pour **[!UICONTROL Lookups\IP Geo-location]** ou **[!UICONTROL Lookups\IP Geo-intelligence]** et cliquez sur **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copiez le [!DNL .bin] fichier de données fourni par Adobe à la fenêtre de dossier Lookups\IP Geo-location ou Lookups\IP Geo-intelligence.
1. Enregistrez le fichier sur l’ordinateur du serveur Data Workbench en cliquant avec le bouton droit de la souris sur le serveur [!DNL Temp] pour le fichier de données et en cliquant sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   Si vous exécutez une grappe, chargez les fichiers sur le serveur Data Workbench maître de la grappe.

## Mise à jour de la transformation IPLookup {#section-a8b99afe3eb04afabe88e15bd465f935}

1. Dans le [!DNL Profile Manager], cliquez sur **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]**, et **[!UICONTROL Geography]**.

1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL IP Lookup.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .

1. Cliquez avec le bouton droit de la souris sur la nouvelle coche, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Une fenêtre de configuration de transformation s&#39;affiche.

1. Dans la fenêtre, cliquez sur **[!UICONTROL Transformation]**, puis cliquez sur **[!UICONTROL Transformations]**.

1. Recherchez et cliquez sur l’une des options suivantes : **[!UICONTROL IPLookup Quova]** ou **[!UICONTROL IPLookup Digital Envoy]**.

1. Pour le paramètre File , mettez à jour le nom du fichier afin qu’il corresponde au nom des nouvelles données ( [!DNL .bin]) fourni par Adobe.
1. Enregistrez le fichier de configuration de transformation en cliquant avec le bouton droit de la souris. **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre de configuration, puis cliquez sur **[!UICONTROL Save]**.

1. Enregistrez le fichier de configuration modifié dans chaque profil qui utilise le service de données en cliquant avec le bouton droit de la souris sur la coche en regard de [!DNL IP Lookup.cfg] dans le [!DNL User] colonne et clic **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. La retransformation des données commence après la synchronisation du profil du jeu de données.

   Pour plus d’informations sur la retransformation de votre jeu de données, voir le chapitre Retraitement et retransformation de *Guide de configuration des jeux de données*.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe (y compris le [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] profile), car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.

Si vous avez installé le [!DNL IP Geo-intelligence] et [!DNL IP Geo-location] service de données pour la version 5.1 ou ultérieure, vous avez terminé la mise à jour du service de données. Cependant, si vous avez installé la variable [!DNL IP Geo-intelligence] et [!DNL IP Geo-location] vous devez effectuer les procédures supplémentaires suivantes avant la version 5.1 du service de données.

## Remplacement du fichier de recherche {#section-ced1efa38a76419d812edd35423dbff7}

Vous ne devez effectuer les étapes suivantes que si vous avez installé le [!DNL IP Geo-intelligence] et [!DNL IP Geo-location] service de données antérieur à la version 5.1.

1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** ou **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**, puis cliquez sur **[!UICONTROL Maps]** pour afficher son contenu.

1. Cliquez avec le bouton droit de la souris dans le **[!UICONTROL Temp]** column pour **[!UICONTROL Maps]** et cliquez sur **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copiez le nouveau [!DNL .txt] fichier fourni par Adobe à la fenêtre du dossier Maps.
1. Enregistrez le fichier sur l’ordinateur du serveur Data Workbench en cliquant avec le bouton droit de la souris sur la coche dans la fonction [!DNL Temp] de la colonne [!DNL .txt] fichier et clic **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Si vous exécutez une grappe, chargez les fichiers sur le serveur Data Workbench maître de la grappe.

## Mise à jour des fichiers de calque {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Vous ne devez effectuer les étapes suivantes que si vous avez installé le [!DNL IP Geo-intelligence] et [!DNL IP Geo-location] service de données antérieur à la version 5.1.

Procédez comme suit pour chaque calque ( [!DNL .layer]) qui fait référence au fichier [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] recherche ( [!DNL .txt]).

1. Dans le dossier Profils\*nom du service de données*\Maps du répertoire d’installation du serveur Data Workbench, ouvrez le [!DNL .layer] dans un éditeur de texte tel que le Bloc-notes.

1. Dans le [!DNL Data Paths] vectoriel, mettez à jour le nom de la variable [!DNL .txt] fichier de recherche correspondant au nom du nouveau [!DNL .txt] fourni par Adobe, comme indiqué dans l’exemple de fichier suivant :

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
1. Répétez les étapes 2 et 3 pour chaque [!DNL .layer] qui référence le fichier [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] [!DNL .txt] fichier .
