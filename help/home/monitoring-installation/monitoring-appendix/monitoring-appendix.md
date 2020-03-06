---
description: Ce document décrit les profils avec leurs champs, dimensions et mesures utilisés par le profil de surveillance des outils de données.
solution: Analytics
title: Dimensions et mesures des profils des outils de données
topic: Data workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensions et mesures des profils des outils de données{#data-workbench-profile-dimensions-and-metrics}

Ce document décrit les profils avec leurs champs, dimensions et mesures utilisés par le profil de surveillance des outils de données.

Pour surveiller les serveurs de l’outil de données, les données sont collectées à l’aide d’un script qui analyse l’état détaillé tout en capturant des informations spécifiques sur le serveur. Les informations du serveur de l’outil de données sont ensuite transmises à un appel de balise de page pour que le capteur de l’outil de données collecte et enregistre dans un fichier VSL.

## Profils utilisés par le profil de surveillance des outils de données {#section-b5b1234f55c3407dae8e68b031b7cd7f}

Ces profils fournissent des dimensions et des mesures qui vous permettent d’afficher l’état du serveur et les données de performances :

* [Dimensions dans le profil d’état du profil Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimensions dans le profil d’état du serveur Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimensions dans le profil historique d&#39;Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Mesures du profil de surveillance historique d’Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

Les profils d’état vous permettent de voir les performances actuelles des outils de données du point de vue opérationnel. Le profil Statut **du** profil et le profil État **du** serveur collectent des données à partir des serveurs Statut détaillé et Outils de données. Toutes les données rassemblées sont placées dans le `cs-uri-query` champ en vue de leur utilisation.

Les profils **** historiques vous permettent d’évaluer l’impact des modifications de configuration et de matériel à l’aide de données historiques. Le profil historique est peut-être le plus utile car il vous permet d&#39;évaluer l&#39;impact des changements de configuration et de matériel au fil du temps.
