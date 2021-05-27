---
description: Vous devez installer et exécuter Capteur sur chaque serveur web qui diffuse le contenu de votre site afin de collecter toutes les requêtes qui sont vues par ces serveurs.
title: Comment puis-je acquérir ces données_
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
exl-id: 1c886f60-eae9-48c2-b641-396c622035d4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# Comment puis-je acquérir ces données_{#how-do-i-acquire-this-data}

Vous devez installer et exécuter Capteur sur chaque serveur web qui diffuse le contenu de votre site afin de collecter toutes les requêtes qui sont vues par ces serveurs.

Ces requêtes représentent au moins 90 % des requêtes envoyées à votre site et 90 % ou plus des données nécessaires à l’analyse complète du trafic de votre site. [!DNL Page Tags] doit ensuite être utilisé pour collecter les 10 % ou moins des données de trafic restantes qui ne sont pas connues de vos serveurs web. Toutefois, voici des configurations valides pour la collecte de données de demande Web sur votre site, par ordre de préférence, en fonction de notre expérience opérationnelle :

1. [!DNL Sensor] est installé sur chaque serveur web que vous contrôlez et qui prend en charge votre site. Le contenu de sites tiers, le contenu diffusé à partir du cache et certains types de contenu dynamique doivent être balisés. De plus, ces balises de page doivent envoyer les données qu’elles collectent à un serveur web à l’emplacement où est exécuté [!DNL Sensor]. Vous pouvez ajouter un serveur web supplémentaire si le niveau de trafic de demande de balise de page le justifie, ou dans certains cas, dédier un serveur web à la collecte de ces demandes de balise de page.
1. [!DNL Sensor] est installé sur deux serveurs web, également appelés serveurs de collecte de données dans ce guide, à votre emplacement dédié à la collecte de données de demande de balise de page à partir de pages balisées. Tout le contenu de votre site est balisé et toutes les balises de page sont dirigées vers les deux serveurs de collecte de données.
1. [!DNL Sensor’s] les services de collecte de données sont fournis par un externaliste qui exécute les serveurs de collecte de données pour collecter toutes vos données de demande web. Dans ce cas, tout le contenu de votre site est balisé et les balises de page envoient leurs données aux serveurs de collecte de données externalisés.

   Pour plus d’informations sur [!DNL Sensor], consultez le *Guide du Data Workbench [!DNL Sensor]*.
