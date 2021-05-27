---
description: Le profil Geography fourni avec Data WorkbenchGeography est un profil interne qui fournit des fonctionnalités supplémentaires à votre application Adobe.
title: Installation du profil Geography
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# Installation du profil Geography{#installing-the-geography-profile}

Le profil Geography fourni avec Data WorkbenchGeography est un profil interne qui fournit des fonctionnalités supplémentaires à votre application Adobe.

Comme pour tous les autres profils internes fournis par Adobe, le profil [!DNL Geography] ne doit pas être modifié. Toute personnalisation doit se produire dans votre jeu de données, dans les profils spécifiques à un rôle ou dans d’autres profils que vous créez.

Le profil [!DNL Geography] comprend plusieurs fichiers d’inclusion de jeux de données de transformation (situés dans le dossier [!DNL Dataset\Transformation\Geography] ) qui définissent des dimensions géographiques. Voici une liste des fichiers d’inclusion de jeux de données de transformation fournis avec le profil [!DNL Geography] :

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

Chacun des fichiers est nommé en fonction de la dimension étendue qu’il définit. Un fichier supplémentaire, [!DNL IPLookup.cfg], définit plusieurs champs de données géographiques utilisés pour définir des dimensions dans les autres fichiers d’inclusion de jeux de données de transformation.

Pour plus d’informations sur les fichiers d’inclusion de jeux de données de transformation, consultez le *Guide de configuration des jeux de données*.

**Pour installer le  [!DNL Geography] profil sur le serveur Data Workbench**

>[!NOTE]
>
>Les instructions d’installation suivantes supposent que vous avez installé Data Workbench et établi une connexion entre Data Workbench et le serveur Data Workbench sur lequel vous installez Data Workbench [!DNL Geography]. Si vous ne l’avez pas fait, consultez le *Guide de l’utilisateur du Data Workbench*.

1. Ouvrez le dossier Profils à partir du fichier [!DNL .zip] fourni par Adobe.
1. Copiez le dossier [!DNL Geography] dans le dossier Profils du répertoire d’installation du serveur Data Workbench. Vous souhaitez obtenir un dossier [!DNL ...\Profiles\Geography] sur votre serveur Data Workbench, comme illustré dans l’exemple suivant. Les noms des autres dossiers du dossier Profils peuvent différer de ceux affichés.

   ![Infos sur l’étape](assets/Geo_installProfiles_dir.png)

1. Procédez comme suit pour mettre à jour le fichier [!DNL profile.cfg] pour chaque profil avec lequel vous souhaitez utiliser Data Workbench [!DNL Geography].

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].

   1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre [!DNL profile.cfg] s’affiche.

   1. Dans la fenêtre [!DNL profile.cfg], cliquez avec le bouton droit de la souris sur **[!UICONTROL Directories]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Pour ajouter le nouveau répertoire à la fin de la liste des répertoires, cliquez avec le bouton droit de la souris sur le numéro ou le nom du dernier répertoire de la liste, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Saisissez le nom du nouveau répertoire : [!DNL Geography].
   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans la balise [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL profile.cfg] dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** *&lt;**[!UICONTROL profile name]***.

      >[!NOTE]
      >
      >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe (y compris le profil [!DNL Geography]), car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.
