---
description: Mesures de profil de valeur
title: Mesures de profil de valeur
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
exl-id: 9e95008c-1162-4f50-89d2-dcf5fcf8746a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 17%

---

# Mesures de profil de valeur{#value-profile-metrics}

{{eol}}

| Mesure | Formule | Niveau | Description |
|---|---|---|---|
| Conversion | `Sessions[not Session_Value=#0]/Sessions` | Session | Pourcentage de sessions qui ont généré de la valeur commerciale (tel que défini par le modèle de valeur commerciale). |
| Pct de valeur | `Value/total(Value)` | Session | Pourcentage de la valeur globale générée à partir du jeu de sessions sélectionné. |
| Valeur | `sum(Session_Value, Session)*0.01` | Session | Valeur totale de l’entreprise générée, en dollars (telle que définie par le modèle de valeur de l’entreprise). |
| Événements de valeur | `Sessions[not Session_Value=#0]` | Session | Nombre de sessions qui ont généré de la valeur commerciale (tel que défini par le modèle de valeur commerciale). |
| Événements de valeur par visiteur | `(Value_Events/Visitors) by Visitor` | Visiteur | Nombre moyen de sessions pour chaque visiteur ayant généré une valeur commerciale (telle que définie par le modèle de valeur commerciale ). |
| Valeur par visiteur | `(Value/Visitors) by Visitor` | Visiteur | Valeur commerciale moyenne générée, en dollars, par chaque visiteur. |
