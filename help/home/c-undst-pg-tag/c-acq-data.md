---
description: Le capteur vous permet d’acquérir des données de requête Web (données de événement ou de journalisation) ainsi que des données de mesure étendues.
title: Quel type de données puis-je acquérir ?
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
exl-id: 97d87084-cac3-4a94-89e0-f01a66e20324
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 2%

---

# Quel type de données puis-je acquérir ?{#what-kind-of-data-can-i-acquire}

Le capteur vous permet d’acquérir des données de requête Web (données de événement ou de journalisation) ainsi que des données de mesure étendues.

Les données de mesure étendues ne sont pas disponibles pour vos serveurs Web dans le cadre de leur fonctionnement normal.

Les rubriques suivantes sont décrites :

## Données de requête Web {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] permet l&#39;acquisition et le transport automatique des données de demande web (données de événement ou de journal) vers un emplacement central pour l&#39;enregistrement et le traitement de l&#39;analyse. À moins que vous ne choisissiez spécifiquement de filtrer certains types de requêtes et de ne pas collecter de données sur ces types de requêtes, [!DNL Sensor] capture les données concernant toutes les requêtes de GET effectuées sur les serveurs Web sur lesquels il est installé.

[!DNL Sensor] automatise ce processus d&#39;acquisition de données pour toutes les demandes de GET effectuées sur vos serveurs et présente des avantages commerciaux et techniques importants par rapport aux autres méthodes d&#39;acquisition de données de demande de site Web. Ces avantages sont les suivants :

* Les demandes qui ne sont pas nécessaires pour l&#39;analyse et le rapports peuvent être filtrées avant que vous n&#39;engagiez des coûts d&#39;acquisition, de transport, d&#39;enregistrement et de traitement.
* Les administrateurs de site n’ont pas à faire pivoter les fichiers journaux par lot, manuellement ou par script.
* [!DNL Sensor] agrégat les fichiers journaux à un emplacement central pour permettre un accès facile au traitement.
* [!DNL Sensor] organise et stocke les fichiers journaux dans un format commun de conservation des données, en supprimant la nécessité de les prétraiter avant de pouvoir les utiliser à des fins d’analyse et de rapports.
* Les instances de certains types de contenu peuvent être incluses dans les fichiers journaux, même si la plupart des requêtes d’un certain type de contenu sont automatiquement filtrées.
* [!DNL Sensor] compresse les entrées des fichiers journaux, ce qui nécessite beaucoup moins d&#39;espace d&#39;enregistrement, ce qui réduit les coûts et permet de garder les données disponibles pour l&#39;analyse pendant de plus longues périodes.
* [!DNL Sensor’s] les fonctionnalités de tolérance aux pannes permettent les pannes du système et du réseau tout en assurant la diffusion des données du journal dans un référentiel central.
* [!DNL Sensor] permet la mise en oeuvre d&#39;expériences contrôlées avec du contenu web, des processus et des campagnes marketing.
* [!DNL Sensor] les horodatages consignent les entrées dans des unités de 100 ns, ce qui permet de nouveaux types de fonctionnalités analytiques.
* [!DNL Sensor] permet aux propriétaires du site d&#39;ajouter des données (mesures) aux entrées du journal après la mise en oeuvre initiale pour examen dans l&#39;analyse et le rapports.

Pour plus d&#39;informations sur l&#39;acquisition de données de mesure étendues, voir [Acquisition de mesures de référence](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe).

## Données de mesure étendue {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] prend également en charge l’utilisation de balises de page (ou de requêtes d’objet incorporées) pour acquérir des données de mesure qui ne sont pas disponibles pour vos serveurs Web dans le cadre de leur fonctionnement normal. Les balises de page sont généralement utilisées pour mesurer :

* Affichage d’une page logique dans un site Web dynamique.
* Affichage du contenu ou des publicités sur un site Web contrôlé par un tiers.
* Affichage du contenu diffusé à partir d’un cache de navigateur ou d’un CDN.
* Informations détaillées sur le navigateur d’un visiteur, notamment les mesures telles que le temps de chargement de page, la résolution d’écran, les champs de formulaire que le visiteur a remplis, etc.
* Autres données qui ne sont pas autrement envoyées par les navigateurs à vos serveurs Web.

[!DNL Sensor] collecte toutes les informations placées dans une demande de GET envoyée à un serveur Web en cours d’exécution  [!DNL Sensor]. Ces demandes peuvent provenir de demandes d&#39;objets incorporées de toute sorte, soit pour simplement mesurer que la demande a été faite à un certain moment par un certain navigateur, soit pour transmettre d&#39;autres données de mesure dans le flux de collecte de données afin qu&#39;elles puissent être traitées à des fins d&#39;analyse et de rapports.

[!DNL Sensor] fournit le meilleur des mondes d’acquisition de données côté client et côté serveur : elle acquiert vos données de journal Web côté serveur et collecte les mesures de site tiers côté client ou de contournement de la mémoire cache prises par les requêtes d’objet incorporées. En d’autres termes, [!DNL Sensor] acquiert à la fois les données de requête normalement connues de vos serveurs Web (mesures côté serveur) et les données de mesure supplémentaires que vous collectez à l’aide de balises de page (mesures côté client) qui envoient leurs données à tout serveur Web exécutant [!DNL Sensor]. Ces serveurs Web peuvent être dédiés à la collecte des mesures côté client, mais ne sont pas nécessaires.

Pour plus d&#39;informations sur l&#39;acquisition de données de mesure étendue, voir [Acquisition de mesures étendues](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944).
