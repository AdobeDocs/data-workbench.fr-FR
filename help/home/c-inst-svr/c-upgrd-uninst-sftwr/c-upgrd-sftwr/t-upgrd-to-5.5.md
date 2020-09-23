---
description: Mise à niveau des composants du serveur pour Data Workbench 6.1 à partir de l’installation 5.4.
solution: Analytics
title: DWB Server mise à niveau 5.4 vers 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---


# Mise à niveau du serveur DWB : 5.4 vers 5.5{#dwb-server-upgrade-to}

Mise à niveau des composants du serveur pour Data Workbench 6.1 à partir de l’installation 5.4.

Par conséquent, la mise à niveau de la version [!DNL Insight] 5.4 à la version [!DNL Insight] 5.5 est relativement simple.

Vous pouvez également effectuer la mise à niveau directement de [!DNL Insight] 5.3 à [!DNL Insight] 5.5 en suivant les étapes ci-dessous. Assurez-vous d’effectuer toutes les tâches de mise à niveau répertoriées dans les sections [Mise à niveau d’Insight 5.4 vers 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) et [Mise à niveau d’Insight 5.4 vers 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) .

1. Arrêtez les [!DNL Insight Server] services sur tous les serveurs de la grappe, à l’exception de ceux [!DNL Insight Master Server].

   1. Copiez les nouveaux [!DNL ReportServer.exe] fichiers et [!DNL Insight.exe] les fichiers dans le dossier Software\Insight.

   1. Une fois que le [!DNL Insight] client a mis à jour, copiez les [!DNL InsightServer.exe] fichiers et [!DNL InsightServer64.exe] les fichiers dans le dossier \Bin.

   1. Patientez jusqu’ [!DNL Insight Master Server] au début, puis vérifiez la version s’exécutant via la [!DNL Connections] visualisation.

1. Sur la grappe [!DNL Master Server] du [!DNL Insight] client :

   1. Effectuez une copie locale du [!DNL Base] profil existant et renommez-le (BaseBackup, par exemple).
   1. Copiez le nouveau [!DNL Base] profil dans le dossier Profils.
   1. Répétez ces deux étapes pour le dossier Transformer.

1. Copiez le dossier Scripts du package de serveur dans le répertoire [!DNL Master Server] d’installation du serveur.
1. Copiez le [!DNL Terrain Images.cfg.off] fichier dans le dossier Composants du dossier [!DNL Master Server].
   **Pour mettre à niveau le logiciel client de[!DNL Insight]5.4 à 5.5**

Dans le [!DNL Insight.cfg] fichier, assurez-vous que le paramètre Mettre à jour le logiciel est défini sur TRUE.
