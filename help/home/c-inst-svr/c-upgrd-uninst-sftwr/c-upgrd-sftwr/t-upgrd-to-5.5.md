---
description: Mise à niveau des composants du serveur pour Data Workbench 6.1 à partir de l’installation 5.4.
title: Mise à niveau du serveur DWB 5.4 vers 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# Mise à niveau du serveur DWB : 5.4 vers 5.5{#dwb-server-upgrade-to}

{{eol}}

Mise à niveau des composants du serveur pour Data Workbench 6.1 à partir de l’installation 5.4.

Par conséquent, la mise à niveau depuis [!DNL Insight] 5.4 à [!DNL Insight] 5.5 est relativement simple.

Vous pouvez également effectuer une mise à niveau directement à partir de [!DNL Insight] 5.3 à [!DNL Insight] 5.5 en suivant les étapes ci-dessous. Assurez-vous d’effectuer toutes les tâches de mise à niveau répertoriées dans la section [Mise à niveau d’Insight 5.4 vers 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) et le [Mise à niveau d’Insight 5.4 vers 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) .

1. Arrêtez le [!DNL Insight Server] sur tous les serveurs de la grappe, à l’exception des services [!DNL Insight Master Server].

   1. Copiez le nouveau [!DNL ReportServer.exe] et [!DNL Insight.exe] dans le dossier Software\Insight .

   1. Après la [!DNL Insight] Le client a été mis à jour, copiez la variable [!DNL InsightServer.exe] et [!DNL InsightServer64.exe] dans le dossier \Bin.

   1. Attendez que la variable [!DNL Insight Master Server] pour démarrer, puis vérifiez la version qui s’exécute via la fonction [!DNL Connections] visualisation.

1. Sur le noeud [!DNL Master Server] dans le [!DNL Insight] client :

   1. Effectuez une copie locale de la [!DNL Base] et renommez-le (par exemple, BaseBackup).
   1. Copiez le nouveau [!DNL Base] profile vers le dossier Profils .
   1. Répétez ces deux étapes pour le dossier Transform .

1. Copiez le dossier Scripts du package du serveur sur le [!DNL Master Server] dans le répertoire d’installation du serveur.
1. Copiez le [!DNL Terrain Images.cfg.off] dans le dossier Components de la propriété [!DNL Master Server].
   **Pour mettre à niveau le logiciel client depuis [!DNL Insight] 5.4 à 5.5**

Dans le [!DNL Insight.cfg] , assurez-vous que le paramètre Mettre à jour le logiciel est défini sur TRUE.
