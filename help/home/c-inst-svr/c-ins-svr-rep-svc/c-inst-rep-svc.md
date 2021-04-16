---
description: Le service de réplication d’Insight Server vous permet de transmettre les données de événement collectées et stockées sur un ordinateur Insight Server à un autre ordinateur Insight Server.
title: Installation du service de réplication
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# Installation du service de réplication{#installing-the-replication-service}

Le service de réplication d’Insight Server vous permet de transmettre les données de événement collectées et stockées sur un ordinateur Insight Server à un autre ordinateur Insight Server.

En règle générale, l&#39;ordinateur sur lequel les données sont collectées et stockées est configuré pour s&#39;exécuter en tant qu&#39;ordinateur [!DNL Repeater]. Voir [Fonctionnalité de répétition](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). Le [!DNL Replication Service], qui est configuré par le fichier [!DNL Replicate.cfg], permet à un ordinateur [!DNL Insight Server] de récupérer les données de l&#39;ordinateur [!DNL Repeater] et de les stocker localement. La machine [!DNL Insight Server] est appelée machine de cible. Plusieurs unités de traitement de données [!DNL Insight Server] peuvent se connecter à un seul [!DNL Repeater] pour demander des copies des données du événement en vue de les inclure dans plusieurs jeux de données.

Vous pouvez utiliser le [!DNL Replication Service] dans les infrastructures réseau avec plusieurs couches de pare-feu pour obtenir des communications à port unique entre des composants séparés par des pare-feu.

**Pour installer la variable[!DNL Replication Service]**

Le fichier [!DNL Replicate.cfg] doit être installé dans le cadre de votre installation [!DNL Insight Server]. Vous pouvez trouver le fichier dans le dossier [!DNL Components] de votre répertoire d&#39;installation [!DNL Insight Server]. Si vous n&#39;avez pas ce fichier, contactez l&#39;Adobe.
