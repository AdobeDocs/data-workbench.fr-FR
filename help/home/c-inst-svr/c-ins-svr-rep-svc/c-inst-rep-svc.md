---
description: Le service de réplication d’Insight Server vous permet de transmettre les données de événement collectées et stockées sur un ordinateur Insight Server à un autre ordinateur Insight Server.
solution: Analytics
title: Installation du service de réplication
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---


# Installation du service de réplication{#installing-the-replication-service}

Le service de réplication d’Insight Server vous permet de transmettre les données de événement collectées et stockées sur un ordinateur Insight Server à un autre ordinateur Insight Server.

En règle générale, l’ordinateur sur lequel les données sont collectées et stockées est configuré pour s’exécuter en tant qu’ [!DNL Repeater] ordinateur. Voir Fonctionnalités [](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md)de répétition. Le [!DNL Replication Service], qui est configuré par le [!DNL Replicate.cfg] fichier, permet à un [!DNL Insight Server] ordinateur de récupérer les données de l&#39; [!DNL Repeater] ordinateur et de les stocker localement. La [!DNL Insight Server] machine est appelée machine à cible. Plusieurs [!DNL Insight Server] unités de traitement de données peuvent se connecter à un seul [!DNL Repeater] afin de demander des copies des données du événement pour les inclure dans plusieurs jeux de données.

Vous pouvez utiliser les [!DNL Replication Service] infrastructures réseau avec plusieurs couches de pare-feu afin d&#39;obtenir des communications d&#39;un port à un port entre des composants séparés par des pare-feu.

**Pour installer la variable[!DNL Replication Service]**

Le [!DNL Replicate.cfg] fichier doit être installé dans le cadre de votre [!DNL Insight Server] installation. Le fichier se trouve dans le [!DNL Components] dossier du répertoire d’ [!DNL Insight Server] installation. Si vous n&#39;avez pas ce fichier, contactez l&#39;Adobe.
