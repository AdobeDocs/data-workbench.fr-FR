---
description: Le paramètre Sample Bytes (Exemples d’octets) du fichier Server.cfg spécifie la taille du cache de données (en octets) pour Data Workbench.
title: Server.cfg
uuid: 7e789133-09fc-442d-b643-cca8620f4a97
exl-id: fb7667f6-4061-4bde-8a48-6489b24e0411
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 1%

---

# Server.cfg{#server-cfg}

Le paramètre Sample Bytes (Exemples d’octets) du fichier Server.cfg spécifie la taille du cache de données (en octets) pour Data Workbench.

La valeur par défaut est 250e6. Les instructions d’ouverture et d’enregistrement du fichier [!DNL Server.cfg] sont les mêmes que pour [!DNL Log Processing Mode.cfg]. Voir [Mode de traitement du journal.cfg](../../../home/c-dataset-const-proc/c-add-config-files/t-log-proc-mode.md#task-e530907cb34f488182afe625e6d9e44a).

>[!NOTE]
>
>Comme le paramètre de ce fichier affecte les performances du système, veuillez contacter Adobe avant d’apporter des modifications.

Vous pouvez limiter davantage la taille du cache de données de l’ordinateur Data Workbench qui se connecte au serveur Data Workbench en définissant le paramètre Taille maximale de l’échantillon dans le fichier [!DNL Insight.cfg] . Pour plus d’informations, consultez le *Guide de l’utilisateur du Data Workbench*.
