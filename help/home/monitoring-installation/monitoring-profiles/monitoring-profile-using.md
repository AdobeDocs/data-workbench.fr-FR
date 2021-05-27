---
description: Le profil Statut du profil de Data Workbench fournit des informations à jour sur l’intégrité du serveur Data Workbench en fonction du profil plutôt que des mesures du serveur ou des données historiques.
title: Espace de travail Statut du profil de Data Workbench
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
exl-id: 40b9b0bf-4fd9-48d8-875b-514921c520cd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 4%

---

# Espace de travail Statut du profil de Data Workbench{#data-workbench-profile-status-workspace}

Le profil Statut du profil de Data Workbench fournit des informations à jour sur l’intégrité du serveur Data Workbench en fonction du profil plutôt que des mesures du serveur ou des données historiques.

## Statut du profil du Data Workbench {#section-65d1fa393cfd450cbacef3cba823fcc1}

Ce profil d’état fournit les informations du serveur Data Workbench qui sont à jour, mais pas tout à fait en temps réel, car l’agent est interrogé toutes les dix minutes et la création de rapports inclut toujours cette latence de dix minutes. Plus précisément, les jeux de données générés par ce profil fournissent la dernière observation du serveur à partir de l’agent, qui dispose le plus souvent d’une période d’interrogation par défaut de dix minutes.

Pour plus d’informations de référence sur les dimensions utilisées dans le profil d’état du profil Data Workbench, voir [Profil d’état du profil Insight](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64).

![](assets/Status_General_Status.png)

Ce rapport est plus destiné à la surveillance des opérations qu’aux composants ou à des fluctuations de trafic spécifiques.

![](assets/Status_General_page.png)

Cela nous donne une idée de qui est dans quel mode : Si un taux d’entrée rapide élevé s’affiche pour un certain profil, ce profil est en mode d’entrée rapide.

Si la mesure Bloqué est 1, le serveur est Bloqué. Si la valeur est 0, le serveur n’est pas bloqué.

**Lecture des journaux pour les chargements par lots volumineux**

![](assets/Status_General_stalled_log.png)
