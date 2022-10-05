---
description: Les fichiers journaux d’audit effectuent le suivi de toutes les tentatives de connexion à Insight Server et de déconnexion, chacune d’elles étant consignée dans la variable <yyyymmdd>Fichiers -access.txt situés par défaut dans le dossier Audit du répertoire d’installation du serveur Insight.
title: Surveillance des journaux d’audit
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# Surveillance des journaux d’audit{#monitoring-audit-logs}

{{eol}}

Les fichiers journaux d’audit effectuent le suivi de toutes les tentatives de connexion à Insight Server et de déconnexion, chacune d’elles étant consignée dans la variable `<YYYYMMDD>-access.txt` fichiers situés par défaut dans le dossier Audit du répertoire d’installation du serveur Insight.

**Fréquence recommandée :** Quotidienne ou selon les besoins pour le dépannage

Les journaux d’audit peuvent s’avérer très utiles lors de la résolution des problèmes de connexion à [!DNL Insight Server]. Vous pouvez surveiller ces journaux à l’aide de votre outil de gestion automatisée ou en affichant [!DNL access.txt] directement.

**Pour afficher les fichiers access.txt à l’aide du[!DNL Server Files Manager]**

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .
1. Cliquez avec le bouton droit de la souris sur l’icône d’une principale [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Audit]** pour afficher son contenu.
1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* en regard du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**. Une coche s’affiche en regard du nom de fichier dans la variable [!DNL Temp] colonne .
1. Cliquez avec le bouton droit de la souris sur la nouvelle coche dans la [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le journal d’audit s’affiche dans une nouvelle fenêtre du Bloc-notes Windows Microsoft.

   ![Infos sur l’étape](assets/cfg_accesscontrol_accessFile.png)
