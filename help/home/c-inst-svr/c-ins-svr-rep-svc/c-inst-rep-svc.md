---
description: Le service de réplication de serveur Insight vous permet de transmettre les données d’événement collectées et stockées sur un ordinateur serveur Insight à un autre ordinateur serveur Insight.
solution: Insight
title: Installation du service de réplication
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Installation du service de réplication{#installing-the-replication-service}

Le service de réplication de serveur Insight vous permet de transmettre les données d’événement collectées et stockées sur un ordinateur serveur Insight à un autre ordinateur serveur Insight.

En règle générale, l’ordinateur sur lequel les données sont collectées et stockées est configuré pour s’exécuter en tant qu’ [!DNL Repeater] ordinateur. Voir Fonctionnalité [Répéter](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). Le [!DNL Replication Service], qui est configuré par le [!DNL Replicate.cfg] fichier, permet à un [!DNL Insight Server] [!DNL Repeater] ordinateur de récupérer les données de l’ordinateur et de les stocker localement. La [!DNL Insight Server] machine est appelée machine cible. Plusieurs [!DNL Insight Server] processeurs numériques peuvent se connecter à un seul [!DNL Repeater] afin de demander des copies des données d’événement pour les inclure dans plusieurs jeux de données.

Vous pouvez utiliser la [!DNL Replication Service] fonctionnalité dans les infrastructures réseau avec plusieurs couches de pare-feu pour obtenir des communications de port unique à port unique entre des composants séparés par des pare-feu.

**Pour installer le[!DNL Replication Service]**

Le [!DNL Replicate.cfg] fichier doit être installé dans le cadre de votre [!DNL Insight Server] installation. Le fichier se trouve dans le [!DNL Components] dossier du répertoire [!DNL Insight Server] d’installation. Si vous ne disposez pas de ce fichier, contactez Adobe.
