---
description: Les fichiers d’inclusion de jeux de données offrent une méthode souple de configuration de votre jeu de données.
solution: Analytics
title: Utilisation des fichiers d’inclusion de jeux de données
topic: Data workbench
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Utilisation des fichiers d’inclusion de jeux de données{#working-with-dataset-include-files}

Les fichiers d’inclusion de jeux de données offrent une méthode souple de configuration de votre jeu de données.

Dans chaque fichier, vous pouvez définir autant de champs, de transformations ou de dimensions que vous le souhaitez et organiser les fichiers d’inclusion en fonction du profil hérité auquel ils appartiennent. Lors de la configuration de votre jeu de données, vous avez la possibilité de modifier les fichiers d’inclusion du jeu de données fournis avec les profils internes de votre application Adobe ou de créer un nouveau jeu de données pour les profils hérités que vous créez.

Lorsque vous modifiez les paramètres d’un jeu de données, incluez le fichier d’un profil interne et enregistrez le fichier mis à jour dans votre profil de jeu de données ou dans un profil hérité que vous créez, vous remplacez en fait les paramètres d’origine du fichier. Adobe recommande de modifier un fichier d’inclusion de jeux de données pour un profil interne chaque fois que vous devez apporter des modifications mineures au contenu du jeu de données, comme la modification d’un paramètre Condition ou d’un paramètre par défaut. Voir [Modification d’un jeu de données existant : Inclure des fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). Cependant, lorsque vous souhaitez spécifier un nouveau champ à transmettre du traitement du journal à la transformation, mettre à jour ou créer de nouveaux champs à l’aide de transformations ou définir des dimensions étendues, il est préférable de créer un fichier d’inclusion de jeux de données. Voir [Création de nouveaux fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e)d’inclusion de jeux de données. Vous pouvez modifier le fichier que vous créez chaque fois que vous le souhaitez.
