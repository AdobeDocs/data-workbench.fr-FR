---
description: Sensor vous permet d’acquérir des données de requête Web (données d’événement ou de journal) ainsi que des données de mesure étendues.
solution: Analytics
title: Quel genre de données puis-je acquérir ?
topic: Data workbench
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Quel genre de données puis-je acquérir ?{#what-kind-of-data-can-i-acquire}

Sensor vous permet d’acquérir des données de requête Web (données d’événement ou de journal) ainsi que des données de mesure étendues.

Les données de mesure étendues ne sont pas disponibles pour vos serveurs Web dans le cadre de leur fonctionnement normal.

Les rubriques suivantes sont décrites :

## Données de requête Web {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] permet l’acquisition et le transport automatique des données de requête Web (données d’événement ou de journal) vers un emplacement central pour le stockage et le traitement en vue de l’analyse. A moins que vous ne choisissiez spécifiquement de filtrer certains types de requêtes et de ne pas collecter de données sur ces types de requêtes, [!DNL Sensor] capture les données concernant toutes les requêtes GET effectuées sur les serveurs Web sur lesquels elles sont installées.

[!DNL Sensor] automatise ce processus d’acquisition de données pour toutes les requêtes GET effectuées sur vos serveurs et présente des avantages commerciaux et techniques importants par rapport aux autres méthodes d’acquisition de données de demande de site Web. Ces avantages sont les suivants :

* Les requêtes qui ne sont pas nécessaires à l’analyse et à la création de rapports peuvent être filtrées avant d’engager des coûts pour leur acquisition, leur transport, leur stockage et leur traitement.
* Les administrateurs de site n’ont pas à faire pivoter les fichiers journaux par lot, manuellement ou par script.
* [!DNL Sensor] agrège les fichiers journaux à un emplacement central afin de faciliter l’accès au traitement.
* [!DNL Sensor] organise et stocke les fichiers journaux dans un format commun de conservation des données, éliminant ainsi la nécessité de les prétraiter avant de pouvoir les utiliser à des fins d’analyse et de création de rapports.
* Les instances de certains types de contenu peuvent être incluses dans les fichiers journaux, même si la plupart des requêtes d’un certain type de contenu sont automatiquement filtrées.
* [!DNL Sensor] compresse les entrées des fichiers journaux, ce qui nécessite beaucoup moins d&#39;espace de stockage, ce qui réduit les coûts et permet de garder les données disponibles pour l&#39;analyse pendant de plus longues périodes.
* [!DNL Sensor’s] les fonctionnalités de tolérance aux pannes permettent les défaillances du système et du réseau tout en assurant la remise des données du journal à un référentiel central.
* [!DNL Sensor] permet la mise en oeuvre d&#39;expériences contrôlées avec du contenu Web, des processus et des campagnes marketing.
* [!DNL Sensor] les horodatages consignent les entrées dans des unités de 100 ns, ce qui permet de créer de nouveaux types de fonctionnalités analytiques.
* [!DNL Sensor] permet aux propriétaires du site d&#39;ajouter des données (mesures) aux entrées du journal après la mise en oeuvre initiale pour prise en compte dans l&#39;analyse et la création de rapports.

Pour plus d&#39;informations sur l&#39;acquisition de données de mesure étendues, voir [Acquisition de mesures](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe)de base.

## Données de mesure étendues {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] prend également en charge l’utilisation de balises de page (ou de requêtes d’objet incorporées) pour acquérir des données de mesure qui ne sont pas disponibles pour vos serveurs Web dans le cadre de leur fonctionnement normal. Les balises de page sont généralement utilisées pour mesurer :

* Affichage d’une page logique dans un site Web dynamique.
* Affichage de contenu ou de publicités sur un site Web contrôlé par un tiers.
* Affichage du contenu diffusé à partir d’un cache de navigateur ou d’un CDN.
* Informations détaillées sur le navigateur d’un visiteur, notamment les mesures telles que le temps de chargement de la page, la résolution d’écran, les champs de formulaire que le visiteur a remplis, etc.
* Autres données qui ne sont pas autrement envoyées par les navigateurs à vos serveurs Web.

[!DNL Sensor] collecte toutes les informations placées dans une requête GET envoyée à un serveur Web en cours d’exécution [!DNL Sensor]. Ces requêtes peuvent provenir de requêtes d’objets incorporés de toute sorte, soit pour simplement mesurer que la requête a été faite à un certain moment par un navigateur donné, soit pour transmettre d’autres données de mesure dans le flux de collecte de données afin qu’elle puisse être traitée à des fins d’analyse et de création de rapports.

[!DNL Sensor] offre le meilleur des mondes d’acquisition de données côté client et côté serveur ; elle acquiert vos données de journal Web côté serveur et collecte les mesures de site tiers côté client ou de mémoire cache prises par les requêtes d’objet incorporées. En d’autres termes, [!DNL Sensor] acquiert les données de requête normalement connues de vos serveurs Web (mesures côté serveur) et les données de mesure supplémentaires que vous collectez par le biais de balises de page (mesures côté client) qui envoient leurs données à tout serveur Web en cours d’exécution [!DNL Sensor]. Ces serveurs Web peuvent être consacrés à la collecte de mesures côté client, mais ne sont pas nécessaires.

Pour plus d&#39;informations sur l&#39;acquisition de données de mesure étendues, voir [Acquisition de mesures](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944)étendues.
