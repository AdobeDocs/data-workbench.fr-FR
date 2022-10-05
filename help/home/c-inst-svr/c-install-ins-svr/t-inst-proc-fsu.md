---
description: Les instructions d’installation d’un FSU de serveur Insight et de configuration pour une utilisation administrative sont très similaires à celles d’installation et de configuration d’un DPU de serveur Insight.
title: Procédures d’installation d’un FSU de serveur Insight
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Procédures d’installation d’un FSU de serveur Insight{#installation-procedures-for-an-insight-server-fsu}

{{eol}}

Les instructions d’installation d’un FSU de serveur Insight et de configuration pour une utilisation administrative sont très similaires à celles d’installation et de configuration d’un DPU de serveur Insight.

Pour *Protection des points de terminaison MS System Center* Dans les serveurs Windows 2012, ces exécutables doivent être ajoutés au **Processus exclus :**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Pour installer et configurer une [!DNL Insight Server] FSU, vous devez effectuer les tâches suivantes :

1. Installez le [!DNL Insight Server] fichiers de programme.
1. Installez le [!DNL Insight Server] certificat numérique.
1. Vérifiez les paramètres du port dans le [!DNL Communications.cfg] fichier .
1. Modifiez le [!DNL Access Control.cfg] pour autoriser l’accès administrateur à [!DNL the Server] de [!DNL the Client].
1. Modifiez le [!DNL server.address] pour définir l’emplacement réseau du serveur.
1. Définissez les paramètres d’utilisation de la mémoire Windows comme décrit.
1. Enregistrer [!DNL Insight Server] comme service Windows, comme décrit.

   Pour obtenir des instructions sur la configuration de sources de données, d’autorisations et de communications pour une [!DNL Insight Server] FSU, voir *Guide de configuration des jeux de données*.
