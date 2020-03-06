---
description: Le profil d’état du profil de l’outil de données fournit des informations à jour sur l’état du serveur de l’outil de données en fonction du profil plutôt que des mesures du serveur ou des données historiques.
solution: Analytics
title: Espace de travail Statut du profil des outils de données
topic: Data workbench
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Espace de travail Statut du profil des outils de données{#data-workbench-profile-status-workspace}

Le profil d’état du profil de l’outil de données fournit des informations à jour sur l’état du serveur de l’outil de données en fonction du profil plutôt que des mesures du serveur ou des données historiques.

## Statut du profil des outils de données {#section-65d1fa393cfd450cbacef3cba823fcc1}

Ce profil d’état fournit les informations actuelles sur le serveur de l’outil de données, mais pas tout à fait en temps réel, car l’agent est interrogé toutes les dix minutes et la création de rapports inclut toujours cette latence de dix minutes. Plus précisément, les jeux de données générés par ce profil fournissent la dernière observation du serveur à partir de l’agent, qui dispose le plus souvent d’une période d’interrogation par défaut de dix minutes.

Pour plus d’informations de référence sur les dimensions utilisées dans le profil d’état du profil de l’outil de données, voir Profil [d’état du profil](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64)Insight.

![](assets/Status_General_Status.png)

Ce rapport est plus destiné à la surveillance des opérations que des composants ou des fluctuations de trafic spécifiques.

![](assets/Status_General_page.png)

Cela nous donne une idée de qui est dans quel mode : Si le taux d’entrée rapide est élevé pour un certain profil, ce profil est en mode d’entrée rapide.

Si la mesure bloquée est 1, le serveur est bloqué. Si la valeur est 0, le serveur n’est pas bloqué.

**Lecture du journal pour les chargements par lots volumineux**

![](assets/Status_General_stalled_log.png)

