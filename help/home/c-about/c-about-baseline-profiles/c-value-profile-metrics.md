---
description: valeur nulle
solution: Analytics
title: Mesures de profil de valeur
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: 662bf8fdff196814e5a11c1f5e1ae12d4d57e1db
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 16%

---


# Mesures de profil de valeur{#value-profile-metrics}

| Mesure | Formule | Niveau | Description |
|---|---|---|---|
| Conversion  | `Sessions[not Session_Value=#0]/Sessions` | Session | Pourcentage de sessions qui ont généré de la valeur commerciale (tel que défini par le modèle de valeur commerciale). |
| Pct de valeur | `Value/total(Value)` | Session | Pourcentage de la valeur globale générée à partir du jeu de sessions sélectionné. |
| Valeur | `sum(Session_Value, Session)*0.01` | Session | Valeur commerciale totale générée, en dollars (telle que définie par le modèle de valeur commerciale). |
| Événements de valeur | `Sessions[not Session_Value=#0]` | Session | Nombre de sessions qui ont généré une valeur commerciale (tel que défini par le modèle de valeur commerciale). |
| Événements de valeur par Visiteur | `(Value_Events/Visitors) by Visitor` | Visitor | Nombre moyen de sessions pour chaque visiteur ayant généré de la valeur commerciale (tel que défini par le modèle de valeur commerciale). |
| Valeur par Visiteur | `(Value/Visitors) by Visitor` | Visitor | Valeur moyenne de l’entreprise générée, en dollars, par chaque visiteur. |
