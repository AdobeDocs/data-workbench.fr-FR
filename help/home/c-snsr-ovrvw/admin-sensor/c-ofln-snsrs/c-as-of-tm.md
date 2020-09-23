---
description: Un serveur d’outils de données prend connaissance d’une source de données, telle qu’un capteur, lorsqu’il reçoit des données de cette source.
solution: Analytics
title: Compréhension de l’heure « À partir de »
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---


# Compréhension de l’heure « À partir de »{#understanding-as-of-time}

Un serveur d’outils de données prend connaissance d’une source de données, telle qu’un capteur, lorsqu’il reçoit des données de cette source.

L’option A partir du moment est une garantie que le [!DNL data workbench server] système dispose de données pour toutes les sources de données dont il a connaissance.

Supposons que nous ayons un ensemble de trois [!DNL Sensors] qui envoient des données à un [!DNL data workbench server]: WEB1, WEB2 et WEB3. Lorsque le [!DNL data workbench server] client reçoit et traite les données de ces [!DNL Sensors]sources, il s’attend automatiquement à ce que les données proviennent de chacune de ces sources. Le champ A partir du moment indique la dernière fois où les données [!DNL data workbench server] ont été reçues de ces trois sources.

En termes pratiques, le [!DNL data workbench server] seul souci concerne le &quot;A partir du temps&quot; et non ce que l&#39;on pourrait appeler &quot;l&#39;heure du mur&quot;, ou l&#39;heure à partir d&#39;une horloge sur le mur. L&#39; [!DNL data workbench server] utilisateur ne connaît l&#39;heure que comme &quot;A partir du temps&quot;. Ceci est particulièrement important à des fins de rapports car il garantit que les rapports s’exécutent toujours en fonction de l’option A partir du moment, ce qui garantit que les rapports ne contenant que des données partielles ne peuvent jamais être envoyés aux utilisateurs finaux du système.

L’ [!DNL data workbench server] utilisateur utilise les données envoyées par l’émetteur pour fournir les données A partir du moment, qu’il s’agisse de données réelles collectées sur le site Web ou de pulsations périodiques envoyées par votre [!DNL Sensors]utilisateur. Ces pulsations ont deux objectifs :

1. Pour maintenir une connexion permanente HTTP/1.1 ouverte entre le [!DNL Sensor] et le [!DNL data workbench server].

1. Pour que l’état A partir de la date d’envoi reste à jour dans le événement où le trafic du site Web n’est pas collecté et envoyé à l’ [!DNL data workbench server]utilisateur.

