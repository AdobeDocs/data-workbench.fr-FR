---
description: Vous devez régulièrement surveiller vos fichiers journaux d’événements pour effectuer le suivi des messages d’événement du système Insight Server, qui sont consignés dans les <yyyymmdd>Fichiers -event.txt situés par défaut dans le dossier Events du répertoire d’installation du serveur Insight.
title: Surveillance des événements administratifs (serveur Insight)
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 1%

---

# Surveillance des événements administratifs{#monitoring-administrative-events}

Vous devez régulièrement surveiller vos fichiers journaux d’événements pour effectuer le suivi des messages d’événement du système Insight Server, qui sont consignés dans les `<YYYYMMDD>-event.txt` fichiers situés par défaut dans le dossier Events du répertoire d’installation du serveur Insight.

**Fréquence recommandée :** Toutes les 5-10 minutes

Vous pouvez surveiller ces événements à l’aide de la variable [!DNL Server Files Manager] in [!DNL Insight], votre outil de gestion automatisée, la variable [!DNL *-event.txt] ou la visionneuse d’événements Windows.

>[!NOTE]
>
>Les journaux d’événements administratifs sont complètement distincts de votre journal d’événements Windows, mais contiennent certains des mêmes événements. Les journaux d’événements administratifs contiennent des informations uniquement sur [!DNL Insight Server] événements .

**Pour afficher les fichiers events.txt à l’aide de la variable[!DNL Server Files Manager]**

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .
1. Cliquez avec le bouton droit de la souris sur l’icône d’une principale [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Events]** pour afficher son contenu.
1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* en regard du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**. Une coche s’affiche en regard du nom de fichier dans la variable [!DNL Temp] colonne .
1. Cliquez avec le bouton droit de la souris sur la coche dans la [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le fichier d’événement s’affiche dans une nouvelle fenêtre du Bloc-notes Windows Microsoft.

   ![Infos sur l’étape](assets/vis_FileManager_eventfile.png)

   Le [!DNL Server.log] dans le fichier [!DNL Trace] dans le dossier [!DNL Insight Server] Le répertoire d’installation contient des informations de journalisation plus détaillées.

**Pour afficher les événements via la visionneuse d’événements Windows**

* Cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Modification du répertoire du journal des événements administratifs**

Le fichier de configuration Logs d’événement administratif, [!DNL Administrative Events Log.cfg], spécifie le répertoire dans lequel la journalisation d’événement est générée.

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .

1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] vous souhaitez configurer et cliquer sur **[!UICONTROL Server Files]**.

1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour afficher son contenu. Le [!DNL Administrative Event Logs.cfg] se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* column pour [!DNL Administrative Event Logs.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la variable [!DNL Temp] column pour [!DNL Administrative Event Logs.cfg].

1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans le [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Dans le [!DNL Administrative Event Logs.cfg] fenêtre, cliquez sur **[!UICONTROL component]** pour afficher son contenu. Le chemin par défaut est le suivant : [!DNL Events] dans le dossier [!DNL Insight Server] répertoire d’installation.

   ![](assets/cfg_adminevents_examplevalues.png)

1. Dans le paramètre Path, saisissez le nom du répertoire dans lequel vous souhaitez générer les données de journalisation d’événement.
1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
   1. Dans le [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
