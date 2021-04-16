---
description: Lors de la collecte de données de événement à partir d’un serveur Web, Sensor définit automatiquement un cookie persistant pour chaque visiteur contenant un petit identifiant aléatoire, sans capturer d’informations d’identification personnelle.
title: Comment le capteur identifie-t-il les visiteurs et les sessions ?
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
exl-id: f5781ed6-ac83-4a8e-b412-8966f8c39c41
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---

# Comment le capteur identifie-t-il les visiteurs et les sessions ?{#how-does-sensor-identify-visitors-and-sessions}

Lors de la collecte de données de événement à partir d’un serveur Web, Sensor définit automatiquement un cookie persistant pour chaque visiteur contenant un petit identifiant aléatoire, sans capturer d’informations d’identification personnelle.

Ce cookie Adobe est utilisé pour identifier le visiteur unique et toutes ses sessions associées.

Par défaut, [!DNL Sensor] capture tous les champs du format de fichier journal étendu W3C de chaque en-tête HTTP, mais vous pouvez configurer [!DNL Sensor] pour capturer tout en-tête transmis entre le client et le serveur. Pour plus d&#39;informations sur les champs de données de événement collectés par [!DNL Sensor] dans les fichiers [!DNL .vsl], voir [Champs d&#39;enregistrement des données de Événement](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).

Les navigateurs de certains visiteurs ne stockent pas de cookies de façon permanente et un très petit nombre de navigateurs visiteurs n’acceptent pas du tout les cookies (même les cookies de session). Bien qu’ils ne représentent qu’une fraction du trafic total d’un site, ils peuvent entraîner un mauvais comptage important si chaque vue de page par un tel visiteur est comptabilisée incorrectement comme une session entière, comme le fait certains logiciels d’analyse de fichiers journaux. L’Adobe résout ce problème en vous permettant d’analyser les visiteurs avec et sans utiliser de cookies.

Pour plus d&#39;informations sur le filtre de sessions rompues, consultez le *Guide du capteur de Data Workbench*.
