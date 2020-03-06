---
description: Le profil Geography fourni avec les données workbenchGeography est un profil interne qui fournit des fonctionnalités supplémentaires à votre application Adobe.
solution: Analytics
title: Installation du profil de géographie
topic: Data workbench
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installation du profil de géographie{#installing-the-geography-profile}

Le profil Geography fourni avec les données workbenchGeography est un profil interne qui fournit des fonctionnalités supplémentaires à votre application Adobe.

Comme pour tous les autres profils internes fournis par Adobe, le [!DNL Geography] profil ne doit pas être modifié. Toute personnalisation doit se produire dans votre jeu de données, dans vos profils spécifiques au rôle ou dans d’autres profils que vous créez.

Le [!DNL Geography] profil comprend plusieurs fichiers de jeu de données de transformation (situés dans le [!DNL Dataset\Transformation\Geography] dossier) qui définissent des dimensions géographiques. Vous trouverez ci-dessous une liste des jeux de données de transformation comprenant les fichiers fournis avec le [!DNL Geography] profil :

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

Chacun des fichiers porte le nom de la dimension étendue qu’il définit. Un fichier supplémentaire [!DNL IPLookup.cfg]définit plusieurs champs de données géographiques utilisés pour définir des dimensions dans l’autre jeu de données de transformation, notamment des fichiers.

Pour plus d’informations sur les fichiers d’inclusion de jeux de données de transformation, voir le Guide *de configuration des jeux de* données.

**Pour installer le[!DNL Geography]profil sur le serveur de l’outil de données**

>[!NOTE]
>
>Les instructions d’installation suivantes partent du principe que vous avez installé les outils de données et établi une connexion entre les outils de données et le serveur sur lequel vous installez les outils de données [!DNL Geography]. Si ce n’est pas le cas, consultez le Guide *de l’utilisateur des outils de* données.

1. Ouvrez le dossier Profils à partir du [!DNL .zip] fichier fourni par Adobe.
1. Copiez le [!DNL Geography] dossier dans le dossier Profils du répertoire d’installation du serveur de l’outil de données. Vous souhaitez obtenir un [!DNL ...\Profiles\Geography] dossier sur votre serveur de outils de données, comme illustré dans l’exemple suivant. Les noms des autres dossiers du dossier Profils peuvent différer de ceux affichés.

   ![Infos sur l’étape](assets/Geo_installProfiles_dir.png)

1. Procédez comme suit pour mettre à jour le [!DNL profile.cfg] fichier de chaque profil avec lequel vous souhaitez utiliser les outils de données [!DNL Geography].

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] , puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.

   1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La [!DNL profile.cfg] fenêtre s&#39;affiche.

   1. Dans la [!DNL profile.cfg] fenêtre, cliquez avec le bouton droit **[!UICONTROL Directories]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Pour ajouter le nouveau répertoire à la fin de la liste des répertoires, cliquez avec le bouton droit de la souris sur le numéro ou le nom du dernier répertoire de la liste, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Entrez le nom du nouveau répertoire : [!DNL Geography].
   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL profile.cfg] dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe (y compris le [!DNL Geography] profil), car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

