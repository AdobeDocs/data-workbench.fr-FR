---
description: Procédure de création d’un fichier d’inclusion de jeu de données.
title: Création de nouveaux fichiers d’inclusion de jeux de données
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
exl-id: 8a7b343d-b695-41aa-b465-8c5cd68d6ef7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# Création de nouveaux fichiers d’inclusion de jeux de données{#creating-new-dataset-include-files}

{{eol}}

Procédure de création d’un fichier d’inclusion de jeu de données.

Vous devez créer un fichier d’inclusion de jeu de données pour effectuer l’une des tâches de configuration de jeu de données suivantes :

* Spécification de nouveaux champs de données à transmettre du traitement du journal à la transformation.
* Définir des transformations qui effectuent l’une des opérations suivantes :

   * Mettez à jour les champs de journal existants.
   * Permet de générer de nouveaux champs qui doivent être transmis du traitement des logs à la transformation ou qui sont utilisés pour définir des dimensions étendues.

      Pour plus d’informations sur les types de transformation disponibles, voir [Transformations de données](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >Si vous définissez des transformations dans un nouveau fichier d’inclusion de jeux de données, veillez à garder à l’esprit l’ordre des entrées et des sorties. Pour plus d’informations sur l’ordre des transformations, voir [Conventions de construction des transformations](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6).

* Création de dimensions étendues. Pour plus d’informations sur les types de dimension disponibles, voir [Dimensions étendues](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez la variable [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour afficher les fichiers d’inclusion de jeux de données existants.

   * Pour afficher la variable [!DNL Log Processing Dataset Include] fichiers, cliquez sur **[!UICONTROL Log Processing]**.

   * Pour afficher la variable [!DNL Transformation Dataset Include] fichiers, cliquez sur **[!UICONTROL Transformation]**.

1. Créer [!DNL Log Processing] ou [!DNL Transformation Dataset Include] en effectuant l’une des étapes suivantes :

   * Dans le [!DNL User] pour le répertoire de traitement du journal, cliquez sur **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**. Un fichier nommé [!DNL New Log Processing.cfg] apparaît dans le répertoire .

   * Dans le [!DNL User] pour le répertoire de transformation, cliquez sur **[!UICONTROL Create]** > **[!UICONTROL New Transformation]**. Un fichier nommé [!DNL New Transformation.cfg] apparaît dans le répertoire .

1. Renommez le nouveau fichier en cochant avec le bouton droit de la souris dans la section [!DNL User] et saisissez le nouveau nom dans le paramètre Fichier .

   ![Infos sur l’étape](assets/vis_ProfileManager_RenameFile.png)

1. Cliquez avec le bouton droit de la souris sur la coche du fichier renommé, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre de configuration s’affiche.
1. Modifiez les paramètres du fichier de configuration selon les besoins. Voir [Fichiers d’inclusion de jeux de données de traitement journaux](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) ou [Fichiers d’inclusion de jeux de données de transformation](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) pour obtenir une description des paramètres disponibles.
1. Pour enregistrer vos modifications, cliquez avec le bouton droit de la souris **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Pour que les modifications apportées localement prennent effet, dans la variable [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, où nom du profil est le nom du profil du jeu de données ou du profil hérité auquel appartient le fichier d’inclusion du jeu de données. Le retraitement ou la retransformation des données commence après la synchronisation du profil du jeu de données.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.

Pour modifier un fichier d’inclusion de jeu de données que vous avez créé, voir [Modification de fichiers d’inclusion de jeux de données existants](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).
