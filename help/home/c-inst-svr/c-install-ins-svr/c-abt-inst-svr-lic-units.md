---
description: Insight Server est disponible sous deux types de licence.
title: À propos des unités de licence de serveur Insight
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---

# À propos des unités de licence de serveur Insight{#about-insight-server-license-units}

Insight Server est disponible sous deux types de licence.

Voici les deux types de licence :

* [Unité de traitement des données (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [Unité de serveur de fichier (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Unité de traitement des données (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Ce type de [!DNL Insight Server] peut traiter, stocker et fournir des données d’un jeu de données d’Adobe. Il peut éventuellement stocker les fichiers journaux qui contiennent les données source à partir desquelles le jeu de données est construit, ou il peut recevoir ces données d’une [!DNL Insight Server] unité de serveur de fichiers (FSU). Un DPU est le type de [!DNL Insight Server] avec lequel les clients [!DNL Insight] et [!DNL Report] interagissent directement.

Si vous installez un DPU [!DNL Insight Server], voir [Procédures d’installation d’un DPU de serveur Insight](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## Unité de serveur de fichier (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Ce type de serveur est configuré pour recevoir et stocker des données d’événement d’une ou de plusieurs instances de réplication de données d’événement ( [!DNL Repeater] fonctionnalité fournie avec une licence d’utilisation spéciale) et transmettre les données à une ou plusieurs unités de traitement de données (DPU) [!DNL Insight Server] pour la création de jeux de données d’Adobe. [!DNL Sensor] Les DPU communiquent avec un FSU à l’aide d’un protocole qui optimise le transfert des données d’événement vers le DPU et qui est beaucoup plus rapide que la maintenance des fichiers journaux sur les serveurs de fichiers ordinaires. L’utilisation d’un FSU réduit également les coûts matériels en permettant aux données de journal d’être stockées sur du matériel de stockage à moindre coût et réduit la complexité administrative en permettant à plusieurs [!DNL Sensors] de pointer vers une seule [!DNL Insight Server].

Si vous installez un FSU [!DNL Insight Server], consultez les [Procédures d’installation d’un FSU de serveur Insight](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
