---
description: La fonctionnalité de transformation s’exécute sur un ordinateur FSU Insight Server pour permettre l’exportation des données source du journal en vue de leur utilisation par d’autres applications.
solution: Analytics
title: Configuration de Transform
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---


# Configuration de Transform{#configuring-transform}

La fonctionnalité de transformation s’exécute sur un ordinateur FSU Insight Server pour permettre l’exportation des données source du journal en vue de leur utilisation par d’autres applications.

[!DNL Transform] peuvent lire [!DNL .vsl] des fichiers, des fichiers journaux, des fichiers XML et des données ODBC et exporter les données sous forme de [!DNL .vsl] fichiers, de fichiers texte ou de fichiers texte délimités qui peuvent être utilisés par des routines de chargement d&#39;entrepôt de données, des agences de contrôle ou d&#39;autres cibles. L&#39;extraction et la transformation des données peuvent être effectuées en continu ou selon d&#39;autres méthodes planifiées. Chaque [!DNL Insight Server] FSU qui fournit la sortie de données de événement modifiées doit s&#39;exécuter [!DNL Transform].

>[!NOTE]
>
>En règle générale, [!DNL Transform] est installé sur un [!DNL Insight Server] FSU. Toutefois, votre mise en oeuvre peut nécessiter une installation sur un [!DNL Insight Server] processeur de données. Pour plus d&#39;informations, contactez l&#39;Adobe.

Pour plus d’informations sur la configuration système requise pour l’installation, la configuration et le fonctionnement [!DNL Transform], voir le document *Configuration système requise* .

L’Adobe distribue la [!DNL Transform] fonctionnalité sous la forme d’un profil dans le [!DNL .zip] fichier pour le [!DNL Insight Server] pack de version. Le [!DNL Transform] profil est un profil interne qui fournit des fonctionnalités supplémentaires à [!DNL Insight Server]. Comme pour tous les autres profils internes fournis par l&#39;Adobe, le profil ne doit pas être modifié. Toute personnalisation doit se produire dans votre jeu de données, dans vos profils spécifiques au rôle ou dans d&#39;autres profils que vous créez.

Le profil se compose des fichiers suivants :

* [!DNL Log Processing.cfg]
* [ !DNL [!DNL Insight] Transform.cfg]
* [ ! DNL [!DNL Insight] Transform Mode.cfg]
* un fichier d&#39;inclusion d&#39;un jeu de données de traitement de journal

Tous ces fichiers se trouvent dans le [!DNL Dataset] dossier du profil.

**Pour installer le[!DNL Transform]profil sur[!DNL Insight Server]**

>[!NOTE]
>
>Les instructions d’installation suivantes supposent que vous avez installé [!DNL Insight] et établi une connexion entre [!DNL Insight] et [!DNL Insight Server] le système sur lequel vous installez [!DNL Transform]. Si vous ne l&#39;avez pas fait, consultez le * [!DNL Insight] Guide de l&#39;utilisateur*.

1. Ouvrez le [!DNL .zip] fichier pour le [!DNL Insight Server] package de publication, puis ouvrez le [!DNL Profiles] dossier dans ce [!DNL .zip] fichier.
1. Copiez le [!DNL Transform] dossier dans le [!DNL Profiles] dossier du répertoire d’ [!DNL Insight Server] installation. Vous souhaitez finir avec un [!DNL ...\Profiles\Transform] dossier sur votre [!DNL Insight Server] site, comme le montre l&#39;exemple suivant.

   ![Infos sur l’étape](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Si vous avez suivi toutes les étapes d’installation [!DNL Insight Server] (voir [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), il se peut que le répertoire des Profils contienne déjà un [!DNL Transform] dossier.

1. Suivez les étapes ci-après pour mettre à jour le [!DNL profile.cfg] fichier du profil avec lequel vous souhaitez utiliser [!DNL Transform]. Le jeu de données est retraité une fois ces étapes terminées.

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] , puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.

   1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La [!DNL profile.cfg] fenêtre s&#39;affiche.

   1. Dans la [!DNL profile.cfg]fenêtre, cliquez avec le bouton droit **[!UICONTROL Directories]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Pour ajouter le nouveau répertoire à la fin de la liste des répertoires, cliquez avec le bouton droit de la souris sur le numéro ou le nom du dernier répertoire dans la liste, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Entrez le nom du nouveau répertoire : [!DNL Transform]
   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** de la souris en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL profile.cfg] de la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par l&#39;Adobe (y compris le profil), car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

