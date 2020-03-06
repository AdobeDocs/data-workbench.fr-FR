---
description: Informations sur la résolution des problèmes du serveur Web, par exemple si le serveur Web est retiré de la rotation ou en cas d’échec du serveur Web.
solution: Insight
title: Compréhension des causes
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Compréhension des causes{#understanding-the-causes}

Informations sur la résolution des problèmes du serveur Web, par exemple si le serveur Web est retiré de la rotation ou en cas d’échec du serveur Web.

## Lorsqu&#39;un serveur Web est retiré de la rotation {#section-b9f709099cb44b4f9d1acb38ca5330e3}

Lorsqu’un serveur Web est retiré de la rotation d’un pool de serveurs, mais qu’il est par ailleurs connecté à l’émetteur qui envoie des pulsations périodiques, l’état A partir du moment est conservé à jour et aucune intervention de la part de quiconque n’est nécessaire.

## En cas d’échec d’un serveur Web {#section-19280cf83ca44bd7b1ee11bfc74494d2}

Lorsqu’un serveur Web est complètement hors ligne en raison d’une défaillance catastrophique, ou qu’il n’envoie pas de données ou de pulsations, le délai A partir de la [!DNL data workbench server] fin s’arrête pour garantir qu’il représente la dernière fois que les données [!DNL data workbench server] ont été reçues de TOUTES les sources de données dont il est conscient. Le système lui-même continue à traiter les données, qui sont toujours disponibles pour l’analyse dans les Outils de données, mais tout ce qui [!DNL data workbench server] est basé sur le paramètre A partir du moment ne fonctionne pas. Par exemple, A partir du moment déclenche la création de rapports et est utilisé pour créer de nombreuses dimensions dérivées dans le système. Lorsque l’option A partir du moment est arrêtée, la création de rapports n’est pas déclenchée et ces dimensions dérivées particulières ne sont pas disponibles.

Par exemple, si WEB2 est hors ligne le 15 juin et n’a pas envoyé de données pendant cinq jours, la date à partir du 15 juin sera le même. La dimension d’hier, par exemple, serait le 14 juin, même si la date d’aujourd’hui est le 20 juin.
