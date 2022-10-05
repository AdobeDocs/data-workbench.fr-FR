---
description: Les fichiers d’inclusion de jeux de données offrent une méthode flexible de configuration de votre jeu de données.
title: Utilisation des fichiers d’inclusion de jeux de données
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
exl-id: 94044c85-030c-4912-9546-d4a34b4115e0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 4%

---

# Utilisation des fichiers d’inclusion de jeux de données{#working-with-dataset-include-files}

{{eol}}

Les fichiers d’inclusion de jeux de données offrent une méthode flexible de configuration de votre jeu de données.

Dans chaque fichier, vous pouvez définir autant de champs, transformations ou dimensions que vous le souhaitez, et vous pouvez organiser les fichiers d’inclusion en fonction du profil hérité auquel ils appartiennent. Lors de la configuration de votre jeu de données, vous avez la possibilité de modifier les fichiers d’inclusion du jeu de données fournis avec les profils internes de votre application d’Adobe ou de créer de nouveaux fichiers d’inclusion de jeux de données pour tous les profils hérités que vous créez.

Lorsque vous modifiez les paramètres d’un fichier d’inclusion de jeux de données pour un profil interne et que vous enregistrez le fichier mis à jour dans votre profil de jeu de données ou un profil hérité que vous créez, vous remplacez effectivement les paramètres d’origine du fichier. Adobe recommande de modifier un fichier d’inclusion de jeu de données pour un profil interne chaque fois que vous devez apporter des modifications mineures au contenu du jeu de données, telles que la modification d’un paramètre de condition ou du paramètre par défaut. Voir [Modification de fichiers d’inclusion de jeux de données existants](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). Cependant, lorsque vous souhaitez spécifier un nouveau champ à transmettre du traitement du journal à la transformation, mettre à jour ou créer de nouveaux champs à l’aide de transformations ou définir des dimensions étendues, il est préférable de créer un fichier d’inclusion de jeux de données. Voir [Création de nouveaux fichiers d’inclusion de jeux de données](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e). Vous pouvez modifier le fichier que vous créez chaque fois que vous le souhaitez.
