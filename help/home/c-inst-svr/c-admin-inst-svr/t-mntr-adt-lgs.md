---
description: Les fichiers journaux d’audit effectuent le suivi de toutes les tentatives de connexion et de déconnexion d’Insight Server, dont chacun est connecté aux fichiers <AAAAMMJJ>-access.txt situés par défaut dans le dossier Audit du répertoire d’installation d’Insight Server.
solution: Analytics
title: Surveillance des journaux d’audit
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---


# Surveillance des journaux d’audit{#monitoring-audit-logs}

Les fichiers journaux d’audit effectuent le suivi de toutes les tentatives de connexion et de déconnexion d’Insight Server, dont chacune est consignée dans les `<YYYYMMDD>-access.txt` fichiers situés par défaut dans le dossier Audit du répertoire d’installation d’Insight Server.

**Fréquence recommandée :** Quotidien ou selon les besoins pour le dépannage

Les journaux d’audit peuvent s’avérer très utiles lors de la résolution des problèmes de connexion à [!DNL Insight Server]. Vous pouvez surveiller ces journaux à l’aide de votre outil de gestion automatisée ou en visualisant directement les [!DNL access.txt] fichiers.

**Pour vue des fichiers access.txt via[!DNL Server Files Manager]**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Servers Manager.
1. Cliquez avec le bouton droit de la souris sur l’icône d’une principale [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez **[!UICONTROL Audit]** pour en vue le contenu.
1. Cliquez avec le bouton droit de la souris sur la coche située dans la colonne du nom *du* serveur en regard du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît en regard du nom de fichier dans la [!DNL Temp] colonne.
1. Cliquez avec le bouton droit de la souris sur la nouvelle coche de la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le journal d&#39;audit s&#39;affiche dans une nouvelle fenêtre du Bloc-notes Microsoft Windows.

   ![Infos sur l’étape](assets/cfg_accesscontrol_accessFile.png)

