---
description: Insight Server est disponible sous deux types de licence.
title: À propos des unités de licence de serveur Insight
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---

# À propos des unités de licence de serveur Insight{#about-insight-server-license-units}

{{eol}}

Insight Server est disponible sous deux types de licence.

Voici les deux types de licence :

* [Unité de traitement des données (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [Unité de serveur de fichier (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Unité de traitement des données (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Ce type de [!DNL Insight Server] peut traiter, stocker et diffuser des données d’un jeu de données d’Adobe. Il peut éventuellement stocker les fichiers journaux qui contiennent les données source à partir desquelles le jeu de données est construit, ou il peut recevoir ces données d’une [!DNL Insight Server] Unité de serveur de fichiers (FSU). Un DPU est le type de [!DNL Insight Server] avec [!DNL Insight] et [!DNL Report] les clients interagissent directement.

Si vous installez une [!DNL Insight Server] DPU, voir [Procédures d’installation d’un DPU de serveur Insight](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## Unité de serveur de fichier (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Ce type de serveur est configuré pour recevoir et stocker des données d’événement d’un ou de plusieurs [!DNL Sensor] ou les instances de réplication de données d’événement ( [!DNL Repeater] fonctionnalité fournie avec une licence d’utilisation spéciale) et diffuser les données vers une ou plusieurs [!DNL Insight Server] Unités de traitement des données (DPU) pour la création de jeux de données d’Adobe. Les DPU communiquent avec un FSU à l’aide d’un protocole qui optimise le transfert des données d’événement vers le DPU et qui est beaucoup plus rapide que la maintenance des fichiers journaux sur les serveurs de fichiers ordinaires. L’utilisation d’un FSU réduit également les coûts matériels en permettant aux données de journal d’être stockées sur du matériel de stockage à moindre coût et réduit la complexité administrative en autorisant plusieurs [!DNL Sensors] pour pointer vers une seule [!DNL Insight Server].

Si vous installez une [!DNL Insight Server] FSU, voir [Procédures d’installation d’un FSU de serveur Insight](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
