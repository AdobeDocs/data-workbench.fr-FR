---
description: Vous devez surveiller régulièrement vos fichiers journaux d’événements afin d’effectuer le suivi des messages d’événement système du serveur Insight, qui sont enregistrés dans les fichiers <AAAAMMJJ>-event.txt situés par défaut dans le dossier Events du répertoire d’installation du serveur Insight.
solution: Insight
title: Contrôle des événements administratifs
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Contrôle des événements administratifs{#monitoring-administrative-events}

Vous devez surveiller régulièrement vos fichiers journaux d’événements afin d’effectuer le suivi des messages d’événement système du serveur Insight, qui sont consignés dans les `<YYYYMMDD>-event.txt` fichiers situés par défaut dans le dossier Events du répertoire d’installation d’Insight Server.

**Fréquence recommandée :** Toutes les 5 à 10 minutes

Vous pouvez surveiller ces événements à l’aide de [!DNL Server Files Manager] in, de votre outil de gestion automatisée, des [!DNL Insight][!DNL *-event.txt] fichiers ou de l’Observateur d’événements Windows.

>[!NOTE]
>
>Les journaux des événements d&#39;administration sont complètement séparés de votre journal des événements Windows, mais ils contiennent certains des mêmes événements. Les journaux des événements d’administration contiennent uniquement des informations sur [!DNL Insight Server] les événements.

**Pour afficher les fichiers events.txt dans le[!DNL Server Files Manager]**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs.
1. Cliquez avec le bouton droit de la souris sur l’icône d’un élément actif [!DNL Insight Server] , puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans la [!DNL Server Files Manager], cliquez **[!UICONTROL Events]** pour en afficher le contenu.
1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom *du* serveur en regard du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît en regard du nom de fichier dans la [!DNL Temp] colonne.
1. Cliquez avec le bouton droit de la souris sur la coche dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le fichier d’événement s’affiche dans une nouvelle fenêtre du Bloc-notes Microsoft Windows.

   ![Infos sur l’étape](assets/vis_FileManager_eventfile.png)

   Le [!DNL Server.log] fichier situé dans le [!DNL Trace] dossier du répertoire d’ [!DNL Insight Server] installation contient des informations de journalisation plus détaillées.

**Pour afficher les événements via l’Observateur d’événements Windows**

* Cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Pour modifier le répertoire Journal des événements d’administration**

Le fichier de configuration Journaux d’événements d’administration [!DNL Administrative Events Log.cfg]indique le répertoire dans lequel la journalisation des événements est générée.

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs.

1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] fichier à configurer, puis cliquez sur **[!UICONTROL Server Files]**.

1. Dans la [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en afficher le contenu. Le [!DNL Administrative Event Logs.cfg] fichier se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom *du* serveur [!DNL Administrative Event Logs.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Administrative Event Logs.cfg].

1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Dans la [!DNL Administrative Event Logs.cfg] fenêtre, cliquez **[!UICONTROL component]** pour en afficher le contenu. Le chemin d’accès par défaut est le [!DNL Events] dossier du répertoire [!DNL Insight Server] d’installation.

   ![](assets/cfg_adminevents_examplevalues.png)

1. Dans le paramètre Path, saisissez le nom du répertoire dans lequel vous souhaitez générer les données de journalisation des événements.
1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
   1. Dans la [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL Temp] colonne et sélectionnez **[!UICONTROL Save to]** > **[!UICONTROL server name]**.

