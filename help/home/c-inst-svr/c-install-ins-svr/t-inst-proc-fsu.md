---
description: Les instructions d’installation d’un FSU de serveur Insight et de configuration pour un usage administratif sont très similaires à celles d’installation et de configuration d’un DPU de serveur Insight.
solution: Insight
title: Procédures d’installation d’un FSU de serveur Insight
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Procédures d’installation d’un FSU de serveur Insight{#installation-procedures-for-an-insight-server-fsu}

Les instructions d’installation d’un FSU de serveur Insight et de configuration pour un usage administratif sont très similaires à celles d’installation et de configuration d’un DPU de serveur Insight.

Pour *MS System Center Endpoint Protection* sur les serveurs Windows 2012, ces exécutables doivent être ajoutés aux processus **exclus :**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Pour installer et configurer un [!DNL Insight Server] FSU, vous devez exécuter les tâches suivantes :

1. Installez les fichiers [!DNL Insight Server] du programme.
1. Installez le certificat [!DNL Insight Server] numérique.
1. Vérifiez les paramètres du port dans le [!DNL Communications.cfg] fichier.
1. Modifiez le [!DNL Access Control.cfg] fichier pour autoriser l’accès administratif à [!DNL the Server] depuis [!DNL the Client].
1. Modifiez le [!DNL server.address] fichier pour définir l’emplacement réseau du serveur.
1. Définissez les paramètres d&#39;utilisation de la mémoire Windows comme décrit.
1. Enregistrez-vous [!DNL Insight Server] en tant que service Windows comme décrit.

   Pour obtenir des instructions sur la configuration des sources de données, des autorisations et des communications pour un [!DNL Insight Server] FSU, consultez le Guide *de configuration des jeux de* données.

