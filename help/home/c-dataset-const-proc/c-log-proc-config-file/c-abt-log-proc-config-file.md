---
description: Le fichier Log Processing.cfg contrôle la phase de traitement du journal de la construction du jeu de données, au cours de laquelle les données non ordonnées sont lues à partir des sources de données (appelées sources de journal), et les filtres et transformations sont appliqués aux données.
title: À propos du fichier de configuration de traitement du journal
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
exl-id: 11ee3298-272d-46c8-bcfe-e485b01606b1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 5%

---

# À propos du fichier de configuration de traitement du journal{#about-the-log-processing-configuration-file}

{{eol}}

Le fichier Log Processing.cfg contrôle la phase de traitement du journal de la construction du jeu de données, au cours de laquelle les données non ordonnées sont lues à partir des sources de données (appelées sources de journal), et les filtres et transformations sont appliqués aux données.

Vous devez modifier la variable [!DNL Log Processing.cfg] pour effectuer l’une des tâches de configuration de jeu de données suivantes :

* Spécification des sources de journal. Voir [Sources de journalisation](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* Déterminer quelles entrées de journal entrent dans le jeu de données lors du traitement du journal. Voir [Filtres de données](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) et [Condition d’entrée du journal](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).

* Permet de fractionner les identifiants de suivi avec de grandes quantités de données d’événement. Voir [Fractionnement des clés](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).
* Configuration d’un serveur Data Workbench à exécuter en tant qu’unité de serveur de fichiers. Voir [Configuration d’une unité du serveur de fichiers Insight](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).
* Configuration d’un serveur Data Workbench pour une exécution en tant que serveur de normalisation centralisé. Voir [Configuration d’une unité du serveur de fichiers Insight](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] Les fichiers peuvent contenir des instructions supplémentaires pour la phase de traitement des journaux de la construction du jeu de données. Ces fichiers existent dans le répertoire Dataset\Log Processing pour tout profil hérité. Ils définissent généralement des paramètres spécifiques à l’application (tels que les paramètres de configuration spécifiques au web pour l’application Site). Pour plus d’informations sur [!DNL Log Processing Dataset Include] fichiers, voir [Fichiers d’inclusion de jeux de données](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Pour plus d’informations sur les paramètres de configuration spécifiques au web pour Site, voir [Paramètres de configuration des données web](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md).
