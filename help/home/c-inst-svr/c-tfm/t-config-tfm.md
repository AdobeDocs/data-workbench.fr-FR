---
description: La fonctionnalité de transformation s’exécute sur un ordinateur FSU de serveur Insight afin de permettre l’exportation des données source du journal pour une utilisation par d’autres applications.
title: Configuration de Transform
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Configuration de Transform{#configuring-transform}

{{eol}}

La fonctionnalité de transformation s’exécute sur un ordinateur FSU de serveur Insight afin de permettre l’exportation des données source du journal pour une utilisation par d’autres applications.

[!DNL Transform] peut lire [!DNL .vsl] fichiers, fichiers journaux, fichiers XML et données ODBC et exporter les données sous la forme [!DNL .vsl] fichiers, fichiers texte ou fichiers texte délimités pouvant être utilisés par les routines de chargement de l’entrepôt de données, les agences de contrôle ou d’autres cibles. L&#39;extraction et la transformation des données peuvent être effectuées sur une base continue ou planifiée. Chaque [!DNL Insight Server] Le FSU qui fournit la sortie des données d’événement modifiées doit s’exécuter. [!DNL Transform].

>[!NOTE]
>
>En règle générale, [!DNL Transform] est installé sur un [!DNL Insight Server] FSU. Toutefois, votre mise en oeuvre peut nécessiter une installation sur un [!DNL Insight Server] DPU. Pour plus d’informations, contactez l’Adobe.

Pour plus d’informations sur la configuration système requise pour l’installation, la configuration et le fonctionnement [!DNL Transform], reportez-vous à la section *Configuration système minimale* document.

Adobe distribue la variable [!DNL Transform] fonctionnalité en tant que profil dans la fonction [!DNL .zip] pour le fichier [!DNL Insight Server] module de mise à jour. Le [!DNL Transform] Un profil est un profil interne qui fournit des fonctionnalités supplémentaires à [!DNL Insight Server]. Comme pour tous les autres profils internes fournis par Adobe, le profil ne doit pas être modifié. Toute personnalisation doit se produire dans votre jeu de données, dans les profils spécifiques à un rôle ou dans d’autres profils que vous créez.

Le profil se compose des fichiers suivants :

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* un fichier d’inclusion de jeu de données de traitement de journal ;

Tous ces fichiers se trouvent dans la variable [!DNL Dataset] pour le profil.

**Pour installer le [!DNL Transform] profile sur[!DNL Insight Server]**

>[!NOTE]
>
>Les instructions d’installation suivantes supposent que vous avez installé [!DNL Insight] et établi une connexion entre [!DNL Insight] et le [!DNL Insight Server] sur lequel vous effectuez l’installation [!DNL Transform]. Si vous ne l’avez pas fait, reportez-vous au [!DNL Insight] Guide de l’utilisateur*.

1. Ouvrez le [!DNL .zip] pour le fichier [!DNL Insight Server] et ouvrez le module externe [!DNL Profiles] dossier dans [!DNL .zip] fichier .
1. Copiez le [!DNL Transform] vers le dossier [!DNL Profiles] dans votre dossier [!DNL Insight Server] répertoire d’installation. Vous voulez obtenir un [!DNL ...\Profiles\Transform] sur votre [!DNL Insight Server] comme illustré dans l’exemple suivant.

   ![Infos sur l’étape](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Si vous avez suivi toutes les étapes d’installation [!DNL Insight Server] (voir [Serveur Insight](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), vous pouvez déjà avoir une [!DNL Transform] dans le répertoire Profils .

1. Procédez comme suit pour mettre à jour la variable [!DNL profile.cfg] pour le profil avec lequel vous souhaitez utiliser [!DNL Transform]. Le jeu de données se retraite une fois ces étapes terminées.

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .

   1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Le [!DNL profile.cfg] s’affiche.

   1. Dans le [!DNL profile.cfg]fenêtre, clic droit **[!UICONTROL Directories]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Pour ajouter le nouveau répertoire à la fin de la liste des répertoires, cliquez avec le bouton droit de la souris sur le numéro ou le nom du dernier répertoire de la liste, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Saisissez le nom du nouveau répertoire : [!DNL Transform]
   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche pour [!DNL profile.cfg] dans le [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe (y compris le profil), car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.
