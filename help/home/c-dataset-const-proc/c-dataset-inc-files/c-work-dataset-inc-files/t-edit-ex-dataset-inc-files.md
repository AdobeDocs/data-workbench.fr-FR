---
description: Les étapes de modification d’un jeu de données existant incluent des fichiers.
title: Modification des fichiers d’inclusion de jeux de données existants
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# Modification des fichiers d’inclusion de jeux de données existants{#editing-existing-dataset-include-files}

{{eol}}

Les étapes de modification d’un jeu de données existant incluent des fichiers.

Vous ouvrez un fichier d’inclusion de jeu de données existant à l’aide de la variable [!DNL Profile Manager] dans data workbench.

Pour plus d’informations sur l’ouverture et l’utilisation de la variable [!DNL Profile Manager], reportez-vous à la section *Guide de l’utilisateur de Data Workbench*.

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez la variable [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour afficher le contenu du répertoire.

   * Pour ouvrir une [!DNL Log Processing Dataset Include] fichier, cliquez sur **[!UICONTROL Log Processing]** pour afficher le contenu du répertoire.

   * Pour ouvrir une [!DNL Transformation Dataset Include] fichier, cliquez sur **[!UICONTROL Transformation]** pour afficher le contenu du répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche en regard du fichier d’inclusion de jeu de données souhaité, puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .
1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre de configuration s’affiche.

   Vous pouvez également ouvrir un fichier d’inclusion de jeux de données à partir d’un [!DNL Transformation Dependency Maps]. Pour plus d’informations sur [!DNL Transformation Dependency Maps], voir [Retraitement et retransformation](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Modifiez les paramètres du fichier de configuration selon les besoins. Voir [Fichiers d’inclusion de jeux de données de traitement journaux](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) ou [Fichiers d’inclusion de jeux de données de transformation](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) pour obtenir des descriptions des paramètres.

   Lors de la modification d’un fichier d’inclusion de jeu de données dans une fenêtre Data Workbench, vous pouvez utiliser des raccourcis clavier pour les fonctions d’édition de base, notamment couper (Ctrl+x ), copier (Ctrl+c), coller (Ctrl+v ), annuler (Ctrl+z ), rétablir (Ctrl+Maj+z ), sélectionner une section (cliquer+glisser) et tout sélectionner (Ctrl+a ). En outre, vous pouvez utiliser les raccourcis pour copier et coller du texte d’un fichier de configuration ( [!DNL .cfg]) à un autre.

1. Pour enregistrer vos modifications, cliquez avec le bouton droit de la souris **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Pour que les modifications apportées localement prennent effet, dans la variable [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, où nom du profil est le nom du profil du jeu de données ou du profil hérité auquel appartient le fichier d’inclusion du jeu de données. Le retraitement ou la retransformation des données commence après la synchronisation du profil du jeu de données.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.
