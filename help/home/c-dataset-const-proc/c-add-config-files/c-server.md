---
description: Le paramètre Sample Bytes (Exemples d’octets) du fichier Server.cfg spécifie la taille du cache de données (en octets) pour Data Workbench.
title: Server.cfg
uuid: 7e789133-09fc-442d-b643-cca8620f4a97
exl-id: fb7667f6-4061-4bde-8a48-6489b24e0411
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 1%

---

# Server.cfg{#server-cfg}

{{eol}}

Le paramètre Sample Bytes (Exemples d’octets) du fichier Server.cfg spécifie la taille du cache de données (en octets) pour Data Workbench.

La valeur par défaut est 250e6. Instructions pour ouvrir et enregistrer le [!DNL Server.cfg] sont identiques à ceux de [!DNL Log Processing Mode.cfg]. Voir [Mode de traitement du journal.cfg](../../../home/c-dataset-const-proc/c-add-config-files/t-log-proc-mode.md#task-e530907cb34f488182afe625e6d9e44a).

>[!NOTE]
>
>Comme le paramètre de ce fichier affecte les performances du système, veuillez contacter Adobe avant d’apporter des modifications.

Vous pouvez limiter davantage la taille du cache de données de l’ordinateur Data Workbench qui se connecte au serveur Data Workbench en définissant le paramètre Taille maximale de l’échantillon dans la variable [!DNL Insight.cfg] fichier . Pour plus d’informations, voir *Guide de l’utilisateur de Data Workbench*.
