---
description: Le service Insight ServerReplication vous permet de transmettre les données d’événement collectées et stockées sur une machine Insight Server à une autre machine Insight Server.
title: Installation du service de réplication
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# Installation du service de réplication{#installing-the-replication-service}

Le service Insight ServerReplication vous permet de transmettre les données d’événement collectées et stockées sur une machine Insight Server à une autre machine Insight Server.

En règle générale, la machine sur laquelle les données sont collectées et stockées est configurée pour fonctionner comme une machine [!DNL Repeater]. Voir [Fonctionnalité du répéteur](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). [!DNL Replication Service], configuré par le fichier [!DNL Replicate.cfg], permet à une machine [!DNL Insight Server] de récupérer les données de la machine [!DNL Repeater] et de les stocker localement. La machine [!DNL Insight Server] est appelée machine cible. Plusieurs [!DNL Insight Server] DPU peuvent se connecter à une seule [!DNL Repeater] pour demander des copies des données d’événement à inclure dans plusieurs jeux de données.

Vous pouvez utiliser la balise [!DNL Replication Service] dans les infrastructures réseau comportant plusieurs couches de pare-feu pour établir des communications à port unique entre les composants séparés par des pare-feu.

**Pour installer le[!DNL Replication Service]**

Le fichier [!DNL Replicate.cfg] doit être installé dans le cadre de votre installation [!DNL Insight Server]. Vous pouvez trouver le fichier dans le dossier [!DNL Components] de votre répertoire d’installation [!DNL Insight Server]. Si vous ne disposez pas de ce fichier, contactez Adobe.
