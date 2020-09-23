---
description: Informations sur la configuration générale du capteur avec une instance de serveur Web s’exécutant sur un serveur Web.
solution: Analytics
title: Utilisation de plusieurs instances d’un serveur web
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---


# Utilisation de plusieurs instances d’un serveur web{#working-with-multiple-instances-of-a-web-server}

Informations sur la configuration générale du capteur avec une instance de serveur Web s’exécutant sur un serveur Web.

![](assets/web_inst.png)

Dans ce scénario, une seule instance de serveur Web écrit des données dans le fichier de file d’attente mappé à la mémoire, qui est lu par l’émetteur et envoyé au [!DNL data workbench server]serveur.

Une fois [!DNL Sensor] installé sur un serveur Web exécutant plusieurs instances de collecteur, vous pouvez le configurer de l’une des deux manières suivantes :

* Vous pouvez faire partager un seul fichier de file d&#39;attente par tous les modules du collecteur.

   Lors de l’utilisation d’un fichier de file d’attente unique, la gestion, la configuration et l’administration sont quelque peu simplifiées, car l’architecture elle-même est moins complexe. Cependant, avec un seul fichier de file d’attente, l’ensemble du serveur Web, quel que soit le nombre d’instances, est identifié comme étant WEB1.

* Vous pouvez répliquer l’architecture ci-dessus plusieurs fois et demander à chaque instance de serveur Web de disposer d’un fichier de file d’attente distinct.

   Cela vous permet d’identifier de manière unique chacune des instances de serveur Web. En d’autres termes, l’identification du serveur Web (et l’identifiant SensorID correspondant dans la [!DNL Sensor] configuration) est fonction de cette configuration.

Dans tous les cas, les données contiennent toujours toutes les informations de nom d’hôte afin que vous puissiez faire la distinction entre [!DNL www.client.com], [!DNL www2.client.com]et ainsi de suite. La configuration correcte est déterminée par les objectifs d’analyse et si les analystes doivent segmenter les données en fonction d’une instance spécifique s’exécutant sur un serveur Web.

>[!NOTE]
>
>Ce type de segmentation n&#39;est généralement utilisé que dans l&#39;analyse opérationnelle et n&#39;offre pas beaucoup d&#39;utilisation pratique en dehors de cette zone.

