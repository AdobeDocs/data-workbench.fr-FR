---
description: Vous devez surveiller régulièrement l’espace disque disponible afin que toutes les machines du serveur de rapports continuent à fonctionner au plus haut niveau possible.
title: Surveillance de l’espace disque (serveur de rapports)
uuid: 590c8239-d20e-470e-b633-7785b75daaa6
exl-id: 0debd601-494f-4d4e-9452-c4d32678dc95
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 1%

---

# Surveillance de l’espace disque{#monitoring-disk-space}

{{eol}}

Vous devez surveiller régulièrement l’espace disque disponible afin que toutes les machines du serveur de rapports continuent à fonctionner au plus haut niveau possible.

Chaque [!DNL Report Server] La machine stocke les types de données suivants :

* Données du système d’exploitation
* Données du rapport
* Données système

>[!NOTE]
>
>Les consultants Adobe peuvent évaluer votre scénario d’utilisation pour vous aider à prévoir la quantité de stockage de données générée et requise par votre application logicielle Adobe. Pour demander une telle évaluation, veuillez contacter les services de conseil d’Adobe.

* [Surveillance de l’espace des données de rapport](../../../home/c-rpt-oview/c-admin-rpt/c-mon-disk-sp.md#section-ad0a63f3a6824e68acd675da0b6c5c23)
* [Sauvegarde des données du système d’exploitation, des rapports et du système](../../../home/c-rpt-oview/c-admin-rpt/c-mon-disk-sp.md#section-b5efb132ca5d4ee69a8608f9b4ab245b)

## Surveillance de l’espace des données de rapport {#section-ad0a63f3a6824e68acd675da0b6c5c23}

**Fréquence recommandée :** Toutes les 5-10 minutes

Veillez à prévoir suffisamment d’espace disque pour que vos rapports s’adaptent à la variable [!DNL Reports] dans le dossier [!DNL Report] répertoire d’installation.

## Sauvegarde des données du système d’exploitation, des rapports et du système {#section-b5efb132ca5d4ee69a8608f9b4ab245b}

**Fréquence recommandée :** Quotidien

Les données des rapports, systèmes et systèmes d’exploitation doivent être sauvegardées régulièrement et avec diligence à l’aide des systèmes de sauvegarde et de reprise sur sinistre normaux de votre entreprise.
