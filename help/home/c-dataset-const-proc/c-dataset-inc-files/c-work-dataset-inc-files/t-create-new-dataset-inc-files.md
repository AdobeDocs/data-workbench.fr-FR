---
description: Procédure de création d’un nouveau fichier d’inclusion de jeu de données.
solution: Analytics
title: Création de nouveaux fichiers d’inclusion de jeux de données
topic: Data workbench
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Création de nouveaux fichiers d’inclusion de jeux de données{#creating-new-dataset-include-files}

Procédure de création d’un nouveau fichier d’inclusion de jeu de données.

Vous devez créer un fichier d’inclusion de jeu de données pour effectuer l’une des tâches suivantes de configuration de jeu de données :

* Spécification de nouveaux champs de données à transmettre du traitement du journal à la transformation.
* Définition de transformations qui effectuent l’une des opérations suivantes :

   * Mettez à jour les champs de journal existants.
   * Créez de nouveaux champs à transmettre du traitement du journal à la transformation ou utilisés pour définir des dimensions étendues.

      Pour plus d’informations sur les types de transformation disponibles, voir Transformations des [données](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >Si vous définissez des transformations dans un nouveau fichier d’inclusion de jeux de données, veillez à garder à l’esprit l’ordre des entrées et des sorties. Pour plus d’informations sur l’ordre des transformations, voir [Conventions pour la construction de transformations](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6).

* Création de dimensions étendues. Pour plus d’informations sur les types de dimension disponibles, voir Dimensions [étendues](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez le fichier [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour afficher les fichiers d’inclusion de jeu de données existants.

   * Pour afficher les [!DNL Log Processing Dataset Include] fichiers, cliquez sur **[!UICONTROL Log Processing]**.

   * Pour afficher les [!DNL Transformation Dataset Include] fichiers, cliquez sur **[!UICONTROL Transformation]**.

1. Créez un nouveau [!DNL Log Processing] ou [!DNL Transformation Dataset Include] fichier en procédant de l’une des manières suivantes :

   * Dans la [!DNL User] colonne du répertoire de traitement du journal, cliquez sur **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**. Un fichier nommé [!DNL New Log Processing.cfg] apparaît dans le répertoire.

   * Dans la [!DNL User] colonne du répertoire Transformation, cliquez sur **[!UICONTROL Create]** > **[!UICONTROL New Transformation]**. Un fichier nommé [!DNL New Transformation.cfg] apparaît dans le répertoire.

1. Renommez le nouveau fichier en cliquant avec le bouton droit de la souris sur sa coche dans la [!DNL User] colonne et en saisissant le nouveau nom dans le paramètre Fichier.

   ![Infos sur l’étape](assets/vis_ProfileManager_RenameFile.png)

1. Cliquez avec le bouton droit de la souris sur la coche du fichier renommé, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre de configuration s’affiche.
1. Modifiez les paramètres dans le fichier de configuration selon vos besoins. Pour obtenir la description des paramètres disponibles, reportez-vous à la section Jeu de données [de traitement du journal Inclure les fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) ou Fichier [de données de](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) transformation Inclure les fichiers.
1. Pour enregistrer vos modifications, cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
1. Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;>**[!UICONTROL profile name]***, où nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données. Le retraitement ou la retransformation des données commence après la synchronisation du profil du jeu de données.

   >[!NOTE]
   >
   >N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

Pour modifier un fichier d’inclusion de jeux de données que vous avez créé, voir [Modification de fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)d’inclusion de jeux de données existants.
