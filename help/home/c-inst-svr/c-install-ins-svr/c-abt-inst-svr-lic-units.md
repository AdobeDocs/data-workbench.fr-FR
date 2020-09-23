---
description: Insight Server est disponible sous deux types de licence.
solution: Analytics
title: À propos des unités de licence de serveur Insight
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---


# À propos des unités de licence de serveur Insight{#about-insight-server-license-units}

Insight Server est disponible sous deux types de licence.

Voici les deux types de licence :

* [Unité de traitement des données](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [Unité de serveur de fichier (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Unité de traitement des données {#section-bf589e13cf5c43a58f8f85a457de6f65}

Ce type de [!DNL Insight Server] peut traiter, stocker et diffuser des données provenant d&#39;un jeu de données d&#39;Adobe. It optionally can store the log files that contain the source data from which the dataset is constructed, or it can receive that data from an [!DNL Insight Server] File Server Unit (FSU). Un DPU est le type de [!DNL Insight Server] dialogue direct entre [!DNL Insight] et [!DNL Report] les clients.

Si vous installez un [!DNL Insight Server] DPU, voir Procédures d’ [installation d’un DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)Insight Server.

## Unité de serveur de fichier (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Ce type de serveur est configuré pour recevoir et stocker des données de événement provenant d&#39;une ou de plusieurs instances de réplication de données [!DNL Sensor] ou de événement ( [!DNL Repeater] fonctionnalité fournie avec une licence d&#39;utilisation spéciale) et diffuser les données vers une ou plusieurs unités de traitement de [!DNL Insight Server] données (DPU) afin de créer des jeux de données d&#39;Adobe. Les unités de traitement des données communiquent avec une unité de traitement des données à l&#39;aide d&#39;un protocole qui optimise le transfert des données de événement vers l&#39;unité de traitement des données et qui est beaucoup plus rapide que la gestion de fichiers journaux sur des serveurs de fichiers ordinaires. The use of an FSU also reduces hardware costs by enabling log data to be stored on lower cost storage hardware and reduces administrative complexity by allowing multiple [!DNL Sensors] to point to a single [!DNL Insight Server].

Si vous installez un [!DNL Insight Server] FSU, consultez Procédures d’ [installation d’un FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)Insight Server.
