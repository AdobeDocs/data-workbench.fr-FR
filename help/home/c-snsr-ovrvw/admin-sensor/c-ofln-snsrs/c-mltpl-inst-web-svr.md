---
description: Informations sur la configuration générale du capteur avec une instance de serveur Web s’exécutant sur un serveur Web.
title: Utilisation de plusieurs instances d’un serveur web
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
exl-id: a371f9ed-6c27-4b3d-843f-ae5621013410
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# Utilisation de plusieurs instances d’un serveur web{#working-with-multiple-instances-of-a-web-server}

Informations sur la configuration générale du capteur avec une instance de serveur Web s’exécutant sur un serveur Web.

![](assets/web_inst.png)

Dans ce scénario, une seule instance de serveur Web écrit des données dans le fichier de file d’attente mappé à la mémoire, qui est lu par l’émetteur et envoyé à [!DNL data workbench server].

Lorsque [!DNL Sensor] est installé sur un serveur Web qui exécute plusieurs instances de collecteur, vous pouvez le configurer de deux manières :

* Vous pouvez faire partager un seul fichier de file d&#39;attente par tous les modules du collecteur.

   Lors de l’utilisation d’un fichier de file d’attente unique, la gestion, la configuration et l’administration sont quelque peu simplifiées, car l’architecture elle-même est moins complexe. Cependant, avec un seul fichier de file d’attente, l’ensemble du serveur Web, quel que soit le nombre d’instances, est identifié comme étant WEB1.

* Vous pouvez répliquer l’architecture ci-dessus plusieurs fois et demander à chaque instance de serveur Web de disposer d’un fichier de file d’attente distinct.

   Cela vous permet d’identifier de manière unique chacune des instances de serveur Web. En d&#39;autres termes, l&#39;identification du serveur Web (et le SensorID correspondant dans la configuration [!DNL Sensor]) est fonction de cette configuration.

Dans tous les cas, les données contiennent toujours toutes les informations de nom d’hôte afin que vous puissiez faire la distinction entre [!DNL www.client.com], [!DNL www2.client.com], etc. La configuration correcte est déterminée par les objectifs d’analyse et si les analystes doivent segmenter les données en fonction d’une instance spécifique s’exécutant sur un serveur Web.

>[!NOTE]
>
>Ce type de segmentation n&#39;est généralement utilisé que dans l&#39;analyse opérationnelle et n&#39;offre pas beaucoup d&#39;utilisation pratique en dehors de cette zone.
