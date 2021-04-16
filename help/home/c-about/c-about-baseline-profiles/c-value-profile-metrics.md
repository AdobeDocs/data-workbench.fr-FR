---
description: Mesures de profil de valeur
title: Mesures de profil de valeur
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
exl-id: 9e95008c-1162-4f50-89d2-dcf5fcf8746a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 17%

---

# Mesures de profil de valeur{#value-profile-metrics}

| Mesure | Formule | Niveau | Description |
|---|---|---|---|
| Conversion | `Sessions[not Session_Value=#0]/Sessions` | Session | Pourcentage de sessions qui ont généré de la valeur commerciale (tel que défini par le modèle de valeur commerciale). |
| Pct de valeur | `Value/total(Value)` | Session | Pourcentage de la valeur globale générée à partir du jeu de sessions sélectionné. |
| Valeur | `sum(Session_Value, Session)*0.01` | Session | Valeur commerciale totale générée, en dollars (telle que définie par le modèle de valeur commerciale). |
| Événements de valeur | `Sessions[not Session_Value=#0]` | Session | Nombre de sessions qui ont généré une valeur commerciale (tel que défini par le modèle de valeur commerciale). |
| Événements de valeur par Visiteur | `(Value_Events/Visitors) by Visitor` | Visiteur | Nombre moyen de sessions pour chaque visiteur ayant généré de la valeur commerciale (tel que défini par le modèle de valeur commerciale). |
| Valeur par Visiteur | `(Value/Visitors) by Visitor` | Visiteur | Valeur moyenne de l’entreprise générée, en dollars, par chaque visiteur. |
