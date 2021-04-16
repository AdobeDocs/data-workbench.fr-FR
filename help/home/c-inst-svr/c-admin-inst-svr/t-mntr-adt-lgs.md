---
description: Les fichiers journaux d’audit effectuent le suivi de toutes les tentatives de connexion et de déconnexion d’Insight Server, dont chacun est connecté aux fichiers <AAAAMMJJ>-access.txt situés par défaut dans le dossier Audit du répertoire d’installation d’Insight Server.
title: Surveillance des journaux d’audit
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# Surveillance des journaux d’audit{#monitoring-audit-logs}

Les fichiers journaux d’audit effectuent le suivi de toutes les tentatives de connexion et de déconnexion d’Insight Server, dont chacun est connecté aux fichiers `<YYYYMMDD>-access.txt` situés par défaut dans le dossier Audit du répertoire d’installation d’Insight Server.

**Fréquence recommandée :** Quotidiennement ou selon les besoins pour le dépannage

Les journaux d&#39;audit peuvent s&#39;avérer très utiles lors de la résolution des problèmes de connexion à [!DNL Insight Server]. Vous pouvez surveiller ces journaux à l&#39;aide de votre outil de gestion automatisée ou en affichant directement les fichiers [!DNL access.txt].

**Pour vue des fichiers access.txt via[!DNL Server Files Manager]**

1. Dans [!DNL Insight], sur l&#39;onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l&#39;espace de travail Servers Manager.
1. Cliquez avec le bouton droit de la souris sur l&#39;icône d&#39;un principal [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Audit]** pour en vue le contenu.
1. Cliquez avec le bouton droit sur la coche de la colonne *nom du serveur* en regard du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît en regard du nom de fichier dans la colonne [!DNL Temp].
1. Cliquez avec le bouton droit sur la nouvelle coche dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le journal d&#39;audit s&#39;affiche dans une nouvelle fenêtre du Bloc-notes Microsoft Windows.

   ![Infos sur l’étape](assets/cfg_accesscontrol_accessFile.png)
