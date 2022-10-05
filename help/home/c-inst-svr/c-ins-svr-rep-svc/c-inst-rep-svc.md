---
description: Le service Insight ServerReplication vous permet de transmettre les données d’événement collectées et stockées sur une machine Insight Server à une autre machine Insight Server.
title: Installation du service de réplication
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# Installation du service de réplication{#installing-the-replication-service}

{{eol}}

Le service Insight ServerReplication vous permet de transmettre les données d’événement collectées et stockées sur une machine Insight Server à une autre machine Insight Server.

En règle générale, la machine sur laquelle les données sont collectées et stockées est configurée pour fonctionner comme une [!DNL Repeater] machine. Voir [Fonctionnalité du répéteur](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). Le [!DNL Replication Service], qui est configuré par la variable [!DNL Replicate.cfg] , active une [!DNL Insight Server] machine pour récupérer les données de [!DNL Repeater] et les stocker localement. Le [!DNL Insight Server] est appelée machine cible. Multiple [!DNL Insight Server] Les DPU peuvent se connecter à un seul [!DNL Repeater] pour demander des copies des données d’événement à inclure dans plusieurs jeux de données.

Vous pouvez utiliser la variable [!DNL Replication Service] dans les infrastructures réseau comportant plusieurs couches de pare-feu afin d’établir des communications entre des composants séparés par des pare-feu à port unique et à port unique.

**Pour installer le[!DNL Replication Service]**

Le [!DNL Replicate.cfg] doit être installé dans le cadre de votre [!DNL Insight Server] installation. Vous pouvez trouver le fichier dans la variable [!DNL Components] de votre dossier [!DNL Insight Server] répertoire d’installation. Si vous ne disposez pas de ce fichier, contactez Adobe.
