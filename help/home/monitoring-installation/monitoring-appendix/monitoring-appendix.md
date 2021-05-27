---
description: Ce document décrit les profils avec leurs champs, dimensions et mesures utilisés par le profil de surveillance Data Workbench.
title: Dimensions et mesures du profil Data Workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Dimensions et mesures du profil Data Workbench{#data-workbench-profile-dimensions-and-metrics}

Ce document décrit les profils avec leurs champs, dimensions et mesures utilisés par le profil de surveillance Data Workbench.

Pour surveiller les serveurs Data Workbench, les données sont collectées à l’aide d’un script qui analyse le statut détaillé tout en capturant des informations de serveur spécifiques. Les informations du serveur Data Workbench sont ensuite transmises à un appel de balise de page pour que Data Workbench Sensor les récupère et les enregistre dans un fichier VSL.

## Profils utilisés par le profil de surveillance du Data Workbench {#section-b5b1234f55c3407dae8e68b031b7cd7f}

Ces profils fournissent des dimensions et des mesures qui vous permettent d’afficher l’état du serveur et les données de performances :

* [Dimensions du profil d’état du profil Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimensions dans le profil d’état du serveur Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimensions du profil historique d’Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Mesures dans le profil de surveillance historique d’Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

Les profils d’état vous permettent de voir les performances actuelles de Data Workbench du point de vue opérationnel. Le profil **État du profil** et le profil **État du serveur** collectent des données à partir du statut détaillé et des serveurs Data Workbench. Toutes les données collectées sont placées dans le champ `cs-uri-query` à utiliser.

Les **profils historiques** vous permettent d’évaluer l’impact des changements de configuration et de matériel à l’aide de données historiques. Le profil historique peut être le plus utile, car il vous permet d’évaluer l’impact des changements de configuration et de matériel au fil du temps.
