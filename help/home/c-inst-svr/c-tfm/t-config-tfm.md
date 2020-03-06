---
description: La fonctionnalité de transformation s’exécute sur un ordinateur FSU Insight Server pour permettre l’exportation des données source du journal en vue de les utiliser par d’autres applications.
solution: Insight
title: Configuration de la transformation
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Configuration de la transformation{#configuring-transform}

La fonctionnalité de transformation s’exécute sur un ordinateur FSU Insight Server pour permettre l’exportation des données source du journal en vue de les utiliser par d’autres applications.

[!DNL Transform] peuvent lire [!DNL .vsl] des fichiers, des fichiers journaux, des fichiers XML et des données ODBC et exporter les données sous forme de [!DNL .vsl] fichiers, de fichiers texte ou de fichiers texte délimités pouvant être utilisés par des routines de chargement d’entrepôt de données, des agences de contrôle ou d’autres cibles. L’extraction et la transformation des données peuvent être effectuées sur une base continue ou planifiée. Chaque [!DNL Insight Server] FSU qui fournit la sortie des données d’événement modifiées doit s’exécuter [!DNL Transform].

>[!NOTE]
>
>Généralement, [!DNL Transform] est installé sur un [!DNL Insight Server] FSU. Toutefois, votre mise en oeuvre peut nécessiter une installation sur un [!DNL Insight Server] DPU. Pour plus d’informations, contactez Adobe.

Pour plus d’informations sur la configuration système requise pour l’installation, la configuration et le fonctionnement [!DNL Transform], voir le document Configuration système requise ** minimale.

Adobe distribue la [!DNL Transform] fonctionnalité sous forme de profil dans le [!DNL .zip] fichier pour le package de [!DNL Insight Server] version. Le [!DNL Transform] profil est un profil interne qui fournit des fonctionnalités supplémentaires à [!DNL Insight Server]. Comme pour tous les autres profils internes fournis par Adobe, le profil ne doit pas être modifié. Toute personnalisation doit se produire dans votre jeu de données, dans vos profils spécifiques au rôle ou dans d’autres profils que vous créez.

Le profil se compose des fichiers suivants :

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* un fichier d&#39;inclusion de jeu de données de traitement de journal

Tous ces fichiers se trouvent dans le [!DNL Dataset] dossier du profil.

**Pour installer le[!DNL Transform]profil sur[!DNL Insight Server]**

>[!NOTE]
>
>Les instructions d’installation suivantes supposent que vous avez installé [!DNL Insight] et établi une connexion entre [!DNL Insight] et le [!DNL Insight Server] sur lequel vous installez [!DNL Transform]. Si vous ne l’avez pas fait, consultez le * [!DNL Insight] Guide de l’utilisateur*.

1. Ouvrez le [!DNL .zip] fichier du [!DNL Insight Server] package de version et ouvrez le [!DNL Profiles] dossier dans ce [!DNL .zip] fichier.
1. Copiez le [!DNL Transform] dossier dans le [!DNL Profiles] dossier du répertoire [!DNL Insight Server] d’installation. Vous souhaitez trouver un [!DNL ...\Profiles\Transform] dossier sur votre site [!DNL Insight Server] comme illustré dans l’exemple suivant.

   ![Infos sur l’étape](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Si vous avez suivi toutes les étapes de l’installation [!DNL Insight Server] (voir [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), vous disposez peut-être déjà d’un [!DNL Transform] dossier dans le répertoire Profils.

1. Procédez comme suit pour mettre à jour le [!DNL profile.cfg] fichier du profil avec lequel vous souhaitez utiliser [!DNL Transform]. Le jeu de données est retraité une fois ces étapes terminées.

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] , puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.

   1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La [!DNL profile.cfg] fenêtre s&#39;affiche.

   1. Dans la [!DNL profile.cfg]fenêtre, cliquez avec le bouton droit **[!UICONTROL Directories]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Pour ajouter le nouveau répertoire à la fin de la liste des répertoires, cliquez avec le bouton droit de la souris sur le numéro ou le nom du dernier répertoire de la liste, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Entrez le nom du nouveau répertoire : [!DNL Transform]
   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL profile.cfg] dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe (y compris le profil), car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

