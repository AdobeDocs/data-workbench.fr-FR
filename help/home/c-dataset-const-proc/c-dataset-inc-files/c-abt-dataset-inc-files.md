---
description: La plupart des profils internes que vous avez reçus avec votre application d’Adobe sont fournis avec leurs propres fichiers de configuration de jeu de données.
title: À propos du fichier d’inclusion de jeux de données
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
exl-id: a23d3f83-4e92-4787-9f77-ee9914cb8893
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 4%

---

# À propos du fichier d’inclusion de jeux de données{#about-dataset-include-files}

La plupart des profils internes que vous avez reçus avec votre application d’Adobe sont fournis avec leurs propres fichiers de configuration de jeu de données.

Les profils internes étant des sous-profils du profil du jeu de données, leurs fichiers de configuration de jeu de données contiennent des règles qui fournissent des paramètres supplémentaires pour le traitement des journaux ou les phases de transformation de la construction du jeu de données. Les fichiers de configuration de jeu de données pour les profils internes et pour tous les profils hérités que vous créez sont appelés des fichiers d’inclusion de jeux de données.

Un fichier d’inclusion de jeu de données contient un sous-ensemble des paramètres contenus dans les fichiers de configuration de jeu de données principaux ( [!DNL Log Processing.cfg] ou [!DNL Transformation.cfg]) pour le profil du jeu de données. Les fichiers d’inclusion de jeux de données contenant des paramètres associés au traitement du journal sont appelés fichiers [!DNL Log Processing Dataset Include] (voir [Fichiers d’inclusion de jeux de données de traitement de journal](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)), tandis que les fichiers d’inclusion de jeux de données associés à la transformation sont appelés fichiers [!DNL Transformation Dataset Include]. Voir [Fichiers d’inclusion de jeux de données de transformation](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). Vous pouvez créer plusieurs fichiers d’inclusion de jeux de données à utiliser dans le processus de construction du jeu de données. Le jeu de données complet comprend tous les champs, transformations et dimensions étendues définis dans tous les fichiers de configuration du jeu de données pour le profil du jeu de données et les profils hérités.
