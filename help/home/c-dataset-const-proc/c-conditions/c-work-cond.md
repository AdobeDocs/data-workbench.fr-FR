---
description: Informations sur l’ajout, la suppression ou la copie d’une condition.
title: Travail avec les conditions
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
exl-id: 0792b308-aa0b-4741-be0c-4f7cc28f3e09
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# Travail avec les conditions{#working-with-conditions}

Informations sur l’ajout, la suppression ou la copie d’une condition.

* [Pour ajouter une condition à un fichier de configuration de jeu de données](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [Pour supprimer une condition d’un fichier de configuration de jeu de données](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [Pour copier une condition](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## Pour ajouter une condition à un fichier de configuration de jeu de données {#section-3e2a34db047b462585502f69722f6511}

1. Lorsque vous travaillez dans votre profil de jeu de données, utilisez [!DNL Profile Manager] pour ouvrir le fichier de configuration de jeu de données que vous souhaitez modifier.

   * Pour ouvrir le fichier [!DNL Log Processing.cfg], voir [Modification du fichier de configuration de traitement du journal](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * Pour ouvrir le fichier [!DNL Transformation.cfg], voir [Modification du fichier de configuration de transformation](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

   * Pour ouvrir un fichier [!DNL Dataset Include], voir [Fichiers d’inclusion de jeux de données](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Dans le fichier de configuration du jeu de données, recherchez le paramètre Condition ou condition d’entrée du journal que vous souhaitez définir.
1. Cliquez avec le bouton droit sur le paramètre et cliquez sur **[!UICONTROL Add new]**. Sélectionnez l’un des types de conditions suivants :

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. Modifiez les paramètres de la condition selon vos besoins. Pour obtenir une description des paramètres de chaque condition, reportez-vous à la section correspondante de cette annexe.
1. Pour enregistrer vos modifications, cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la balise [!DNL Profile Manager,], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, où le nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel le fichier appartient.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.

## Pour supprimer une condition d’un fichier de configuration de jeu de données {#section-677270f93f1648c3a268ca2aea7d4540}

1. Cliquez avec le bouton droit de la souris sur le nom de la condition ou le numéro correspondant à la condition que vous souhaitez supprimer.
1. Cliquez sur **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, où number correspond au nombre correspondant à la condition que vous souhaitez supprimer.

## Pour copier une condition {#section-00617bcf2c274f428686b2ec7f2d1db8}

Vous pouvez copier une condition d’un emplacement vers un autre dans le même fichier ou copier une condition d’un fichier de configuration de jeu de données vers un autre.

1. Cliquez avec le bouton droit sur le nom de la condition ou sur le numéro correspondant à la condition que vous souhaitez copier, puis cliquez sur **[!UICONTROL Copy]**.
1. Cliquez avec le bouton droit de la souris sur le nom ou le numéro de la condition sous laquelle vous souhaitez placer la condition copiée, puis cliquez sur **[!UICONTROL Paste]**.
