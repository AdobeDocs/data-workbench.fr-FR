---
description: Informations sur la configuration générale du capteur avec une instance de serveur Web s’exécutant sur un serveur Web.
solution: Insight
title: Utilisation de plusieurs instances d’un serveur Web
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Utilisation de plusieurs instances d’un serveur Web{#working-with-multiple-instances-of-a-web-server}

Informations sur la configuration générale du capteur avec une instance de serveur Web s’exécutant sur un serveur Web.

![](assets/web_inst.png)

Dans ce scénario, une seule instance de serveur Web écrit des données dans le fichier de file d’attente mappé à la mémoire, qui est lu par l’émetteur et envoyé au [!DNL data workbench server]serveur.

Lorsque [!DNL Sensor] est installé sur un serveur Web qui exécute plusieurs instances de collecteur, vous pouvez le configurer de deux manières :

* Vous pouvez faire partager un fichier de file d’attente à tous les modules du collecteur.

   Lors de l’utilisation d’un fichier de file d’attente unique, la gestion, la configuration et l’administration sont quelque peu simplifiées, car l’architecture elle-même est moins complexe. Toutefois, avec un seul fichier de file d’attente, l’ensemble du serveur Web, quel que soit le nombre d’instances, est identifié comme étant WEB1.

* Vous pouvez répliquer l’architecture ci-dessus plusieurs fois et demander à chaque instance de serveur Web de disposer d’un fichier de file d’attente distinct.

   Cela vous permet d’identifier chacune des instances de serveur Web de manière unique. En d’autres termes, l’identification du serveur Web (et du SensorID correspondant dans la [!DNL Sensor] configuration) est une fonction de cette configuration.

Dans tous les cas, les données contiennent toujours toutes les informations de nom d’hôte afin que vous puissiez faire la distinction entre [!DNL www.client.com], [!DNL www2.client.com], etc. La configuration correcte est déterminée par les objectifs de l’analyse et si les analystes doivent segmenter les données en fonction d’une instance spécifique s’exécutant sur un serveur Web.

>[!NOTE]
>
>Ce type de segmentation n&#39;est généralement utilisé que dans l&#39;analyse opérationnelle et n&#39;offre pas beaucoup d&#39;utilité pratique en dehors de ce domaine.

