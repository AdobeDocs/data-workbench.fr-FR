---
description: Lors de la collecte de données d’événement à partir d’un serveur web, Capteur définit automatiquement un cookie persistant pour chaque visiteur contenant un petit identifiant aléatoire, sans capturer d’informations d’identification personnelle.
title: Comment le capteur identifie-t-il les visiteurs et les sessions ?
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
exl-id: f5781ed6-ac83-4a8e-b412-8966f8c39c41
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---

# Comment le capteur identifie-t-il les visiteurs et les sessions ?{#how-does-sensor-identify-visitors-and-sessions}

{{eol}}

Lors de la collecte de données d’événement à partir d’un serveur web, Capteur définit automatiquement un cookie persistant pour chaque visiteur contenant un petit identifiant aléatoire, sans capturer d’informations d’identification personnelle.

Ce cookie d’Adobe est utilisé pour identifier le visiteur unique et toutes ses sessions associées.

Par défaut, [!DNL Sensor] capture tous les champs du format de fichier journal étendu W3C à partir de chaque en-tête HTTP, mais vous pouvez configurer [!DNL Sensor] pour capturer tout en-tête transmis entre le client et le serveur. Pour plus d’informations sur les champs de données d’événement collectés par [!DNL Sensor] in [!DNL .vsl] fichiers, voir [Champs d’enregistrement des données d’événement](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).

Les navigateurs de certains visiteurs ne stockent pas de cookies de manière persistante et un très petit nombre de navigateurs de visiteurs n’acceptent pas du tout les cookies (même les cookies de session). Même s’ils ne représentent qu’une fraction du trafic total d’un site, ils peuvent entraîner un mauvais comptage important si chaque page vue par un tel visiteur est incorrectement comptabilisée comme une session entière, comme le fait certains logiciels d’analyse de fichiers journaux. Adobe résout ce problème en vous permettant d’analyser les visiteurs avec et sans utiliser de cookies.

Pour plus d’informations sur le filtre Sessions rompues, voir la section *Guide du capteur de Data Workbench*.
