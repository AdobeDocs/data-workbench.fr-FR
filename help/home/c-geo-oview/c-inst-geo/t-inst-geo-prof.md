---
description: Le profil Geography fourni avec Data WorkbenchGeography est un profil interne qui fournit des fonctionnalités supplémentaires à votre application Adobe.
title: Installation du profil Geography
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# Installation du profil Geography{#installing-the-geography-profile}

{{eol}}

Le profil Geography fourni avec Data WorkbenchGeography est un profil interne qui fournit des fonctionnalités supplémentaires à votre application Adobe.

Comme pour tous les autres profils internes fournis par Adobe, la variable [!DNL Geography] ne doit pas être modifié. Toute personnalisation doit se produire dans votre jeu de données, dans les profils spécifiques à un rôle ou dans d’autres profils que vous créez.

Le [!DNL Geography] profile comprend plusieurs fichiers d’inclusion de jeux de données de transformation (situés dans la variable [!DNL Dataset\Transformation\Geography] ) qui définissent des dimensions géographiques. Vous trouverez ci-dessous une liste des fichiers d’inclusion de jeux de données de transformation fournis avec la variable [!DNL Geography] profile:

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

Chacun des fichiers est nommé en fonction de la dimension étendue qu’il définit. un fichier supplémentaire, [!DNL IPLookup.cfg], définit plusieurs champs de données géographiques qui sont utilisés pour définir des dimensions dans les autres fichiers d’inclusion de jeux de données de transformation.

Pour plus d’informations sur les fichiers d’inclusion de jeux de données de transformation, voir *Guide de configuration des jeux de données*.

**Pour installer le [!DNL Geography] profil sur le serveur Data Workbench**

>[!NOTE]
>
>Les instructions d’installation suivantes supposent que vous avez installé Data Workbench et établi une connexion entre Data Workbench et le serveur Data Workbench sur lequel vous installez Data Workbench. [!DNL Geography]. Si vous ne l’avez pas fait, reportez-vous à la section *Guide de l’utilisateur de Data Workbench*.

1. Ouvrez le dossier Profils à partir du [!DNL .zip] fichier fourni par Adobe.
1. Copiez le [!DNL Geography] dans le dossier Profils du répertoire d’installation du serveur Data Workbench. Vous voulez obtenir un [!DNL ...\Profiles\Geography] sur votre serveur data workbench, comme illustré dans l’exemple suivant. Les noms des autres dossiers du dossier Profils peuvent différer de ceux affichés.

   ![Infos sur l’étape](assets/Geo_installProfiles_dir.png)

1. Procédez comme suit pour mettre à jour la variable [!DNL profile.cfg] pour chaque profil avec lequel vous souhaitez utiliser Data Workbench. [!DNL Geography].

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .

   1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Le [!DNL profile.cfg] s’affiche.

   1. Dans le [!DNL profile.cfg] fenêtre, clic droit **[!UICONTROL Directories]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Pour ajouter le nouveau répertoire à la fin de la liste des répertoires, cliquez avec le bouton droit de la souris sur le numéro ou le nom du dernier répertoire de la liste, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Saisissez le nom du nouveau répertoire : [!DNL Geography].
   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche pour [!DNL profile.cfg] dans le [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe (y compris le [!DNL Geography] profile), car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.
