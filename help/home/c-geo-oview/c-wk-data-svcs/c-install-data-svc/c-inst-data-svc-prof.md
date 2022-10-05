---
description: Les profils de service de données (Géo-intelligence IP et Géolocalisation IP) sont des profils internes qui fournissent des fonctionnalités supplémentaires à votre application Adobe.
title: Installation du profil de services de données
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 1%

---

# Installation du profil de services de données{#installing-the-data-service-profile}

{{eol}}

Les profils de service de données (Géo-intelligence IP et Géolocalisation IP) sont des profils internes qui fournissent des fonctionnalités supplémentaires à votre application Adobe.

Comme pour tous les autres profils internes fournis par Adobe, ces profils ne doivent pas être modifiés. Toute personnalisation doit se produire dans votre jeu de données, dans les profils spécifiques à un rôle ou dans d’autres profils que vous créez.

Les profils de service de données incluent les fichiers suivants à installer sur un serveur Data Workbench :

* **Profils\*nom du profil *\Dataset\Log Processing\Traffic\IP.cfg:** Répertorie le champ c-ip à transmettre du traitement du journal à la transformation.
* **Profils\*nom du profil *\Dataset\Transformation\Geography\IPLookup.cfg:** Définit une transformation IPLookup qui produit plusieurs champs de données géographiques à l’aide du fichier de recherche Géo-intelligence IP ou Géolocalisation IP fourni.

Pour plus d’informations sur les fichiers d’inclusion de jeux de données de transformation, voir *Guide de configuration des jeux de données*.

En outre, chaque profil de service de données vous fournit un fichier de couche de point d’élément nommé [!DNL IP Coordinates.layer]. Ce fichier de couche vous permet de mapper dynamiquement des emplacements dans votre jeu de données sur le globe à l’aide d’adresses IP. Après l’installation, la couche est stockée dans le dossier Profils\*nom du service de données*\Maps du répertoire d’installation du serveur Data Workbench.

Le [!DNL IP Coordinates.layer] référence la dimension Coordonnées , définie dans la variable [!DNL Coordinates.cfg] fourni avec le fichier [!DNL Geography] et situés dans le dossier Jeu de données\Transformation\Geography. Chaque élément de la dimension Coordonnées défini dans votre jeu de données est mappé sur le globe à l’aide des informations de latitude et de longitude contenues dans cet élément. Pour plus d’informations sur les calques de point d’élément qui utilisent des points dynamiques, voir [Définir des calques de point d’élément à l’aide de points dynamiques](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

>[!NOTE]
>
>Si vous avez installé le service de données de géo-intelligence IP et de géolocalisation IP avant la version 5.1, votre fichier de couche de point d’élément référence un fichier de recherche au lieu d’utiliser des points dynamiques. Chaque fichier de couche fait référence au fichier de recherche Géocodes IP et à la dimension Géocode IP. Le fichier de recherche Codes géographiques IP contient une liste de codes géographiques IP (emplacements géographiques basés sur l’adresse IP) et la latitude et la longitude pour chacun d’eux. Chaque élément d’une dimension de géocode IP défini dans votre jeu de données est mappé sur le globe à l’aide de la latitude et de la longitude répertoriées pour ce géocode IP dans le fichier de recherche de géocodes IP.

Le nom du fichier de couche et les fichiers auxquels il fait référence diffèrent pour chaque service de données :

* Le [!DNL IP Geocodes D.layer] est installé avec le profil IP de géointelligence (Digital Envoy). Ce calque de point d’élément fait référence au [!DNL IP Geocodes D yyyymmdd.txt] fichier de recherche (que vous devez mettre à jour régulièrement) et la dimension ID de géocode IP.

* Le [!DNL IP Geocodes Q.layer] est installé avec le profil de géolocalisation IP (Quova). Ce calque de point d’élément fait référence au [!DNL IP Geocodes Q yyyymmdd.txt] fichier de recherche (que vous devez mettre à jour régulièrement) et la dimension Q du géocode IP.

Pour plus d’informations sur les calques de point d’élément qui utilisent des fichiers de recherche, voir [Définition de calques de point d’élément faisant référence à des fichiers Lookup](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f).

## Pour installer le profil de géolocalisation des adresses IP ou de géolocalisation des adresses IP {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>Les instructions d’installation suivantes supposent que vous avez installé Data Workbench et établi une connexion entre Data Workbench et le serveur Data Workbench sur lequel vous installez Data Workbench. [!DNL Geography]. Si vous ne l’avez pas fait, reportez-vous à la section *Guide de l’utilisateur de Data Workbench*.

1. Ouvrez le dossier Profils à partir du [!DNL .zip] fichier que vous avez reçu d’Adobe.
1. Copiez le dossier IP Geo-intelligence ou IP Geo-location dans le dossier Profils du répertoire d’installation du serveur Data Workbench. Vous voulez finir avec un...\Profils\Dossier de géointelligence IP ou ...\Profiles\IP Géolocalisation sur votre serveur Data Workbench, comme illustré dans l’exemple suivant. Les noms des autres dossiers dans la variable [!DNL Profiles] peut différer de celles affichées.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Procédez comme suit pour mettre à jour la variable [!DNL profile.cfg] pour chaque profil avec lequel vous souhaitez utiliser la variable [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] profile.

   1. Ouvrez le **[!UICONTROL Profile Manager]**.
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .

   1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Le [!DNL profile.cfg] s’affiche.

   1. Dans le [!DNL profile.cfg]fenêtre, clic droit **[!UICONTROL Directories]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Pour ajouter le nouveau répertoire à la fin de la liste des répertoires, cliquez avec le bouton droit de la souris sur le numéro ou le nom du dernier répertoire de la liste, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Saisissez le nom du nouveau répertoire : [!DNL IP Geo-intelligence] ou I [!DNL P Geo-location].

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche pour [!DNL profile.cfg] dans le [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

>[!NOTE]
>
>N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe (y compris le [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] profile), car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.
