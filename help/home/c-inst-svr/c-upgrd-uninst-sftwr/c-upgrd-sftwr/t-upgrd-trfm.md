---
description: Procédure de mise à niveau du dossier Transform.
solution: Analytics
title: Mise à niveau de Transform
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---


# Mise à niveau de Transform{#upgrading-transform}

Procédure de mise à niveau du dossier Transform.

1. Ouvrez le [!DNL .zip] fichier pour le [!DNL Insight Server] package de publication, puis ouvrez le [!DNL Profiles] dossier dans ce [!DNL .zip] fichier.
1. Copiez le [!DNL Transform] dossier dans le [!DNL Profiles] dossier du répertoire d’ [!DNL Insight Server] installation. Cette opération remplace le [!DNL Transform] dossier existant.
1. Pour chaque profil qui hérite du [!DNL Transform] profil, vérifiez que le [!DNL profile.cfg] fichier comporte une entrée &quot;Transformer&quot; dans le vecteur Répertoires.
Le retraitement des données commence après la synchronisation du profil.
