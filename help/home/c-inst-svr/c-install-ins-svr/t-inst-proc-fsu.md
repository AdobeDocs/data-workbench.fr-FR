---
description: Les instructions d’installation d’un FSU d’Insight Server et de configuration pour une utilisation administrative sont très similaires à celles d’installation et de configuration d’un DPU d’Insight Server.
title: Procédures d’installation d’un FSU de serveur Insight
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Procédures d’installation d’un FSU de serveur Insight{#installation-procedures-for-an-insight-server-fsu}

Les instructions d’installation d’un FSU d’Insight Server et de configuration pour une utilisation administrative sont très similaires à celles d’installation et de configuration d’un DPU d’Insight Server.

Pour *MS System Center Endpoint Protection* sur les serveurs Windows 2012, ces exécutables doivent être ajoutés aux **processus exclus:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Pour installer et configurer un FSU [!DNL Insight Server], vous devez exécuter les tâches suivantes :

1. Installez les fichiers de programme [!DNL Insight Server].
1. Installez le certificat numérique [!DNL Insight Server].
1. Vérifiez les paramètres de port dans le fichier [!DNL Communications.cfg].
1. Modifiez le fichier [!DNL Access Control.cfg] pour autoriser l&#39;accès administratif à [!DNL the Server] à partir de [!DNL the Client].
1. Modifiez le fichier [!DNL server.address] pour définir l’emplacement réseau du serveur.
1. Définissez les paramètres d&#39;utilisation de la mémoire Windows comme décrit.
1. Enregistrez [!DNL Insight Server] en tant que service Windows comme décrit.

   Pour obtenir des instructions sur la configuration des sources de données, des autorisations et des communications pour un FSU [!DNL Insight Server], consultez le *Guide de configuration des jeux de données*.
