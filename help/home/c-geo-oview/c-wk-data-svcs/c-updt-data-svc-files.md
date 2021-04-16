---
description: Si vous vous abonnez à l’un ou l’autre des services de données, vous devez régulièrement mettre à jour les fichiers de services de données fournis par Adobe.
title: Mise à jour des fichiers de service de données
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 1%

---

# Mise à jour des fichiers de service de données{#updating-data-service-files}

Si vous vous abonnez à l’un ou l’autre des services de données, vous devez régulièrement mettre à jour les fichiers de services de données fournis par Adobe.

Pour ce faire, vous devez avoir accès aux fichiers sur le serveur de l’outil de données.

Pour charger les fichiers de données [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence], vous devez exécuter les procédures suivantes.

## Remplacement du fichier de données {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. Dans l’outil de données, sous l’onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l’espace de travail [!DNL Servers Manager].

1. Dans la fenêtre [!DNL Servers Manager], cliquez avec le bouton droit de la souris sur l&#39;icône du serveur de l&#39;outil de données sur lequel vous souhaitez charger les fichiers, puis cliquez sur **[!UICONTROL Server Files]**.

1. Dans la colonne [!DNL Server Files Manager], cliquez avec le bouton droit dans la colonne **[!UICONTROL Temp]** pour **[!UICONTROL Lookups\IP Geo-location]** ou **[!UICONTROL Lookups\IP Geo-intelligence]** et cliquez sur **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]***.

1. Copiez le fichier de données [!DNL .bin] fourni par Adobe dans la fenêtre du dossier de géointelligence des recherches\IP ou de la géolocalisation des recherches\IP.
1. Enregistrez le fichier sur l’ordinateur serveur de l’outil de données en cliquant avec le bouton droit sur la colonne [!DNL Temp] du fichier de données et en cliquant sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

   Si vous exécutez une grappe, téléchargez les fichiers sur le serveur maître de l’outil de données de la grappe.

## Mise à jour de la transformation IPLookup {#section-a8b99afe3eb04afabe88e15bd465f935}

1. Dans le [!DNL Profile Manager], cliquez sur **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** et **[!UICONTROL Geography]**.

1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL IP Lookup.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].

1. Cliquez avec le bouton droit de la souris sur la nouvelle coche et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Une fenêtre de configuration de transformation s&#39;affiche.

1. Dans la fenêtre, cliquez sur **[!UICONTROL Transformation]**, puis sur **[!UICONTROL Transformations]**.

1. Recherchez **[!UICONTROL IPLookup Quova]** ou **[!UICONTROL IPLookup Digital Envoy]**, puis cliquez dessus.

1. Pour le paramètre File, mettez à jour le nom du fichier pour qu&#39;il corresponde au nom du nouveau fichier de données ( [!DNL .bin]) fourni par l&#39;Adobe.
1. Enregistrez le fichier de configuration de transformation en cliquant avec le bouton droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre de configuration et en cliquant sur **[!UICONTROL Save]**.

1. Enregistrez le fichier de configuration modifié dans chaque profil qui utilise le service de données en cliquant avec le bouton droit sur la coche située en regard de [!DNL IP Lookup.cfg] dans la colonne [!DNL User] et en cliquant sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***. La retransformation des données commence après la synchronisation du profil du jeu de données.

   Pour plus d&#39;informations sur la retransformation de votre jeu de données, consultez le chapitre Retraitement et retransformation du *Guide de configuration des jeux de données*.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par l&#39;Adobe (y compris le profil [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence]), car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

Si vous avez installé le service de données [!DNL IP Geo-intelligence] et [!DNL IP Geo-location] pour la version 5.1 ou ultérieure, vous avez effectué la mise à jour du service de données. Cependant, si vous avez installé les services de données [!DNL IP Geo-intelligence] et [!DNL IP Geo-location] avant la version 5.1, vous devez exécuter les procédures supplémentaires suivantes.

## Remplacement du fichier de recherche {#section-ced1efa38a76419d812edd35423dbff7}

Vous ne devez exécuter les étapes suivantes que si vous avez installé le service de données [!DNL IP Geo-intelligence] et [!DNL IP Geo-location] avant la version 5.1.

1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** ou **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**, puis sur **[!UICONTROL Maps]** pour en vue le contenu.

1. Cliquez avec le bouton droit dans la colonne **[!UICONTROL Temp]** pour **[!UICONTROL Maps]** et cliquez sur **[!UICONTROL Open]** > *&lt; &lt;a4/&quot;*.**[!UICONTROL folder]**

1. Copiez le nouveau fichier [!DNL .txt] fourni par Adobe dans la fenêtre du dossier Maps.
1. Enregistrez le fichier sur l’ordinateur serveur de l’outil de données en cliquant avec le bouton droit de la coche dans la colonne [!DNL Temp] du fichier [!DNL .txt] et en cliquant sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

>[!NOTE]
>
>Si vous exécutez une grappe, téléchargez les fichiers sur le serveur maître de l’outil de données de la grappe.

## Mise à jour des fichiers de couche {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Vous ne devez exécuter les étapes suivantes que si vous avez installé le service de données [!DNL IP Geo-intelligence] et [!DNL IP Geo-location] avant la version 5.1.

Suivez ces étapes pour chaque fichier de calque ( [!DNL .layer]) qui référence le fichier de recherche [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] ( [!DNL .txt]).

1. Dans le dossier Profils\*nom du service de données*\Maps du répertoire d’installation du serveur de l’outil de données, ouvrez le fichier [!DNL .layer] dans un éditeur de texte tel que le Bloc-notes.

1. Dans le vecteur [!DNL Data Paths], mettez à jour le nom du fichier de recherche [!DNL .txt] pour qu&#39;il corresponde au nom du nouveau fichier [!DNL .txt] fourni par l&#39;Adobe, comme indiqué dans l&#39;exemple de fichier suivant :

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
1. Répétez les étapes 2 et 3 pour chaque fichier [!DNL .layer] qui référence le fichier [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] [!DNL .txt].
