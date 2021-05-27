---
description: Un serveur Data Workbench prend connaissance d’une source de données, telle qu’un capteur, lorsqu’il reçoit des données de cette source.
title: Compréhension de l’heure « À partir de »
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# Compréhension de l’heure « À partir de »{#understanding-as-of-time}

Un serveur Data Workbench prend connaissance d’une source de données, telle qu’un capteur, lorsqu’il reçoit des données de cette source.

L’ À partir du temps est une garantie que [!DNL data workbench server] contient des données pour toutes les sources de données dont il est conscient.

Supposons que nous ayons un ensemble de trois [!DNL Sensors] qui envoient des données à un [!DNL data workbench server] : WEB1, WEB2 et WEB3. À mesure que la fonction [!DNL data workbench server] reçoit et traite les données de ces [!DNL Sensors], elle s’attend automatiquement à des données provenant de chacune de ces sources. Le champ &quot;À partir du moment&quot; indique la dernière fois où [!DNL data workbench server] a reçu des données de ces trois sources.

En termes pratiques, [!DNL data workbench server] se soucie uniquement du &quot;À partir du moment&quot; et non de ce qu’on pourrait appeler &quot;l’heure du mur&quot; ou de l’heure à partir d’une horloge sur le mur. [!DNL data workbench server] connaît l’heure uniquement en tant que &quot;À partir du moment&quot;. Cela est particulièrement important à des fins de création de rapports, car cela garantit que les rapports s’exécutent toujours selon l’état A partir du moment , ce qui garantit que les rapports contenant uniquement des données partielles ne peuvent jamais être envoyés aux utilisateurs finaux du système.

[!DNL data workbench server] utilise les données envoyées à partir de l’émetteur pour fournir les données À partir du moment, qu’il s’agisse de données réelles collectées sur le site web ou de pulsations périodiques envoyées par votre [!DNL Sensors]. Ces pulsations ont deux objectifs :

1. Pour maintenir une connexion persistante HTTP/1.1 ouverte entre [!DNL Sensor] et [!DNL data workbench server].

1. Pour tenir le champ À partir du moment à jour dans le cas où le trafic du site web n’est pas collecté et envoyé à la balise [!DNL data workbench server].
