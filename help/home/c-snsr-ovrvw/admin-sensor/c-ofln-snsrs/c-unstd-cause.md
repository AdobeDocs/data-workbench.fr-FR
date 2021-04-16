---
description: Informations sur la résolution des problèmes de serveur Web, par exemple si le serveur Web est retiré de la rotation ou si le serveur Web échoue.
title: Compréhension des causes
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---

# Compréhension des causes{#understanding-the-causes}

Informations sur la résolution des problèmes de serveur Web, par exemple si le serveur Web est retiré de la rotation ou si le serveur Web échoue.

## Lorsqu&#39;un serveur Web est retiré de la rotation {#section-b9f709099cb44b4f9d1acb38ca5330e3}

Lorsqu’un serveur Web est retiré de la rotation d’un pool de serveurs, mais qu’il est par ailleurs connecté à l’émetteur qui envoie des pulsations périodiques, l’état A partir du moment est conservé à jour et aucune intervention de la part de quiconque n’est nécessaire.

## En cas d&#39;échec d&#39;un serveur Web {#section-19280cf83ca44bd7b1ee11bfc74494d2}

Lorsqu&#39;un serveur Web est complètement hors ligne en raison d&#39;une panne catastrophique, ou qu&#39;il n&#39;envoie pas de données ou de pulsations, le délai A partir de la [!DNL data workbench server] s&#39;arrête pour garantir qu&#39;il représente la dernière fois que [!DNL data workbench server] a reçu des données de TOUTES les sources de données dont il est conscient. Le système lui-même continue à traiter les données, qui sont toujours disponibles pour l’analyse dans le Data Workbench, mais tout ce qui se trouve dans [!DNL data workbench server] qui est basé sur le champ A partir du temps ne fonctionne pas. Par exemple, l’attribut A partir du temps déclenche le rapports et est utilisé pour créer de nombreuses dimensions dérivées dans le système. Lorsque l’attribut A partir du moment s’est arrêté, le rapports n’est pas déclenché et ces dimensions dérivées particulières ne sont pas disponibles.

Par exemple, si WEB2 était hors ligne le 15 juin et n’envoyait aucune donnée pendant cinq jours, la date A partir de maintenant serait le 15 juin. La dimension d’hier, par exemple, serait le 14 juin, même si la date d’aujourd’hui est le 20 juin.
