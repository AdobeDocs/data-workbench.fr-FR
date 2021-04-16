---
description: Les fichiers inclus dans les jeux de données offrent une méthode souple pour configurer votre jeu de données.
title: Utilisation des fichiers d’inclusion de jeux de données
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
exl-id: 94044c85-030c-4912-9546-d4a34b4115e0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 4%

---

# Utilisation des fichiers d’inclusion de jeux de données{#working-with-dataset-include-files}

Les fichiers inclus dans les jeux de données offrent une méthode souple pour configurer votre jeu de données.

Dans chaque fichier, vous pouvez définir autant de champs, de transformations ou de dimensions que vous le souhaitez et organiser les fichiers inclus en fonction de l’profil hérité auquel ils appartiennent. Lors de la configuration de votre jeu de données, vous avez la possibilité de modifier le jeu de données en incluant les fichiers fournis avec les profils internes de votre application d&#39;Adobe ou de créer un nouveau jeu de données en incluant les fichiers pour tous les profils hérités que vous créez.

Lorsque vous modifiez les paramètres d&#39;un jeu de données, incluez un fichier pour un profil interne et enregistrez le fichier mis à jour sur votre profil de données ou un profil hérité que vous créez, vous remplacez en fait les paramètres d&#39;origine du fichier. Adobe recommande de modifier le fichier d&#39;inclusion d&#39;un jeu de données pour un profil interne chaque fois que vous devez apporter des modifications mineures au contenu du jeu de données, telles que la modification d&#39;un paramètre Condition ou du paramètre par défaut. Voir [Modification d&#39;un jeu de données existant : Inclure des fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). Cependant, lorsque vous souhaitez spécifier un nouveau champ à transmettre du traitement du journal à la transformation, mettre à jour ou créer de nouveaux champs à l’aide de transformations ou définir des dimensions étendues, il est préférable de créer un fichier d’inclusion de jeux de données. Voir [Création de nouveaux jeux de données : Inclure des fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e). Vous pouvez modifier le fichier que vous créez chaque fois que vous le jugez approprié.
