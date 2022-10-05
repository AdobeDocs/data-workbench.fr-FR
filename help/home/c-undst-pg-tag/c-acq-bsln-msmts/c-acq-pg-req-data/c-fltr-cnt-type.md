---
description: L’objectif de la fonctionnalité de filtrage de type contenu de Capteur est d’éliminer la nécessité de stocker et de traiter des informations qui ne sont pas utiles à des fins d’analyse.
title: Filtrage par type de contenu
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# Filtrage par type de contenu{#filtering-by-content-type}

{{eol}}

L’objectif de la fonctionnalité de filtrage de type contenu de Capteur est d’éliminer la nécessité de stocker et de traiter des informations qui ne sont pas utiles à des fins d’analyse.

La plupart des données de requête disponibles par le biais de l’API d’un serveur web ne sont pas utiles dans l’analyse commerciale. Le stockage et le traitement sont coûteux et [!DNL Sensor’s] le filtrage de type contenu permet d’éviter tout stockage et traitement inutiles.

Pour optimiser les performances de traitement des données de journaux Web et réduire la quantité de données de mesure à stocker, [!DNL Site] acquiert des données de mesure (données de requête, entrées de journal, données de journal, etc.) pour toutes les requêtes de type de contenu web, à l’exception des types de contenu spécifiquement répertoriés (tels que les feuilles de style en cascade, les demandes d’image, etc.), qui sont filtrés avant d’être transmis au serveur Data Workbench par [!DNL Sensor]. Ce filtrage peut être désactivé pour un serveur web entier et il peut également être remplacé pour un objet de contenu spécifique en ajoutant la paire nom-valeur &quot;Log=1&quot; à la chaîne de requête d’un objet incorporé particulier (par exemple, [!DNL https://www.mysite.com/advertisement.gif?Log=1]).
