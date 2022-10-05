---
description: Un serveur Data Workbench prend connaissance d’une source de données, telle qu’un capteur, lorsqu’il reçoit des données de cette source.
title: Compréhension de l’heure « À partir de »
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# Compréhension de l’heure « À partir de »{#understanding-as-of-time}

{{eol}}

Un serveur Data Workbench prend connaissance d’une source de données, telle qu’un capteur, lorsqu’il reçoit des données de cette source.

À l’heure actuelle, la variable [!DNL data workbench server] contient des données pour toutes les sources de données dont elle est consciente.

Disons que nous avons un ensemble de trois [!DNL Sensors] qui envoient des données à un [!DNL data workbench server]: WEB1, WEB2 et WEB3. Comme la variable [!DNL data workbench server] reçoit et traite les données de ces [!DNL Sensors], des données de chacune de ces sources sont automatiquement attendues. Le champ À partir du moment indique la dernière fois que la variable [!DNL data workbench server] ont reçu des données de ces trois sources.

En termes pratiques, la [!DNL data workbench server] se soucie uniquement de l’heure et non de ce qu’on pourrait appeler &quot;l’heure du mur&quot; ou de l’heure d’une horloge sur le mur. Le [!DNL data workbench server] ne connaît l’heure que comme À partir du moment. Cela est particulièrement important à des fins de création de rapports, car cela garantit que les rapports s’exécutent toujours selon l’état A partir du moment , ce qui garantit que les rapports contenant uniquement des données partielles ne peuvent jamais être envoyés aux utilisateurs finaux du système.

Le [!DNL data workbench server] utilise les données envoyées par l’émetteur pour fournir les données &quot;À partir du moment&quot;, qu’il s’agisse de données réelles collectées sur le site web ou de pulsations périodiques envoyées par votre [!DNL Sensors]. Ces pulsations ont deux objectifs :

1. Pour maintenir une connexion persistante HTTP/1.1 ouverte entre la variable [!DNL Sensor] et le [!DNL data workbench server].

1. Pour tenir le champ À partir du moment à jour dans le cas où le trafic du site web n’est pas collecté et envoyé au [!DNL data workbench server].
