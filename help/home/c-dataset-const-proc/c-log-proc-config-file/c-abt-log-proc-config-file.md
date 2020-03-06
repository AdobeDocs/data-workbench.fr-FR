---
description: Le fichier Log Processing.cfg contrôle la phase de traitement du journal de la construction des jeux de données, au cours de laquelle les données non ordonnées sont lues à partir des sources de données (appelées sources de journaux), et des filtres et des transformations sont appliqués aux données.
solution: Analytics
title: A propos du fichier de configuration de traitement du journal
topic: Data workbench
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# A propos du fichier de configuration de traitement du journal{#about-the-log-processing-configuration-file}

Le fichier Log Processing.cfg contrôle la phase de traitement du journal de la construction des jeux de données, au cours de laquelle les données non ordonnées sont lues à partir des sources de données (appelées sources de journaux), et des filtres et des transformations sont appliqués aux données.

Vous devez modifier le [!DNL Log Processing.cfg] fichier pour effectuer l’une des tâches suivantes de configuration du jeu de données :

* Spécification des sources du journal. Voir Sources [de journal](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* Détermination des entrées du journal qui entrent dans le jeu de données lors du traitement du journal. Voir Filtres [de données](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) et Condition [d’entrée dans le](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)journal.

* Activation du fractionnement des ID de suivi avec de grandes quantités de données d’événement. Voir [Séparation des clés](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).
* Configuration d’un serveur de outils de données à exécuter en tant qu’unité de serveur de fichiers. Voir [Configuration d’une unité](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)de serveur de fichiers Insight Server.
* Configuration d’un serveur de outils de données pour qu’il s’exécute en tant que serveur de normalisation centralisé. Voir [Configuration d’une unité](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)de serveur de fichiers Insight Server.

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] peuvent contenir des instructions supplémentaires pour la phase de traitement du journal de la construction des jeux de données. Ces fichiers existent dans le répertoire DataSet\Log Processing pour tout profil hérité. Ils définissent généralement des paramètres spécifiques à l’application (tels que les paramètres de configuration spécifiques au Web pour l’application Site). Pour plus d’informations sur [!DNL Log Processing Dataset Include] les fichiers, voir Fichiers [inclus dans le jeu de](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)données. Pour plus d’informations sur les paramètres de configuration spécifiques au Web pour Site, voir Paramètres [de configuration pour les données](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md)Web.

