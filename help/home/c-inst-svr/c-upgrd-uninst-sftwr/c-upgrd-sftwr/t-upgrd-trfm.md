---
description: Procédure de mise à niveau du dossier Transform.
title: Mise à niveau de Transform
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# Mise à niveau de Transform{#upgrading-transform}

Procédure de mise à niveau du dossier Transform.

1. Ouvrez le fichier [!DNL .zip] pour le module de version [!DNL Insight Server] et ouvrez le dossier [!DNL Profiles] dans ce fichier [!DNL .zip].
1. Copiez le dossier [!DNL Transform] dans le dossier [!DNL Profiles] de votre répertoire d’installation [!DNL Insight Server]. Cela remplace le dossier [!DNL Transform] existant.
1. Pour chaque profil qui hérite du profil [!DNL Transform], vérifiez que le fichier [!DNL profile.cfg] comporte une entrée &quot;Transform&quot; dans le vecteur Directories.
Le retraitement des données commence après la synchronisation du profil.
