---
description: Lors de la collecte de données d’événement à partir d’un serveur Web, Sensor définit automatiquement un cookie persistant pour chaque visiteur contenant un petit identifiant aléatoire, sans capturer d’informations d’identification personnelle.
solution: Insight
title: Comment le capteur identifie-t-il les visiteurs et les sessions ?
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Comment le capteur identifie-t-il les visiteurs et les sessions ?{#how-does-sensor-identify-visitors-and-sessions}

Lors de la collecte de données d’événement à partir d’un serveur Web, Sensor définit automatiquement un cookie persistant pour chaque visiteur contenant un petit identifiant aléatoire, sans capturer d’informations d’identification personnelle.

Ce cookie Adobe permet d’identifier le visiteur unique et toutes ses sessions associées.

Par défaut, [!DNL Sensor] capture tous les champs du format de fichier journal étendu W3C de chaque en-tête HTTP, mais vous pouvez configurer [!DNL Sensor] pour capturer tout en-tête transmis entre le client et le serveur. Pour plus d’informations sur les champs de données d’événement collectés par [!DNL Sensor] dans [!DNL .vsl] les fichiers, voir Champs [d’enregistrement des données d’](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)événement.

Les navigateurs de certains visiteurs ne stockent pas de cookies de manière permanente et un très petit nombre de visiteurs n’acceptent pas du tout les cookies (même les cookies de session). Bien qu’ils ne représentent qu’une fraction du trafic total d’un site, ils peuvent entraîner un mauvais comptage important si chaque page vue par un tel visiteur est comptabilisée incorrectement comme une session entière, comme le fait certains logiciels d’analyse de fichiers journaux. Adobe résout ce problème en vous permettant d’analyser les visiteurs avec et sans utiliser de cookies.

Pour plus d’informations sur le filtre de sessions rompues, consultez le Guide *de l’outil de* données Sensor.
