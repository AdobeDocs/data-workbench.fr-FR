---
description: Mise à niveau des composants du serveur pour Data Workbench 6.1 à partir de l’installation 5.4.
title: DWB Server mise à niveau 5.4 vers 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# Mise à niveau du serveur DWB : 5.4 vers 5.5{#dwb-server-upgrade-to}

Mise à niveau des composants du serveur pour Data Workbench 6.1 à partir de l’installation 5.4.

Par conséquent, la mise à niveau de [!DNL Insight] 5.4 à [!DNL Insight] 5.5 est relativement simple.

Vous pouvez également effectuer la mise à niveau directement de [!DNL Insight] 5.3 vers [!DNL Insight] 5.5 en suivant les étapes ci-dessous. Assurez-vous d’effectuer toutes les tâches de mise à niveau répertoriées dans la section [Mise à niveau d’Insight 5.4 vers 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) et la section [Mise à niveau d’Insight 5.4 vers 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9).

1. Arrêtez les services [!DNL Insight Server] sur tous les serveurs de la grappe, à l&#39;exception de [!DNL Insight Master Server].

   1. Copiez les nouveaux fichiers [!DNL ReportServer.exe] et [!DNL Insight.exe] dans le dossier Software\Insight.

   1. Après la mise à jour du client [!DNL Insight], copiez les fichiers [!DNL InsightServer.exe] et [!DNL InsightServer64.exe] dans le dossier \Bin.

   1. Attendez que [!DNL Insight Master Server] soit début, puis vérifiez la version s’exécutant via la visualisation [!DNL Connections].

1. Sur le client [!DNL Master Server] du cluster [!DNL Insight] :

   1. Effectuez une copie locale du profil [!DNL Base] existant et renommez-le (par exemple, BaseBackup).
   1. Copiez le nouveau profil [!DNL Base] dans le dossier Profils.
   1. Répétez ces deux étapes pour le dossier Transformer.

1. Copiez le dossier Scripts du package de serveur dans [!DNL Master Server] dans le répertoire d’installation du serveur.
1. Copiez le fichier [!DNL Terrain Images.cfg.off] dans le dossier Composants de [!DNL Master Server].
   **Pour mettre à niveau le logiciel client de  [!DNL Insight] 5.4 à 5.5**

Dans le fichier [!DNL Insight.cfg], assurez-vous que le paramètre Mettre à jour le logiciel est défini sur TRUE.
