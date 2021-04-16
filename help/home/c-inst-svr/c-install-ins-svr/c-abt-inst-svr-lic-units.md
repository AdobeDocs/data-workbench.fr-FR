---
description: Insight Server est disponible sous deux types de licence.
title: À propos des unités de licence de serveur Insight
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
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

Ce type de [!DNL Insight Server] peut traiter, stocker et diffuser des données d&#39;un jeu de données d&#39;Adobe. Il peut éventuellement stocker les fichiers journaux qui contiennent les données source à partir desquelles le jeu de données est créé ou recevoir ces données d&#39;une unité de serveur de fichiers [!DNL Insight Server] (FSU). Un DPU est le type de [!DNL Insight Server] avec lequel les clients [!DNL Insight] et [!DNL Report] interagissent directement.

Si vous installez un [!DNL Insight Server] DPU, voir [Procédures d’installation d’un DPU de serveur Insight](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## Unité de serveur de fichier (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Ce type de serveur est configuré pour recevoir et stocker des données de événement provenant d&#39;une ou de plusieurs instances de réplication de données [!DNL Sensor] ou de événement (fonctionnalité [!DNL Repeater] fournie avec une licence d&#39;utilisation spéciale) et diffuser les données vers une ou plusieurs unités de traitement de données (DPU) [!DNL Insight Server] pour la création de jeux de données d&#39;Adobe. Les unités de traitement des données communiquent avec une unité de traitement des données à l&#39;aide d&#39;un protocole qui optimise le transfert des données de événement vers l&#39;unité de traitement des données et qui est beaucoup plus rapide que la gestion de fichiers journaux sur des serveurs de fichiers ordinaires. L&#39;utilisation d&#39;un FSU réduit également les coûts matériels en permettant de stocker les données de journal sur du matériel d&#39;enregistrement à moindre coût et réduit la complexité administrative en permettant à plusieurs [!DNL Sensors] de pointer vers un [!DNL Insight Server] unique.

Si vous installez un FSU [!DNL Insight Server], consultez la section [Procédures d’installation d’un FSU de serveur Insight](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
