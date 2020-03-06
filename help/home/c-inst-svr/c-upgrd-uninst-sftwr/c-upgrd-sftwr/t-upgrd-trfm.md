---
description: Procédure de mise à niveau du dossier Transform.
solution: Insight
title: Mise à niveau de la transformation
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mise à niveau de la transformation{#upgrading-transform}

Procédure de mise à niveau du dossier Transform.

1. Ouvrez le [!DNL .zip] fichier du [!DNL Insight Server] package de version et ouvrez le [!DNL Profiles] dossier dans ce [!DNL .zip] fichier.
1. Copiez le [!DNL Transform] dossier dans le [!DNL Profiles] dossier du répertoire [!DNL Insight Server] d’installation. Cette opération remplace le [!DNL Transform] dossier existant.
1. Pour chaque profil qui hérite du [!DNL Transform] profil, vérifiez que le [!DNL profile.cfg] fichier comporte une entrée &quot;Transformer&quot; dans le vecteur Répertoires.
Le retraitement des données commence après la synchronisation du profil.
