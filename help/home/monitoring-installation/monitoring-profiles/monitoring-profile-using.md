---
description: Le profil d’état du Profil des outils de données fournit des informations à jour sur l’état du serveur des outils de données en fonction du profil plutôt que des mesures du serveur ou des données historiques.
title: Espace de travail Statut du profil de Data Workbench
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
exl-id: 40b9b0bf-4fd9-48d8-875b-514921c520cd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 4%

---

# Espace de travail Statut du profil de Data Workbench{#data-workbench-profile-status-workspace}

Le profil d’état du Profil des outils de données fournit des informations à jour sur l’état du serveur des outils de données en fonction du profil plutôt que des mesures du serveur ou des données historiques.

## Etat du Profil Data Workbench {#section-65d1fa393cfd450cbacef3cba823fcc1}

Ce profil d’état fournit les informations du serveur de l’outil de données qui sont à jour, mais pas tout à fait en temps réel, car l’agent est interrogé toutes les dix minutes et le rapports inclut toujours cette latence de dix minutes. Plus précisément, les jeux de données générés par ce profil fournissent la dernière observation du serveur à partir de l&#39;agent, qui a le plus souvent une période d&#39;interrogation par défaut de dix minutes.

Pour obtenir des informations de référence supplémentaires sur les dimensions utilisées dans le profil d’état du Profil de l’outil de données, voir [profil d’état du Profil Insight](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64).

![](assets/Status_General_Status.png)

Ce rapport est davantage destiné à la surveillance des opérations que des composants ou des fluctuations de trafic spécifiques.

![](assets/Status_General_page.png)

Cela nous donne une idée de qui est dans quel mode : Si le taux d&#39;entrée rapide est élevé pour un certain profil, ce profil est en mode d&#39;entrée rapide.

Si la mesure bloquée est 1, le serveur est bloqué. Si la valeur est 0, le serveur n’est pas bloqué.

**Lecture du journal pour les chargements par lots volumineux**

![](assets/Status_General_stalled_log.png)
