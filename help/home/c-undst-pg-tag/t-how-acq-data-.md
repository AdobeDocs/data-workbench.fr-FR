---
description: Vous devez installer et exécuter Sensor sur chaque serveur Web qui diffuse le contenu de votre site pour collecter toutes les requêtes qui sont vues par ces serveurs.
solution: Analytics
title: Comment puis-je acquérir ces données_
topic: Data workbench
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Comment puis-je acquérir ces données_{#how-do-i-acquire-this-data}

Vous devez installer et exécuter Sensor sur chaque serveur Web qui diffuse le contenu de votre site pour collecter toutes les requêtes qui sont vues par ces serveurs.

Ces requêtes représentent 90 % ou plus des requêtes envoyées à votre site et 90 % ou plus des données nécessaires à l’analyse complète du trafic de votre site. [!DNL Page Tags] doit ensuite être utilisée pour collecter les 10 % restants ou moins des données de trafic qui ne sont pas connues de vos serveurs Web. Les configurations suivantes, toutefois, sont valides pour la collecte de données de requête Web à partir de votre site, par ordre de préférence, en fonction de notre expérience opérationnelle :

1. [!DNL Sensor] est installé sur chaque serveur Web dont vous avez le contrôle et qui prend en charge votre site. Le contenu des sites tiers, le contenu diffusé à partir du cache et certains types de contenu dynamique doivent être balisés et ces balises de page doivent envoyer les données qu’elles collectent à un serveur Web situé à l’emplacement où vous êtes en cours d’exécution [!DNL Sensor]. Vous pouvez ajouter un serveur Web supplémentaire si le niveau du trafic de la demande de balise de page le justifie ou, dans certains cas, dédier un serveur Web à la collecte de ces requêtes de balise de page.
1. [!DNL Sensor] est installé sur deux serveurs Web, également appelés serveurs de collecte de données dans ce guide, à votre emplacement, qui sont dédiés à la collecte de données de demande de balise de page à partir de pages balisées. Tout le contenu de votre site est balisé et toutes les balises de page sont dirigées vers les deux serveurs de collecte de données.
1. [!DNL Sensor’s] les services de collecte de données sont fournis par un fournisseur externe qui exécute des serveurs de collecte de données pour collecter toutes vos données de requête Web. Dans ce cas, tout le contenu de votre site est balisé et les balises de page envoient leurs données aux serveurs de collecte de données externalisés.

   Pour plus d’informations sur [!DNL Sensor]les outils de *données, consultez le[!DNL Sensor]Guide des outils de données*.

