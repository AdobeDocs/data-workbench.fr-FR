---
description: Mise à niveau des composants de serveur pour l’outil de données version 6.1 à partir de l’installation 5.4.
solution: Insight
title: DWB Server version 5.4 à 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mise à niveau du serveur DWB : 5.4 à 5.5{#dwb-server-upgrade-to}

Mise à niveau des composants de serveur pour l’outil de données version 6.1 à partir de l’installation 5.4.

Par conséquent, la mise à niveau de [!DNL Insight] 5.4 à [!DNL Insight] 5.5 est relativement simple.

Vous pouvez également effectuer une mise à niveau directe de la version [!DNL Insight] .3 vers [!DNL Insight] .5 en suivant les étapes ci-dessous. Veillez à effectuer toutes les tâches de mise à niveau répertoriées dans les sections [Mise à niveau d’Insight 5.4 vers 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) et [Mise à niveau d’Insight 5.4 vers 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) .

1. Arrêtez les [!DNL Insight Server] services sur tous les serveurs de la grappe, à l’exception de [!DNL Insight Master Server].

   1. Copiez les nouveaux [!DNL ReportServer.exe] et [!DNL Insight.exe] fichiers dans le dossier Software\Insight.

   1. Une fois que le [!DNL Insight] client a mis à jour, copiez les fichiers [!DNL InsightServer.exe] et [!DNL InsightServer64.exe] dans le dossier \Bin.

   1. Attendez le [!DNL Insight Master Server] démarrage de, puis vérifiez la version qui s’exécute via la [!DNL Connections] visualisation.

1. Sur la grappe [!DNL Master Server] dans le [!DNL Insight] client :

   1. Effectuez une copie locale du [!DNL Base] profil existant et renommez-le (BaseBackup, par exemple).
   1. Copiez le nouveau [!DNL Base] profil dans le dossier Profils.
   1. Répétez ces deux étapes pour le dossier Transformer.

1. Copiez le dossier Scripts du package du serveur dans le [!DNL Master Server] répertoire d’installation du serveur.
1. Copiez le [!DNL Terrain Images.cfg.off] fichier dans le dossier Composants du dossier [!DNL Master Server].
   **Pour mettre à niveau le logiciel client de[!DNL Insight]5.4 à 5.5**

Dans le [!DNL Insight.cfg] fichier, assurez-vous que le paramètre Mettre à jour le logiciel est défini sur TRUE.
