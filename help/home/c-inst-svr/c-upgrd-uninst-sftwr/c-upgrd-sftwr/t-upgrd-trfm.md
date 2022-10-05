---
description: Procédure de mise à niveau du dossier Transform.
title: Mise à niveau de Transform
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# Mise à niveau de Transform{#upgrading-transform}

{{eol}}

Procédure de mise à niveau du dossier Transform.

1. Ouvrez le [!DNL .zip] pour le fichier [!DNL Insight Server] et ouvrez le module externe [!DNL Profiles] dossier dans [!DNL .zip] fichier .
1. Copiez le [!DNL Transform] vers le dossier [!DNL Profiles] dans votre dossier [!DNL Insight Server] répertoire d’installation. Cette opération remplace le [!DNL Transform] dossier.
1. Pour chaque profil qui hérite de la variable [!DNL Transform] , confirmez que la variable [!DNL profile.cfg] comporte une entrée &quot;Transform&quot; dans le vecteur Répertoires.
Le retraitement des données commence après la synchronisation du profil.
