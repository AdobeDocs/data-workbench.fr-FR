---
description: Les données d’événement doivent être sauvegardées quotidiennement à l’aide des systèmes de sauvegarde normaux et des procédures de reprise sur sinistre de votre entreprise.
title: Sauvegarde des données d’événement
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
exl-id: 5afeb3a2-a2e7-4155-8fb9-1abc9c22c3c6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 5%

---

# Sauvegarde des données d’événement{#backing-up-event-data}

{{eol}}

Les données d’événement doivent être sauvegardées quotidiennement à l’aide des systèmes de sauvegarde normaux et des procédures de reprise sur sinistre de votre entreprise.

**Fréquence recommandée :** Quotidien

[!DNL Insight Server] commence les nouveaux fichiers journaux à 00h00 GMT tous les jours. Adobe vous recommande de sauvegarder les fichiers journaux chaque jour peu après 12h00 GMT afin que vous puissiez capturer toutes les données du jour précédent. Par exemple, la sauvegarde de tous les fichiers journaux à 00h05 GMT le 15 décembre capture toutes les données du 14 décembre. [!DNL Insight Server] n’a pas besoin d’être arrêté lors des sauvegardes des fichiers journaux, et toutes les fonctionnalités restent disponibles.

## Sauvegarde des données d’intégration, du système d’exploitation, de sortie et du système {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Fréquence recommandée :** Quotidien

L’intégration, le système d’exploitation, la sortie et les données système doivent être sauvegardés régulièrement et avec diligence à l’aide des systèmes de sauvegarde et de reprise sur sinistre normaux de votre entreprise.
