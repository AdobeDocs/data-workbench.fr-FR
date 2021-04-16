---
description: Un serveur d’outils de données prend connaissance d’une source de données, telle qu’un capteur, lorsqu’il reçoit des données de cette source.
title: Compréhension de l’heure « À partir de »
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# Compréhension de l’heure « À partir de »{#understanding-as-of-time}

Un serveur d’outils de données prend connaissance d’une source de données, telle qu’un capteur, lorsqu’il reçoit des données de cette source.

L’option A partir du moment est une garantie que [!DNL data workbench server] contient des données pour toutes les sources de données dont il a connaissance.

Supposons que nous ayons un ensemble de trois [!DNL Sensors] qui envoient des données à un [!DNL data workbench server] : WEB1, WEB2 et WEB3. Comme [!DNL data workbench server] reçoit et traite les données de ces [!DNL Sensors], il s&#39;attend automatiquement à ce que les données proviennent de chacune de ces sources. Le champ A partir du moment indique la dernière fois où [!DNL data workbench server] a reçu des données de ces trois sources.

En termes pratiques, le [!DNL data workbench server] ne se soucie que du &quot;A partir du temps&quot; et non de ce que l&#39;on pourrait appeler &quot;l&#39;heure du mur&quot;, ou de l&#39;heure à partir d&#39;une horloge sur le mur. Le [!DNL data workbench server] ne connaît l&#39;heure que comme &quot;A partir du temps&quot;. Ceci est particulièrement important à des fins de rapports car il garantit que les rapports s’exécutent toujours en fonction de l’option A partir du moment, ce qui garantit que les rapports ne contenant que des données partielles ne peuvent jamais être envoyés aux utilisateurs finaux du système.

[!DNL data workbench server] utilise les données envoyées par l&#39;émetteur pour fournir le champ A partir du moment, qu&#39;il s&#39;agisse de données réelles collectées sur le site Web ou de pulsations périodiques envoyées par votre [!DNL Sensors]. Ces pulsations ont deux objectifs :

1. Pour maintenir une connexion permanente HTTP/1.1 ouverte entre [!DNL Sensor] et [!DNL data workbench server].

1. Pour que l’état A partir du moment reste à jour dans le événement où le trafic du site Web n’est pas collecté et envoyé à [!DNL data workbench server].
