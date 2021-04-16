---
description: Vous devez régulièrement surveiller vos fichiers journaux de événement pour effectuer le suivi des messages du événement système d’Insight Server, qui sont enregistrés dans les fichiers <AAAAMMJJ>-événement.txt situés par défaut dans le dossier Événements du répertoire d’installation d’Insight Server.
title: Surveillance des événements administratifs
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 2%

---

# Surveillance des événements administratifs{#monitoring-administrative-events}

Vous devez régulièrement surveiller vos fichiers journaux de événement pour suivre les messages du événement système d’Insight Server, qui sont enregistrés dans les fichiers `<YYYYMMDD>-event.txt` situés par défaut dans le dossier Événements du répertoire d’installation d’Insight Server.

**Fréquence recommandée :** toutes les 5 à 10 minutes

Vous pouvez surveiller ces événements à l&#39;aide de [!DNL Server Files Manager] dans [!DNL Insight], de votre outil de gestion automatisée, des fichiers [!DNL *-event.txt] ou du lecteur de Événement Windows.

>[!NOTE]
>
>Les journaux des Événements d&#39;administration sont complètement séparés de votre journal des Événements Windows, mais ils contiennent certains des mêmes événements. Les Journaux des Événements d&#39;administration ne contiennent des informations que sur [!DNL Insight Server] événements.

**Pour vue des fichiers événements.txt via[!DNL Server Files Manager]**

1. Dans [!DNL Insight], sur l&#39;onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l&#39;espace de travail Servers Manager.
1. Cliquez avec le bouton droit de la souris sur l&#39;icône d&#39;un principal [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Events]** pour en vue le contenu.
1. Cliquez avec le bouton droit sur la coche de la colonne *nom du serveur* en regard du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît en regard du nom de fichier dans la colonne [!DNL Temp].
1. Cliquez avec le bouton droit sur la coche de la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le fichier événement s&#39;affiche dans une nouvelle fenêtre du Bloc-notes Microsoft Windows.

   ![Infos sur l’étape](assets/vis_FileManager_eventfile.png)

   Le fichier [!DNL Server.log] situé dans le dossier [!DNL Trace] du répertoire d&#39;installation [!DNL Insight Server] contient des informations de journalisation plus détaillées.

**Pour vue des Événements via le lecteur de Événement Windows**

* Cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Pour modifier le répertoire Journal des Événements d&#39;administration**

Le fichier de configuration Journaux du Événement d&#39;administration [!DNL Administrative Events Log.cfg] spécifie le répertoire dans lequel la journalisation du événement est générée.

1. Dans [!DNL Insight], sur l&#39;onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l&#39;espace de travail Servers Manager.

1. Cliquez avec le bouton droit de la souris sur l&#39;icône [!DNL Insight Server] que vous souhaitez configurer, puis cliquez sur **[!UICONTROL Server Files]**.

1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour en vue le contenu. Le fichier [!DNL Administrative Event Logs.cfg] se trouve dans ce répertoire.

1. Cliquez avec le bouton droit sur la coche de la colonne *nom du serveur* pour [!DNL Administrative Event Logs.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la colonne [!DNL Temp] pour [!DNL Administrative Event Logs.cfg].

1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Dans la fenêtre [!DNL Administrative Event Logs.cfg], cliquez sur **[!UICONTROL component]** pour en vue le contenu. Le chemin d’accès par défaut est le dossier [!DNL Events] dans le répertoire d’installation de [!DNL Insight Server].

   ![](assets/cfg_adminevents_examplevalues.png)

1. Dans le paramètre Path, saisissez le nom du répertoire dans lequel vous souhaitez générer les données de journalisation du événement.
1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
   1. Dans la colonne [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
