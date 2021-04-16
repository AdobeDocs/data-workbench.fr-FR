---
description: La fonctionnalité de filtrage de type de contenu de Sensor a pour objectif d’éliminer la nécessité de stocker et de traiter des informations qui ne sont pas utiles à des fins d’analyse.
title: Filtrage par type de contenu
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# Filtrage par type de contenu{#filtering-by-content-type}

La fonctionnalité de filtrage de type de contenu de Sensor a pour objectif d’éliminer la nécessité de stocker et de traiter des informations qui ne sont pas utiles à des fins d’analyse.

La plupart des données de requête disponibles par le biais de l’API d’un serveur Web ne sont pas utiles dans l’analyse de l’entreprise. L&#39;Enregistrement et le traitement sont coûteux et le filtrage de type contenu [!DNL Sensor’s] permet d&#39;éviter tout enregistrement et traitement inutiles.

Pour optimiser les performances de traitement des données du journal Web et réduire la quantité de données de mesure à stocker, [!DNL Site] acquiert des données de mesure (données de demande, entrées de journal, données de journal, etc.) pour toutes les requêtes de type de contenu Web, à l&#39;exception des types de contenu spécifiquement répertoriés (tels que les feuilles de style en cascade, les demandes d&#39;image, etc.), qui sont filtrés avant leur transmission au serveur de données par [!DNL Sensor]. Ce filtrage peut être désactivé pour un serveur Web entier et peut également être remplacé pour un objet de contenu particulier en ajoutant la paire nom-valeur &quot;Log=1&quot; à la chaîne de requête d’un objet incorporé particulier (par exemple, [!DNL http://www.mysite.com/advertisement.gif?Log=1]).
