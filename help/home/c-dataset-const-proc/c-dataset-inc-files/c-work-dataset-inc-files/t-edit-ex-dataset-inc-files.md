---
description: Les étapes de modification d’un jeu de données existant incluent des fichiers.
title: Modification des fichiers d’inclusion de jeux de données existants
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# Modification des fichiers d’inclusion de jeux de données existants{#editing-existing-dataset-include-files}

Les étapes de modification d’un jeu de données existant incluent des fichiers.

Vous ouvrez un fichier d’inclusion de jeu de données existant à l’aide de [!DNL Profile Manager] dans l’outil de données.

Pour plus d&#39;informations sur l&#39;ouverture et l&#39;utilisation de [!DNL Profile Manager], consultez le *Guide de l&#39;utilisateur Data Workbench*.

1. Lorsque vous travaillez dans votre profil de jeux de données, ouvrez [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour afficher le contenu de l&#39;annuaire.

   * Pour ouvrir un fichier [!DNL Log Processing Dataset Include], cliquez sur **[!UICONTROL Log Processing]** pour afficher le contenu du répertoire.

   * Pour ouvrir un fichier [!DNL Transformation Dataset Include], cliquez sur **[!UICONTROL Transformation]** pour afficher le contenu du répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche en regard du fichier d’inclusion du jeu de données souhaité, puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre de configuration s&#39;affiche.

   Vous pouvez également ouvrir un fichier d&#39;inclusion de jeu de données à partir d&#39;un [!DNL Transformation Dependency Maps]. Pour plus d&#39;informations sur [!DNL Transformation Dependency Maps], voir [Retraitement et retransformation](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Modifiez les paramètres dans le fichier de configuration selon vos besoins. Voir [Jeu de données de traitement du journal Inclure les fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) ou [Jeu de données de transformation Inclure les fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) pour la description des paramètres.

   Lors de la modification d’un jeu de données, vous pouvez utiliser des touches de raccourci pour les fonctions de modification de base, notamment couper (Ctrl+x), copier (Ctrl+c), coller (Ctrl+v), annuler (Ctrl+z), rétablir (Ctrl+Maj+z), sélectionner une section (cliquer+faire glisser) et sélectionner tout (Ctrl+a). En outre, vous pouvez utiliser les raccourcis pour copier et coller le texte d&#39;un fichier de configuration ( [!DNL .cfg]) vers un autre.

1. Pour enregistrer vos modifications, cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
1. Pour que les modifications apportées localement prennent effet, dans [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, où le nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données. Le retraitement ou la retransformation des données commence après la synchronisation du profil du jeu de données.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.
