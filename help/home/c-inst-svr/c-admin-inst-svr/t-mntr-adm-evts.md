---
description: Vous devez surveiller régulièrement vos fichiers journaux d’événements pour effectuer le suivi des messages d’événement du système Insight Server, qui sont consignés dans les fichiers <YYYMMDD>-event.txt situés par défaut dans le dossier Events du répertoire d’installation du serveur Insight.
title: Surveillance des événements administratifs
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 2%

---

# Surveillance des événements administratifs{#monitoring-administrative-events}

Vous devez surveiller régulièrement vos fichiers journaux d’événements pour suivre les messages d’événement du système Insight Server, qui sont consignés dans les fichiers `<YYYYMMDD>-event.txt` situés par défaut dans le dossier Events du répertoire d’installation Insight Server.

**Fréquence recommandée :** Toutes les 5-10 minutes

Vous pouvez surveiller ces événements à l’aide de [!DNL Server Files Manager] dans [!DNL Insight], de votre outil de gestion automatisée, des fichiers [!DNL *-event.txt] ou de la visionneuse d’événements Windows.

>[!NOTE]
>
>Les journaux d’événements administratifs sont complètement distincts de votre journal d’événements Windows, mais contiennent certains des mêmes événements. Les journaux d’événements administratifs contiennent des informations uniquement sur les événements [!DNL Insight Server].

**Pour afficher les fichiers events.txt à l’aide de la variable[!DNL Server Files Manager]**

1. Dans [!DNL Insight], dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l’espace de travail Gestionnaire de serveurs.
1. Cliquez avec le bouton droit de la souris sur l’icône d’une principale [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.
1. Dans la balise [!DNL Server Files Manager], cliquez sur **[!UICONTROL Events]** pour en visualiser le contenu.
1. Cliquez avec le bouton droit sur la coche dans la colonne *nom du serveur* en regard du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**. Une coche s’affiche en regard du nom de fichier dans la colonne [!DNL Temp].
1. Cliquez avec le bouton droit sur la coche dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le fichier d’événement s’affiche dans une nouvelle fenêtre du Bloc-notes Microsoft Windows.

   ![Infos sur l’étape](assets/vis_FileManager_eventfile.png)

   Le fichier [!DNL Server.log] situé dans le dossier [!DNL Trace] du répertoire d’installation [!DNL Insight Server] contient des informations de journalisation plus détaillées.

**Pour afficher les événements via la visionneuse d’événements Windows**

* Cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Modification du répertoire du journal des événements administratifs**

Le fichier de configuration Logs d’événements administratifs, [!DNL Administrative Events Log.cfg], spécifie le répertoire dans lequel la journalisation des événements est générée.

1. Dans [!DNL Insight], dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l’espace de travail Gestionnaire de serveurs.

1. Cliquez avec le bouton droit de la souris sur l’icône [!DNL Insight Server] que vous souhaitez configurer, puis cliquez sur **[!UICONTROL Server Files]**.

1. Dans la balise [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour en visualiser le contenu. Le fichier [!DNL Administrative Event Logs.cfg] se trouve dans ce répertoire.

1. Cliquez avec le bouton droit sur la coche dans la colonne *nom du serveur* pour [!DNL Administrative Event Logs.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche s’affiche dans la colonne [!DNL Temp] pour [!DNL Administrative Event Logs.cfg].

1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Dans la fenêtre [!DNL Administrative Event Logs.cfg], cliquez sur **[!UICONTROL component]** pour en visualiser le contenu. Le chemin par défaut est le dossier [!DNL Events] dans le répertoire d’installation de [!DNL Insight Server].

   ![](assets/cfg_adminevents_examplevalues.png)

1. Dans le paramètre Path, saisissez le nom du répertoire dans lequel vous souhaitez générer les données de journalisation d’événement.
1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
   1. Dans la balise [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
