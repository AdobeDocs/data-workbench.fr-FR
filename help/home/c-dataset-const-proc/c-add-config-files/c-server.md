---
description: Le paramètre Sample Bytes du fichier Server.cfg spécifie la taille du cache de données (en octets) pour l’outil de données.
solution: Analytics
title: Server.cfg
topic: Data workbench
uuid: 7e789133-09fc-442d-b643-cca8620f4a97
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Server.cfg{#server-cfg}

Le paramètre Sample Bytes du fichier Server.cfg spécifie la taille du cache de données (en octets) pour l’outil de données.

La valeur par défaut est 250e6. Les instructions d’ouverture et d’enregistrement du [!DNL Server.cfg] fichier sont les mêmes que celles pour [!DNL Log Processing Mode.cfg]. Voir [Log Processing Mode.cfg](../../../home/c-dataset-const-proc/c-add-config-files/t-log-proc-mode.md#task-e530907cb34f488182afe625e6d9e44a).

>[!NOTE]
>
>Comme le paramètre de ce fichier affecte les performances du système, contactez Adobe avant d’apporter des modifications.

Vous pouvez également limiter la taille du cache de données pour l’ordinateur de l’outil de données qui se connecte au serveur de l’outil de données en définissant le paramètre Taille d’échantillon maximale dans le [!DNL Insight.cfg] fichier. For more information, see the *Data Workbench User Guide*.
