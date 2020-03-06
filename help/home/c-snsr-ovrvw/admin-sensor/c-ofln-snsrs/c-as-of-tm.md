---
description: Un serveur d’outils de données se rend compte d’une source de données, telle qu’un capteur, lorsqu’il reçoit des données de cette source.
solution: Insight
title: Comprendre Le Temps "À Partir De"
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Comprendre Le Temps &quot;À Partir De&quot;{#understanding-as-of-time}

Un serveur d’outils de données se rend compte d’une source de données, telle qu’un capteur, lorsqu’il reçoit des données de cette source.

L’option A partir du moment est une garantie que l’ [!DNL data workbench server] utilisateur dispose de données pour toutes les sources de données dont il a connaissance.

Supposons que nous ayons un ensemble de trois [!DNL Sensors] qui envoient des données à un [!DNL data workbench server]: WEB1, WEB2 et WEB3. Lorsque le [!DNL data workbench server] client reçoit et traite les données de ces sources [!DNL Sensors], il s’attend automatiquement à ce que les données proviennent de chacune d’elles. Le champ A partir du moment indique la dernière fois que les données [!DNL data workbench server] ont été reçues de ces trois sources.

En termes pratiques, le [!DNL data workbench server] seul souci concerne le A partir du temps et non ce que l&#39;on pourrait appeler le temps des murs, ou l&#39;heure à partir d&#39;une horloge sur le mur. Le [!DNL data workbench server] nom du moment est &quot;A partir du moment&quot;. Cela est particulièrement important aux fins de création de rapports, car il garantit que les rapports s’exécutent toujours selon le calendrier A partir duquel les rapports ne contenant que des données partielles ne peuvent jamais être envoyés aux utilisateurs finaux du système.

L’ [!DNL data workbench server] utilisateur utilise les données envoyées par l’émetteur pour fournir les données A partir du moment, qu’il s’agisse de données réelles collectées sur le site Web ou de pulsations périodiques envoyées par votre [!DNL Sensors]utilisateur. Ces pulsations ont deux objectifs :

1. Pour maintenir une connexion permanente HTTP/1.1 ouverte entre le [!DNL Sensor] et le [!DNL data workbench server].

1. Pour conserver l’état A partir du moment à jour dans le cas où le trafic du site Web n’est pas collecté et envoyé au [!DNL data workbench server].

