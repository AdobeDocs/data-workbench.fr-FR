---
description: La fonctionnalité de transformation s’exécute sur un ordinateur FSU Insight Server pour permettre l’exportation des données source du journal en vue de leur utilisation par d’autres applications.
title: Configuration de Transform
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Configuration de Transform{#configuring-transform}

La fonctionnalité de transformation s’exécute sur un ordinateur FSU Insight Server pour permettre l’exportation des données source du journal en vue de leur utilisation par d’autres applications.

[!DNL Transform] peuvent lire  [!DNL .vsl] des fichiers, des fichiers journaux, des fichiers XML et des données ODBC et exporter les données sous forme de  [!DNL .vsl] fichiers, de fichiers texte ou de fichiers texte délimités qui peuvent être utilisés par des routines de chargement d&#39;entrepôt de données, des agences de contrôle ou d&#39;autres cibles. L&#39;extraction et la transformation des données peuvent être effectuées en continu ou selon d&#39;autres méthodes planifiées. Chaque unité de traitement des données de événement [!DNL Insight Server] qui fournit la sortie de données modifiées doit exécuter [!DNL Transform].

>[!NOTE]
>
>En règle générale, [!DNL Transform] est installé sur un FSU [!DNL Insight Server]. Toutefois, votre mise en oeuvre peut nécessiter l’installation sur un DPU [!DNL Insight Server]. Pour plus d&#39;informations, contactez l&#39;Adobe.

Pour plus d&#39;informations sur la configuration système requise pour l&#39;installation, la configuration et l&#39;exploitation de [!DNL Transform], consultez le document *Configuration minimale requise*.

Adobe distribue la fonctionnalité [!DNL Transform] en tant que profil dans le fichier [!DNL .zip] pour le package de version [!DNL Insight Server]. Le profil [!DNL Transform] est un profil interne qui fournit des fonctionnalités supplémentaires à [!DNL Insight Server]. Comme pour tous les autres profils internes fournis par l&#39;Adobe, le profil ne doit pas être modifié. Toute personnalisation doit se produire dans votre jeu de données, dans vos profils spécifiques au rôle ou dans d&#39;autres profils que vous créez.

Le profil se compose des fichiers suivants :

* [!DNL Log Processing.cfg]
* [ ! DNL [!DNL Insight] Transform.cfg]
* [ ! DNL [!DNL Insight] Transform Mode.cfg]
* un fichier d&#39;inclusion d&#39;un jeu de données de traitement de journal

Tous ces fichiers se trouvent dans le dossier [!DNL Dataset] du profil.

**Pour installer le  [!DNL Transform] profil sur[!DNL Insight Server]**

>[!NOTE]
>
>Les instructions d&#39;installation suivantes supposent que vous avez installé [!DNL Insight] et établi une connexion entre [!DNL Insight] et [!DNL Insight Server] sur laquelle vous installez [!DNL Transform]. Si vous ne l&#39;avez pas fait, consultez le * [!DNL Insight] Guide de l&#39;utilisateur*.

1. Ouvrez le fichier [!DNL .zip] pour le package de publication [!DNL Insight Server] et ouvrez le dossier [!DNL Profiles] dans ce fichier [!DNL .zip].
1. Copiez le dossier [!DNL Transform] dans le dossier [!DNL Profiles] de votre répertoire d&#39;installation [!DNL Insight Server]. Vous souhaitez finir avec un dossier [!DNL ...\Profiles\Transform] sur votre [!DNL Insight Server], comme indiqué dans l&#39;exemple suivant.

   ![Infos sur l’étape](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Si vous avez suivi toutes les étapes d&#39;installation de [!DNL Insight Server] (voir [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), il se peut que le répertoire des Profils contienne déjà un dossier [!DNL Transform].

1. Suivez les étapes ci-après pour mettre à jour le fichier [!DNL profile.cfg] pour le profil avec lequel vous souhaitez utiliser [!DNL Transform]. Le jeu de données est retraité une fois ces étapes terminées.

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].

   1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La fenêtre [!DNL profile.cfg] s&#39;affiche.

   1. Dans la fenêtre [!DNL profile.cfg], cliquez avec le bouton droit de la souris sur **[!UICONTROL Directories]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Pour ajouter le nouveau répertoire à la fin de la liste des répertoires, cliquez avec le bouton droit de la souris sur le numéro ou le nom du dernier répertoire de la liste et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Entrez le nom du nouveau répertoire : [!DNL Transform]
   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la colonne [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL profile.cfg] de la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

      >[!NOTE]
      >
      >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par l&#39;Adobe (y compris le profil), car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.
