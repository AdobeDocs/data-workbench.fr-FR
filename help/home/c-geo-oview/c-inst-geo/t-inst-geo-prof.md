---
description: Le profil Geography fourni avec les outils de donnéesGeography est un profil interne qui fournit des fonctionnalités supplémentaires à votre application d’Adobe.
title: Installation du profil Geography
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# Installation du profil Geography{#installing-the-geography-profile}

Le profil Geography fourni avec les outils de donnéesGeography est un profil interne qui fournit des fonctionnalités supplémentaires à votre application d’Adobe.

Comme pour tous les autres profils internes fournis par l&#39;Adobe, le profil [!DNL Geography] ne doit pas être modifié. Toute personnalisation doit se produire dans votre jeu de données, dans vos profils spécifiques au rôle ou dans d&#39;autres profils que vous créez.

Le profil [!DNL Geography] comprend plusieurs fichiers de données de transformation (situés dans le dossier [!DNL Dataset\Transformation\Geography]) qui définissent des dimensions géographiques. Vous trouverez ci-dessous une liste du jeu de données de transformation comprenant les fichiers fournis avec le profil [!DNL Geography] :

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

Chacun des fichiers porte le nom de la dimension étendue qu’il définit. Un fichier supplémentaire, [!DNL IPLookup.cfg], définit plusieurs champs de données géographiques qui sont utilisés pour définir des dimensions dans l&#39;autre jeu de données de transformation, y compris les fichiers.

Pour plus d&#39;informations sur les fichiers inclus dans le jeu de données de transformation, consultez le *Guide de configuration du jeu de données*.

**Pour installer le  [!DNL Geography] profil sur le serveur de l’outil de données**

>[!NOTE]
>
>Les instructions d’installation suivantes supposent que vous avez installé l’outil de données et établi une connexion entre l’outil de données et le serveur de l’outil de données sur lequel vous installez l’outil de données [!DNL Geography]. Si vous ne l’avez pas fait, consultez le *Guide de l’utilisateur Data Workbench*.

1. Ouvrez le dossier Profils à partir du fichier [!DNL .zip] qui vous a été fourni par Adobe.
1. Copiez le dossier [!DNL Geography] dans le dossier Profils du répertoire d’installation du serveur de l’outil de données. Vous souhaitez obtenir un dossier [!DNL ...\Profiles\Geography] sur votre serveur de outils de données, comme indiqué dans l’exemple suivant. Les noms des autres dossiers du dossier Profils peuvent différer de ceux affichés.

   ![Infos sur l’étape](assets/Geo_installProfiles_dir.png)

1. Suivez les étapes ci-après pour mettre à jour le fichier [!DNL profile.cfg] pour chaque profil avec lequel vous souhaitez utiliser les outils de données [!DNL Geography].

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].

   1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre [!DNL profile.cfg] s&#39;affiche.

   1. Dans la fenêtre [!DNL profile.cfg], cliquez avec le bouton droit de la souris sur **[!UICONTROL Directories]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Pour ajouter le nouveau répertoire à la fin de la liste des répertoires, cliquez avec le bouton droit de la souris sur le numéro ou le nom du dernier répertoire de la liste et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Entrez le nom du nouveau répertoire : [!DNL Geography].
   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la colonne [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL profile.cfg] de la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

      >[!NOTE]
      >
      >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par l&#39;Adobe (y compris le profil [!DNL Geography]), car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.
