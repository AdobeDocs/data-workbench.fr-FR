---
description: La fonctionnalité de filtrage de type de contenu de Sensor a pour objectif d’éliminer la nécessité de stocker et de traiter des informations qui ne sont pas utiles à des fins d’analyse.
solution: Analytics
title: Filtrage par type de contenu
topic: Data workbench
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Filtrage par type de contenu{#filtering-by-content-type}

La fonctionnalité de filtrage de type de contenu de Sensor a pour objectif d’éliminer la nécessité de stocker et de traiter des informations qui ne sont pas utiles à des fins d’analyse.

La plupart des données de requête disponibles par le biais de l’API d’un serveur Web ne sont pas utiles dans l’analyse de l’entreprise. Le stockage et le traitement sont onéreux et le filtrage de type de contenu vous permet d’éviter tout stockage et traitement inutiles. [!DNL Sensor’s]

Pour optimiser les performances de traitement des données du journal Web et réduire la quantité de données de mesure à stocker, [!DNL Site] acquiert des données de mesure (données de requête, entrées de journal, données de journal, etc.) pour toutes les requêtes de type de contenu Web, à l’exception des types de contenu spécifiquement répertoriés (feuilles de style en cascade, demandes d’image, etc.), qui sont filtrés avant d’être transmis au serveur de données par [!DNL Sensor]. Ce filtrage peut être désactivé pour l’ensemble d’un serveur Web et il peut également être remplacé pour un objet de contenu particulier en ajoutant la paire nom-valeur &quot;Log=1&quot; à la chaîne de requête d’un objet incorporé particulier (par exemple, [!DNL http://www.mysite.com/advertisement.gif?Log=1]).
