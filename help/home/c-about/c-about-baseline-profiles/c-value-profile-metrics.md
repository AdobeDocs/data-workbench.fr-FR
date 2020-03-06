---
description: valeur nulle
solution: Analytics
title: Mesures de profil de valeur
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mesures de profil de valeur{#value-profile-metrics}

| Mesure | Formule | Niveau | Description |
|---|---|---|---|
| Conversion | [![Sessions DNL, pas Session_Value=#0]/Sessions] | Session | Pourcentage de sessions qui ont généré de la valeur commerciale (comme défini par le modèle de valeur commerciale). |
| Pct de valeur | [!DNL Value/total(Value)] | Session | Pourcentage de la valeur globale générée à partir du jeu de sessions sélectionné. |
| Valeur | [!DNL sum(Session_Value, Session)*0.01] | Session | Valeur totale de l&#39;entreprise générée, en dollars (telle que définie par le modèle de valeur de l&#39;entreprise). |
| Evénements de valeur | [!DNL[Sessionsnot Session_Value=#0]] | Session | Nombre de sessions qui ont généré une valeur commerciale (telle que définie par le modèle de valeur commerciale). |
| Événements de valeur par visiteur | [!DNL (Value_Events/Visitors) by Visitor] | Visitor | Nombre moyen de sessions pour chaque visiteur ayant généré de la valeur commerciale (comme défini par le modèle de valeur commerciale). |
| Valeur par visiteur | [!DNL (Value/Visitors) by Visitor] | Visitor | Valeur commerciale moyenne générée, en dollars, par chaque visiteur. |