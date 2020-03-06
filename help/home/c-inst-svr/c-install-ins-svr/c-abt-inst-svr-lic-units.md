---
description: Insight Server est disponible sous deux types de licence.
solution: Insight
title: A propos des unités de licence d’Insight Server
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# A propos des unités de licence d’Insight Server{#about-insight-server-license-units}

Insight Server est disponible sous deux types de licence.

Voici les deux types de licence :

* [Unité de traitement des données (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [FSU (File Server Unit)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Unité de traitement des données (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Ce type de [!DNL Insight Server] peut traiter, stocker et diffuser des données d’un jeu de données Adobe. Il peut éventuellement stocker les fichiers journaux qui contiennent les données source à partir desquelles le jeu de données est créé ou recevoir ces données d’une unité de serveur de [!DNL Insight Server] fichiers (FSU). Un DPU est le type d’ [!DNL Insight Server] interaction directe entre [!DNL Insight] [!DNL Report] les clients et les clients.

Si vous installez un [!DNL Insight Server] DPU, voir Procédures d’ [installation d’un DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)de serveur Insight.

## FSU (File Server Unit) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Ce type de serveur est configuré pour recevoir et stocker les données d’événement d’une ou de plusieurs instances de réplication de données [!DNL Sensor] ou d’événement ( [!DNL Repeater] fonctionnalité fournie avec une licence d’utilisation spéciale) et transmettre les données à une ou plusieurs unités de traitement de [!DNL Insight Server] données (DPU) pour la création de jeux de données Adobe. Les unités de traitement de données communiquent avec une unité de gestion de l&#39;alimentation à l&#39;aide d&#39;un protocole qui optimise le transfert des données d&#39;événement vers l&#39;unité de traitement de l&#39;alimentation et qui est beaucoup plus rapide que la gestion des fichiers journaux sur les serveurs de fichiers ordinaires. L&#39;utilisation d&#39;un FSU permet également de réduire les coûts matériels en permettant de stocker les données de journal sur du matériel de stockage à moindre coût et de réduire la complexité administrative en permettant à plusieurs [!DNL Sensors] de pointer vers un seul [!DNL Insight Server].

Si vous installez un [!DNL Insight Server] FSU, voir Procédures d’ [installation d’un FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)de serveur Insight.
