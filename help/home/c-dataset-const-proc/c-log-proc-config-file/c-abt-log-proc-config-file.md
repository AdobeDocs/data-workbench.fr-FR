---
description: Le fichier Log Processing.cfg contrôle la phase de traitement du journal de la construction des jeux de données, au cours de laquelle les données non ordonnées sont lues à partir des sources de données (appelées sources de journaux), et les filtres et transformations sont appliqués aux données.
title: À propos du fichier de configuration de traitement du journal
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
exl-id: 11ee3298-272d-46c8-bcfe-e485b01606b1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 5%

---

# À propos du fichier de configuration de traitement du journal{#about-the-log-processing-configuration-file}

Le fichier Log Processing.cfg contrôle la phase de traitement du journal de la construction des jeux de données, au cours de laquelle les données non ordonnées sont lues à partir des sources de données (appelées sources de journaux), et les filtres et transformations sont appliqués aux données.

Vous devez modifier le fichier [!DNL Log Processing.cfg] pour exécuter l&#39;une des tâches de configuration de jeu de données suivantes :

* Spécification des sources de journal. Voir [Sources de journal](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* Détermination des entrées du journal qui entrent dans le jeu de données lors du traitement du journal. Voir [Filtres de données](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) et [Condition d’entrée du journal](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).

* Activation du fractionnement des ID de suivi avec de grandes quantités de données de événement. Voir [Séparation des clés](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).
* Configuration d’un serveur d’outils de données à exécuter en tant qu’unité de serveur de fichiers. Voir [Configuration d’une unité de serveur de fichiers du serveur Insight](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).
* Configuration d’un serveur d’outils de données à exécuter en tant que serveur de normalisation centralisé. Voir [Configuration d’une unité de serveur de fichiers du serveur Insight](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] peuvent contenir des instructions supplémentaires pour la phase de traitement du journal de la construction des jeux de données. Ces fichiers existent dans le répertoire Dataset\Log Processing pour tout profil hérité. Ils définissent généralement des paramètres spécifiques à l&#39;application (tels que des paramètres de configuration spécifiques au Web pour l&#39;application Site). Pour plus d&#39;informations sur les fichiers [!DNL Log Processing Dataset Include], consultez [Jeu de données Inclure les fichiers](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Pour plus d’informations sur les paramètres de configuration spécifiques au Web pour le site, voir [Paramètres de configuration pour les données Web](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md).
