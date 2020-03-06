---
description: Vous pouvez définir des transformations de données à appliquer pendant la phase de traitement du journal ou de transformation de la construction du jeu de données.
solution: Analytics
title: Définition d'une transformation
topic: Data workbench
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Définition d&#39;une transformation{#defining-a-transformation}

Vous pouvez définir des transformations de données à appliquer pendant la phase de traitement du journal ou de transformation de la construction du jeu de données.

>[!NOTE]
>
>Adobe recommande de définir les transformations dans les fichiers [!DNL Log Processing] ou [!DNL Transformation Dataset Include] plutôt que dans [!DNL Log Processing.cfg] ou [!DNL Transformation.cfg].

Les transformations suivantes fonctionnent uniquement lorsqu’elles sont définies dans le [!DNL Transformation.cfg] fichier ou dans un [!DNL Transformation Dataset Include] fichier :

* [](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)AjouterURL
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [Lignes de recherche](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [Sources de données ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessioniser](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**Pour définir une transformation**

1. Utilisez le [!DNL Profile Manager] pour ouvrir le fichier de configuration du jeu de données dans lequel vous souhaitez définir la transformation.

   * (Recommandé) Pour ouvrir un fichier d’inclusion de jeu de données, voir Fichiers [inclus dans le jeu de](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)données.
   * Pour ouvrir le [!DNL Log Processing.cfg] fichier, voir [Modification du fichier](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)de configuration du traitement du journal.

   * Pour ouvrir le [!DNL Transformation.cfg] fichier, voir [Modification du fichier](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)de configuration de transformation.

1. Cliquez avec le bouton droit **[!UICONTROL Transformations]**, puis cliquez sur **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]**>*.
1. Saisissez les informations appropriées pour votre transformation. Pour obtenir des descriptions des types de transformation et des informations sur leurs paramètres, consultez les sections suivantes :

   * [Transformations standard](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [Transformations URI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [Intégration des données de recherche](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. Après avoir défini votre ou vos transformations dans le fichier de configuration, enregistrez le fichier localement et enregistrez-le dans votre profil de jeu de données sur le serveur de l’outil de données.

       Conseils pour la définition et la modification des transformations :
   
   * Lors de la modification de la configuration d’une transformation dans une fenêtre du Outils de données, vous pouvez utiliser des touches de raccourci pour les fonctions de modification de base, notamment couper (Ctrl+x), copier (Ctrl+c), coller (Ctrl+v), annuler (Ctrl+z), rétablir (Ctrl+Maj+z), sélectionner une section (cliquer+faire glisser) et sélectionner tout (Ctrl+a). En outre, vous pouvez utiliser les raccourcis pour copier et coller du texte ou des définitions de transformation complètes d’un fichier de configuration ( [!DNL .cfg]) à un autre.
   * Pour toute transformation que vous définissez, vous pouvez ajouter une ou plusieurs lignes de commentaire au paramètre Commentaires pour décrire la transformation ou ajouter des remarques sur son utilisation. Pour ajouter un commentaire à l’aide de l’outil de données, cliquez avec le bouton droit sur l’ **[!UICONTROL Comments]** étiquette, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

   * Vous pouvez ouvrir la configuration de toute transformation à partir d’une [!DNL Transformation Dependency Map]. Après avoir ouvert la configuration, vous pouvez la modifier et enregistrer vos modifications. Pour plus d’informations sur [!DNL Transformation Dependency Maps]cette solution, voir Outils [de configuration des jeux de](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)données.

   * Une sortie de chaîne vide issue d’une transformation peut remplacer une chaîne non vide dans le champ de sortie.

