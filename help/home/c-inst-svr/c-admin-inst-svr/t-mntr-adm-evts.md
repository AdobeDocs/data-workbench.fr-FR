---
description: Vous devez régulièrement surveiller vos fichiers journaux de événement pour effectuer le suivi des messages du événement système d’Insight Server, qui sont enregistrés dans les fichiers <AAAAMMJJ>-événement.txt situés par défaut dans le dossier Événements du répertoire d’installation d’Insight Server.
solution: Analytics
title: Surveillance des événements administratifs
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 2%

---


# Surveillance des événements administratifs{#monitoring-administrative-events}

Vous devez régulièrement surveiller vos fichiers journaux de événement pour suivre les messages du événement système d’Insight Server, qui sont enregistrés dans les fichiers `<YYYYMMDD>-event.txt` situés par défaut dans le dossier Événements du répertoire d’installation d’Insight Server.

**Fréquence recommandée :** Toutes les 5 à 10 minutes

Vous pouvez contrôler ces événements à l’aide de l’ [!DNL Server Files Manager] outil de gestion automatisée, de l’outil de gestion [!DNL Insight]In, des [!DNL *-event.txt] fichiers ou du lecteur de Événement Windows.

>[!NOTE]
>
>Les journaux des Événements d&#39;administration sont complètement séparés de votre journal des Événements Windows, mais ils contiennent certains des mêmes événements. Les Journaux des Événements d&#39;administration ne contiennent que des informations sur les [!DNL Insight Server] événements.

**Pour vue des fichiers événements.txt via[!DNL Server Files Manager]**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Servers Manager.
1. Cliquez avec le bouton droit de la souris sur l’icône d’une principale [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez **[!UICONTROL Events]** pour en vue le contenu.
1. Cliquez avec le bouton droit de la souris sur la coche située dans la colonne du nom *du* serveur en regard du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît en regard du nom de fichier dans la [!DNL Temp] colonne.
1. Cliquez avec le bouton droit de la souris sur la coche de la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le fichier événement s&#39;affiche dans une nouvelle fenêtre du Bloc-notes Microsoft Windows.

   ![Infos sur l’étape](assets/vis_FileManager_eventfile.png)

   Le [!DNL Server.log] fichier situé dans le [!DNL Trace] dossier du répertoire d’ [!DNL Insight Server] installation contient des informations de journalisation plus détaillées.

**Pour vue des Événements via le lecteur de Événement Windows**

* Cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Pour modifier le répertoire Journal des Événements d&#39;administration**

Le fichier de configuration Journaux du Événement d&#39;administration [!DNL Administrative Events Log.cfg]spécifie le répertoire dans lequel la journalisation du événement est générée.

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Servers Manager.

1. Cliquez avec le bouton droit de la souris sur l’icône de la [!DNL Insight Server] fenêtre à configurer, puis cliquez sur **[!UICONTROL Server Files]**.

1. Dans le [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en vue le contenu. Le [!DNL Administrative Event Logs.cfg] fichier se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche de la colonne du nom *du* serveur [!DNL Administrative Event Logs.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Administrative Event Logs.cfg].

1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Dans la [!DNL Administrative Event Logs.cfg] fenêtre, cliquez **[!UICONTROL component]** pour en vue le contenu. Le chemin d’accès par défaut correspond au [!DNL Events] dossier du répertoire [!DNL Insight Server] d’installation.

   ![](assets/cfg_adminevents_examplevalues.png)

1. Dans le paramètre Path, saisissez le nom du répertoire dans lequel vous souhaitez générer les données de journalisation du événement.
1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** de la souris en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
   1. Dans la [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL Temp] colonne et sélectionnez **[!UICONTROL Save to]** > **[!UICONTROL server name]**.

