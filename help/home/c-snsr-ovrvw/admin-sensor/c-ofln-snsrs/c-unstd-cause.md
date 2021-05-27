---
description: Informations sur la résolution des problèmes liés au serveur web, par exemple si le serveur web est hors rotation ou si le serveur web échoue.
title: Compréhension des causes
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---

# Compréhension des causes{#understanding-the-causes}

Informations sur la résolution des problèmes liés au serveur web, par exemple si le serveur web est hors rotation ou si le serveur web échoue.

## Lorsqu’un serveur web est retiré de la rotation {#section-b9f709099cb44b4f9d1acb38ca5330e3}

Lorsqu’un serveur web est extrait de la rotation d’un pool de serveurs, mais qu’il est connecté autrement à l’émetteur qui envoie des pulsations périodiques, l’heure est tenue à jour et aucune intervention de la part de quiconque n’est nécessaire.

## En cas d’échec d’un serveur web {#section-19280cf83ca44bd7b1ee11bfc74494d2}

Lorsqu’un serveur web est complètement hors ligne en raison d’une défaillance catastrophique ou qu’il n’envoie pas de données ou de pulsations, l’heure À partir de [!DNL data workbench server] s’arrête pour garantir qu’il représente la dernière fois que [!DNL data workbench server] a reçu des données de TOUTES les sources de données dont il est informé. Le système lui-même continue à traiter les données, qui sont toujours disponibles pour analyse en Data Workbench, mais tout ce qui se trouve dans la balise [!DNL data workbench server] basée sur la valeur &quot;À partir du moment&quot; ne fonctionne pas. Par exemple, le champ À partir du temps déclenche la création de rapports et est utilisé pour créer de nombreuses dimensions dérivées dans le système. Lorsque le délai A partir de l’expiration s’est arrêté, la création de rapports n’est pas déclenchée et ces dimensions dérivées spécifiques ne sont pas disponibles.

Par exemple, si WEB2 est hors ligne le 15 juin et n’a pas envoyé de données pendant cinq jours, l’heure serait le 15 juin. La dimension d’Hier, par exemple, serait le 14 juin, même si la date d’aujourd’hui est le 20 juin.
