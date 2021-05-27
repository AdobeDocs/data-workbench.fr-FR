---
description: Capteur vous permet d’acquérir des données de demande web (données d’événement ou de journal) ainsi que des données de mesure étendue.
title: Quel type de données puis-je acquérir ?
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
exl-id: 97d87084-cac3-4a94-89e0-f01a66e20324
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 2%

---

# Quel type de données puis-je acquérir ?{#what-kind-of-data-can-i-acquire}

Capteur vous permet d’acquérir des données de demande web (données d’événement ou de journal) ainsi que des données de mesure étendue.

Les données de mesure étendues ne sont pas disponibles pour les serveurs web dans le cadre de leur fonctionnement normal.

Les rubriques suivantes sont décrites :

## Données de requête web {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] permet l’acquisition et le transport automatique des données de requête web (données d’événement ou de journal) vers un emplacement central pour le stockage et le traitement en vue de l’analyse. [!DNL Sensor] capture les données concernant toutes les demandes GET effectuées à partir des serveurs web sur lesquels il est installé, sauf si vous choisissez spécifiquement de filtrer certains types de demandes et de ne pas collecter de données concernant ces types de demandes.

[!DNL Sensor] automatise ce processus d’acquisition de données pour toutes les demandes de GET effectuées sur vos serveurs et présente d’importants avantages commerciaux et techniques par rapport à d’autres méthodes d’acquisition de données de demande de site web. Ces avantages sont les suivants :

* Les requêtes qui ne sont pas nécessaires à l’analyse et à la création de rapports peuvent être filtrées avant d’engager des coûts pour leur acquisition, leur transport, leur stockage et leur traitement.
* Les administrateurs de site n’ont pas à faire pivoter les fichiers journaux par lot, soit manuellement, soit par script.
* [!DNL Sensor] agrège les fichiers journaux à un emplacement central afin de permettre un accès facile au traitement.
* [!DNL Sensor] organise et stocke les fichiers journaux dans un format commun de conservation des données, en supprimant la nécessité de les prétraiter avant qu’ils puissent être utilisés à des fins d’analyse et de création de rapports.
* Les instances de certains types de contenu peuvent être incluses dans les fichiers journaux, même si la plupart des demandes pour un certain type de contenu sont automatiquement filtrées.
* [!DNL Sensor] compresse les entrées du fichier journal, ce qui nécessite beaucoup moins d’espace de stockage, ce qui réduit les coûts et permet de conserver les données à disposition pour analyse pendant de plus longues périodes.
* [!DNL Sensor’s] les fonctionnalités de tolérance aux pannes permettent des erreurs système et réseau tout en assurant la diffusion des données de journal vers un référentiel central.
* [!DNL Sensor] permet la mise en oeuvre d’expériences contrôlées avec du contenu web, des processus et des campagnes marketing.
* [!DNL Sensor] les horodatages consignent les entrées dans des unités de 100 ns, ce qui permet de nouveaux types de fonctionnalités d’analyse.
* [!DNL Sensor] permet aux propriétaires de site d’ajouter des données (mesures) aux entrées de journal après la mise en oeuvre initiale pour prise en compte dans l’analyse et la création de rapports.

Pour plus d’informations sur l’acquisition de données de mesure étendue, voir [Acquisition des mesures de ligne de base](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe).

## Données de mesure étendues {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] prend également en charge l’utilisation de balises de page (ou de requêtes d’objet incorporées) pour acquérir des données de mesure qui ne sont pas disponibles pour vos serveurs web dans le cadre de leur fonctionnement normal. Les balises de page sont généralement utilisées pour mesurer les éléments suivants :

* Affichage d’une page logique dans un site web dynamique.
* Affichage de contenu ou de publicités sur un site web contrôlé par un tiers.
* Affichage du contenu diffusé à partir d’un cache de navigateur ou d’un réseau de diffusion de contenu.
* Informations détaillées sur le navigateur d’un visiteur, notamment des mesures telles que le temps de chargement d’une page, la résolution d’écran, les champs de formulaire remplis par le visiteur, etc.
* Autres données qui ne sont pas autrement envoyées par les navigateurs à vos serveurs web.

[!DNL Sensor] collecte toutes les informations placées dans une demande de GET envoyée à un serveur web en cours d’exécution  [!DNL Sensor]. Ces requêtes peuvent provenir de requêtes d’objet incorporées de toute sorte, soit pour simplement mesurer que la requête a été faite à un certain moment par un certain navigateur, soit pour transmettre d’autres données de mesure dans le flux de collecte de données afin qu’elles puissent être traitées à des fins d’analyse et de création de rapports.

[!DNL Sensor] fournit le meilleur des mondes d’acquisition de données côté client et côté serveur : elle acquiert vos données de journaux web côté serveur et collecte des mesures de contournement de cache ou de site tiers côté client prises par les requêtes d’objet intégrées. En d’autres termes, [!DNL Sensor] acquiert à la fois les données de requête normalement connues de vos serveurs web (mesures côté serveur) et toutes les données de mesure supplémentaires que vous collectez grâce à l’utilisation de balises de page (mesures côté client) qui envoient leurs données à tout serveur web exécutant [!DNL Sensor]. Ces serveurs web peuvent être dédiés à la collecte de mesures côté client, mais ne le sont pas nécessairement.

Pour plus d’informations sur l’acquisition de données de mesure étendue, voir [Acquisition des mesures étendues](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944).
