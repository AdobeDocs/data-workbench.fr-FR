---
description: Vous pouvez définir les transformations de données à appliquer pendant le traitement des journaux ou la phase de transformation de la construction des jeux de données.
title: Définition d’une transformation
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
exl-id: 61ce8093-9e64-419a-bddc-dc2225c0eaab
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 5%

---

# Définition d’une transformation{#defining-a-transformation}

Vous pouvez définir les transformations de données à appliquer pendant le traitement des journaux ou la phase de transformation de la construction des jeux de données.

>[!NOTE]
>
>Adobe recommande de définir des transformations dans les fichiers [!DNL Log Processing] ou [!DNL Transformation Dataset Include] au lieu de [!DNL Log Processing.cfg] ou [!DNL Transformation.cfg].

Les transformations suivantes ne fonctionnent que si elles sont définies dans le fichier [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include] :

* [](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)AppendURII
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [Sources de données ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessionize](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**Pour définir une transformation**

1. Utilisez [!DNL Profile Manager] pour ouvrir le fichier de configuration du jeu de données dans lequel vous souhaitez définir la transformation.

   * (Recommandé) Pour ouvrir un fichier d’inclusion de dataset, voir [Fichiers d’inclusion de dataset](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).
   * Pour ouvrir le fichier [!DNL Log Processing.cfg], voir [Modification du fichier de configuration de traitement du journal](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * Pour ouvrir le fichier [!DNL Transformation.cfg], voir [Modification du fichier de configuration de transformation](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Cliquez avec le bouton droit **[!UICONTROL Transformations]**, puis cliquez sur **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]***.
1. Saisissez les informations appropriées pour votre transformation. Pour obtenir des descriptions des types de transformation et des informations sur leurs paramètres, consultez les sections suivantes :

   * [Transformations standard](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [Transformations URI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [Intégration des données Lookup](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. Après avoir défini votre ou vos transformations dans le fichier de configuration, enregistrez le fichier localement et enregistrez-le dans votre profil de données sur le serveur de l&#39;outil de données.

       Conseils pour la définition et la modification des transformations :
   
   * Lors de la modification de la configuration d&#39;une transformation dans une fenêtre de l&#39;outil de données, vous pouvez utiliser des touches de raccourci pour les fonctions de modification de base, notamment couper (Ctrl+x), copier (Ctrl+c), coller (Ctrl+v), annuler (Ctrl+z), rétablir (Ctrl+Maj+z), sélectionner une section (cliquer+faire glisser) et sélectionner tout (Ctrl+a). En outre, vous pouvez utiliser les raccourcis pour copier et coller du texte ou des définitions de transformation entières d&#39;un fichier de configuration ( [!DNL .cfg]) à un autre.
   * Pour toute transformation que vous définissez, vous pouvez ajouter une ou plusieurs lignes de commentaire au paramètre Commentaires pour décrire la transformation ou ajouter des remarques sur son utilisation. Pour ajouter un commentaire à l’aide de l’outil de données, cliquez avec le bouton droit de la souris sur l’étiquette **[!UICONTROL Comments]**, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

   * Vous pouvez ouvrir la configuration de toute transformation à partir d&#39;un [!DNL Transformation Dependency Map]. Après avoir ouvert la configuration, vous pouvez la modifier et enregistrer vos modifications. Pour plus d&#39;informations sur [!DNL Transformation Dependency Maps], voir [Outils de configuration des jeux de données](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

   * Une sortie de chaîne vide issue d’une transformation peut remplacer une chaîne non vide dans le champ de sortie.
