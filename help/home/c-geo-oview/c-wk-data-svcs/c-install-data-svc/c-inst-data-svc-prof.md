---
description: Les profils de service de données (Géo-intelligence IP et Géolocalisation IP) sont des profils internes qui offrent des fonctionnalités supplémentaires à votre application d’Adobe.
title: Installation du profil de services de données
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 1%

---

# Installation du profil de services de données{#installing-the-data-service-profile}

Les profils de service de données (Géo-intelligence IP et Géolocalisation IP) sont des profils internes qui offrent des fonctionnalités supplémentaires à votre application d’Adobe.

Comme pour tous les autres profils internes fournis par l&#39;Adobe, ces profils ne doivent pas être modifiés. Toute personnalisation doit se produire dans votre jeu de données, dans vos profils spécifiques au rôle ou dans d&#39;autres profils que vous créez.

Les profils de service de données suivants incluent les fichiers à installer sur un serveur d’outils de données :

* **Profils\*nom *du profil \Dataset\Log Processing\Traffic\IP.cfg:** Liste le champ c-ip à transmettre du traitement du journal à la transformation.
* **Profils\*nom *du profil \Dataset\Transformation\Geography\IPLookup.cfg:** Définit une transformation IPLookup qui produit plusieurs champs de données géographiques à l’aide du fichier de recherche Géo-intelligence IP ou Géolocalisation IP fourni.

Pour plus d&#39;informations sur les fichiers inclus dans le jeu de données de transformation, consultez le *Guide de configuration du jeu de données*.

En outre, chaque profil de service de données fournit un fichier de couche de points d’élément nommé [!DNL IP Coordinates.layer]. Ce fichier de calque vous permet de mapper dynamiquement des emplacements dans votre jeu de données sur le globe à l’aide d’adresses IP. Après l’installation, la couche est stockée dans le dossier Profils\*nom du service de données*\Maps du répertoire d’installation du serveur de l’outil de données.

Le fichier [!DNL IP Coordinates.layer] fait référence à la dimension Coordinates, définie dans le fichier [!DNL Coordinates.cfg] fourni avec le profil [!DNL Geography] et situé dans le répertoire Dataset\Transformation\Geography folder. Chaque élément de la dimension Coordonnées défini dans votre jeu de données est mappé sur le globe à l’aide des informations de latitude et de longitude contenues dans cet élément. Pour plus d’informations sur les calques de points d’élément qui utilisent des points dynamiques, voir [Définition de calques de points d’élément à l’aide de points dynamiques](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

>[!NOTE]
>
>Si vous avez installé le service de données de géo-intelligence IP et de géolocalisation IP avant la version 5.1, votre fichier de couche de points d’élément référence un fichier de recherche plutôt que d’utiliser des points dynamiques. Chaque fichier de calque référence le fichier de recherche Géocodes IP et la dimension Géocode IP. Le fichier de recherche Codes géographiques IP contient une liste de codes géographiques IP (emplacements géographiques basés sur l’adresse IP) et la latitude et la longitude pour chacun d’eux. Chaque élément d’une dimension de géocode IP défini dans votre jeu de données est mappé sur le globe à l’aide de la latitude et de la longitude répertoriées pour ce géocode IP dans le fichier de recherche Géocodes IP.

Le nom du fichier de couche et des fichiers auxquels il fait référence diffèrent pour chaque service de données :

* Le fichier [!DNL IP Geocodes D.layer] est installé avec le profil IP Geo-Intelligence (Digital Envoy). Ce calque de point d’élément fait référence au fichier de recherche [!DNL IP Geocodes D yyyymmdd.txt] (que vous devez mettre à jour régulièrement) et à la dimension Code géographique d’IP.

* Le fichier [!DNL IP Geocodes Q.layer] est installé avec le profil de géolocalisation IP (Quova). Ce calque de point d’élément fait référence au fichier de recherche [!DNL IP Geocodes Q yyyymmdd.txt] (que vous devez mettre à jour régulièrement) et à la dimension Q du géocode IP.

Pour plus d’informations sur les calques de points d’élément qui utilisent des fichiers de recherche, voir [Définition des calques de points d’élément référençant les fichiers de recherche](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f).

## Pour installer le profil de géo-intelligence IP ou de géo-localisation IP {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>Les instructions d’installation suivantes supposent que vous avez installé l’outil de données et établi une connexion entre l’outil de données et le serveur de l’outil de données sur lequel vous installez l’outil de données [!DNL Geography]. Si vous ne l’avez pas fait, consultez le *Guide de l’utilisateur Data Workbench*.

1. Ouvrez le dossier Profils à partir du fichier [!DNL .zip] que vous avez reçu de l&#39;Adobe.
1. Copiez le dossier IP Geo-intelligence ou IP Geo-location dans le dossier Profils du répertoire d’installation du serveur de l’outil de données. Vous voulez finir avec un ...\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example. Les noms des autres dossiers du dossier [!DNL Profiles] peuvent différer de ceux affichés.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Suivez les étapes ci-après pour mettre à jour le fichier [!DNL profile.cfg] pour chaque profil avec lequel vous souhaitez utiliser le profil [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location].

   1. Ouvrez le **[!UICONTROL Profile Manager]**.
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].

   1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre [!DNL profile.cfg] s&#39;affiche.

   1. Dans la fenêtre [!DNL profile.cfg], cliquez avec le bouton droit de la souris sur **[!UICONTROL Directories]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Pour ajouter le nouveau répertoire à la fin de la liste des répertoires, cliquez avec le bouton droit de la souris sur le numéro ou le nom du dernier répertoire de la liste et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Entrez le nom du nouveau répertoire : [!DNL IP Geo-intelligence] ou I [!DNL P Geo-location].

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la colonne [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL profile.cfg] de la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

>[!NOTE]
>
>N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par l&#39;Adobe (y compris le profil [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence]), car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.
