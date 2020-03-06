---
description: Les étapes de modification d’un jeu de données existant incluent des fichiers.
solution: Analytics
title: Modification d’un jeu de données existant - Inclure des fichiers
topic: Data workbench
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Modification d’un jeu de données existant - Inclure des fichiers{#editing-existing-dataset-include-files}

Les étapes de modification d’un jeu de données existant incluent des fichiers.

Vous ouvrez un fichier d’inclusion d’un jeu de données existant à l’aide de l’outil [!DNL Profile Manager] in data.

Pour plus d’informations sur l’ouverture et l’utilisation de [!DNL Profile Manager]Data Workbench, consultez le Guide *de l’utilisateur des outils de* données.

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez le fichier [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour afficher le contenu du répertoire.

   * Pour ouvrir un [!DNL Log Processing Dataset Include] fichier, cliquez **[!UICONTROL Log Processing]** sur pour afficher le contenu du répertoire.

   * Pour ouvrir un [!DNL Transformation Dataset Include] fichier, cliquez **[!UICONTROL Transformation]** sur pour afficher le contenu du répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche en regard du fichier d’inclusion du jeu de données souhaité, puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre de configuration s’affiche.

   Vous pouvez également ouvrir un fichier d’inclusion d’un jeu de données à partir d’un fichier [!DNL Transformation Dependency Maps]. Pour plus d’informations sur [!DNL Transformation Dependency Maps], voir [Retraitement et retransformation](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Modifiez les paramètres dans le fichier de configuration selon vos besoins. Voir [Journal des données de traitement Inclure les fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) ou [Transformation des données Inclure les fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) pour obtenir la description des paramètres.

   Lors de la modification d’un fichier d’inclusion d’un jeu de données dans une fenêtre de l’outil de données, vous pouvez utiliser des touches de raccourci pour les fonctions de modification de base, notamment couper (Ctrl+x), copier (Ctrl+c), coller (Ctrl+v), annuler (Ctrl+z), rétablir (Ctrl+Maj+z), sélectionner une section (cliquer+faire glisser) et sélectionner tout (Ctrl+a). En outre, vous pouvez utiliser les raccourcis pour copier et coller le texte d’un fichier de configuration ( [!DNL .cfg]) vers un autre.

1. Pour enregistrer vos modifications, cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
1. Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;>**[!UICONTROL profile name]***, où nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données. Le retraitement ou la retransformation des données commence après la synchronisation du profil du jeu de données.

   >[!NOTE]
   >
   >N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

