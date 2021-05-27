---
description: La fonctionnalité de transformation s’exécute sur un ordinateur FSU de serveur Insight afin de permettre l’exportation des données source du journal pour une utilisation par d’autres applications.
title: Configuration de Transform
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Configuration de Transform{#configuring-transform}

La fonctionnalité de transformation s’exécute sur un ordinateur FSU de serveur Insight afin de permettre l’exportation des données source du journal pour une utilisation par d’autres applications.

[!DNL Transform] peut lire  [!DNL .vsl] des fichiers, des fichiers journaux, des fichiers XML et des données ODBC et exporter les données sous forme de  [!DNL .vsl] fichiers, de fichiers texte ou de fichiers texte délimités pouvant être utilisés par les routines de chargement de l’entrepôt de données, les agences de contrôle ou d’autres cibles. L&#39;extraction et la transformation des données peuvent être effectuées sur une base continue ou planifiée. Chaque FSU [!DNL Insight Server] qui fournit la sortie des données d’événement modifié doit exécuter [!DNL Transform].

>[!NOTE]
>
>En règle générale, [!DNL Transform] est installé sur un FSU [!DNL Insight Server]. Cependant, votre mise en oeuvre peut nécessiter une installation sur un DPU [!DNL Insight Server]. Pour plus d’informations, contactez Adobe.

Pour plus d’informations sur la configuration requise du système pour l’installation, la configuration et le fonctionnement [!DNL Transform], voir le document *Configuration système minimale* .

Adobe distribue la fonctionnalité [!DNL Transform] sous la forme d’un profil dans le fichier [!DNL .zip] pour le module de version [!DNL Insight Server]. Le profil [!DNL Transform] est un profil interne qui fournit des fonctionnalités supplémentaires à [!DNL Insight Server]. Comme pour tous les autres profils internes fournis par Adobe, le profil ne doit pas être modifié. Toute personnalisation doit se produire dans votre jeu de données, dans les profils spécifiques à un rôle ou dans d’autres profils que vous créez.

Le profil se compose des fichiers suivants :

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* un fichier d’inclusion de jeu de données de traitement de journal ;

Tous ces fichiers se trouvent dans le dossier [!DNL Dataset] du profil.

**Pour installer le  [!DNL Transform] profil sur[!DNL Insight Server]**

>[!NOTE]
>
>Les instructions d’installation suivantes supposent que vous avez installé [!DNL Insight] et établi une connexion entre [!DNL Insight] et la [!DNL Insight Server] sur laquelle vous installez [!DNL Transform]. Si vous ne l’avez pas fait, consultez le * [!DNL Insight] Guide de l’utilisateur*.

1. Ouvrez le fichier [!DNL .zip] pour le module de version [!DNL Insight Server] et ouvrez le dossier [!DNL Profiles] dans ce fichier [!DNL .zip].
1. Copiez le dossier [!DNL Transform] dans le dossier [!DNL Profiles] de votre répertoire d’installation [!DNL Insight Server]. Vous souhaitez obtenir un dossier [!DNL ...\Profiles\Transform] sur votre [!DNL Insight Server] comme illustré dans l’exemple suivant.

   ![Infos sur l’étape](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Si vous avez suivi toutes les étapes d’installation de [!DNL Insight Server] (voir [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), un dossier [!DNL Transform] peut déjà se trouver dans le répertoire Profils .

1. Suivez les étapes ci-après pour mettre à jour le fichier [!DNL profile.cfg] du profil avec lequel vous souhaitez utiliser [!DNL Transform]. Le jeu de données se retraite une fois ces étapes terminées.

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].

   1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La fenêtre [!DNL profile.cfg] s’affiche.

   1. Dans la fenêtre [!DNL profile.cfg]cliquez avec le bouton droit de la souris sur **[!UICONTROL Directories]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Pour ajouter le nouveau répertoire à la fin de la liste des répertoires, cliquez avec le bouton droit de la souris sur le numéro ou le nom du dernier répertoire de la liste, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Saisissez le nom du nouveau répertoire : [!DNL Transform]
   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans la balise [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL profile.cfg] dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** *&lt;**[!UICONTROL profile name]***.

      >[!NOTE]
      >
      >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe (y compris le profil), car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.
