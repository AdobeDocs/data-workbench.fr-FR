---
description: Informations sur la configuration générale du capteur avec une instance de serveur web s’exécutant sur un serveur web.
title: Utilisation de plusieurs instances d’un serveur web
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
exl-id: a371f9ed-6c27-4b3d-843f-ae5621013410
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# Utilisation de plusieurs instances d’un serveur web{#working-with-multiple-instances-of-a-web-server}

Informations sur la configuration générale du capteur avec une instance de serveur web s’exécutant sur un serveur web.

![](assets/web_inst.png)

Dans ce scénario, une seule instance de serveur web écrit des données dans le fichier de file d’attente mappé en mémoire, qui est lu par l’émetteur et envoyé à [!DNL data workbench server].

Lorsque [!DNL Sensor] est installé sur un serveur web qui exécute plusieurs instances de collecteur, vous pouvez le configurer de deux manières :

* Vous pouvez faire en sorte que tous les modules du collecteur partagent un fichier de file d’attente.

   Lors de l’utilisation d’un seul fichier de file d’attente, la gestion, la configuration et l’administration sont quelque peu simplifiées, car l’architecture elle-même est moins complexe. Cependant, avec un seul fichier de file d’attente, l’ensemble du serveur web, quel que soit le nombre d’instances, est identifié comme étant WEB1.

* Vous pouvez répliquer l’architecture ci-dessus plusieurs fois et demander à chaque instance de serveur web d’avoir un fichier de file d’attente distinct.

   Vous pouvez ainsi identifier de manière unique chacune des instances de serveur web. En d’autres termes, l’identification du serveur web (et l’identifiant Capteur correspondant dans la configuration [!DNL Sensor]) est une fonction de cette configuration.

Dans tous les cas, les données contiennent toujours toutes les informations de nom d’hôte afin que vous puissiez faire la distinction entre [!DNL www.client.com], [!DNL www2.client.com], etc. La configuration correcte est déterminée par les objectifs de l’analyse et si les analystes doivent segmenter les données en fonction d’une instance spécifique s’exécutant sur un serveur web.

>[!NOTE]
>
>Ce type de segmentation n&#39;est généralement utilisé que dans les analyses opérationnelles et n&#39;est pas très utile en dehors de ce domaine.
