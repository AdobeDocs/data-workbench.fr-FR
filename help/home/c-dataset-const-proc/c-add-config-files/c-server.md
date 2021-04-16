---
description: Le paramètre Sample Bytes du fichier Server.cfg spécifie la taille du cache de données (en octets) pour l’outil de données.
title: Server.cfg
uuid: 7e789133-09fc-442d-b643-cca8620f4a97
exl-id: fb7667f6-4061-4bde-8a48-6489b24e0411
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 1%

---

# Server.cfg{#server-cfg}

Le paramètre Sample Bytes du fichier Server.cfg spécifie la taille du cache de données (en octets) pour l’outil de données.

La valeur par défaut est 250e6. Les instructions d&#39;ouverture et d&#39;enregistrement du fichier [!DNL Server.cfg] sont identiques à celles de [!DNL Log Processing Mode.cfg]. Voir [Mode de traitement du journal.cfg](../../../home/c-dataset-const-proc/c-add-config-files/t-log-proc-mode.md#task-e530907cb34f488182afe625e6d9e44a).

>[!NOTE]
>
>Comme le paramètre de ce fichier affecte les performances du système, veuillez contacter l&#39;Adobe avant d&#39;apporter des modifications.

Vous pouvez également limiter la taille du cache de données pour l’ordinateur de l’outil de données qui se connecte au serveur de l’outil de données en définissant le paramètre Taille maximale de l’échantillon dans le fichier [!DNL Insight.cfg]. Pour plus d&#39;informations, consultez le *Guide de l&#39;utilisateur Data Workbench*.
