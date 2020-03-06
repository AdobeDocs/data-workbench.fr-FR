---
description: Informations sur l’ajout, la suppression ou la copie d’une condition.
solution: Analytics
title: Utilisation Des Conditions
topic: Data workbench
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Utilisation Des Conditions{#working-with-conditions}

Informations sur l’ajout, la suppression ou la copie d’une condition.

* [Pour ajouter une condition à un fichier de configuration de jeu de données](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [Pour supprimer une condition d’un fichier de configuration d’ensemble de données](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [Pour copier une condition](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## Pour ajouter une condition à un fichier de configuration de jeu de données {#section-3e2a34db047b462585502f69722f6511}

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez le fichier [!DNL Profile Manager] de configuration de jeu de données que vous souhaitez modifier.

   * Pour ouvrir le [!DNL Log Processing.cfg] fichier, voir [Modification du fichier](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)de configuration du traitement du journal.

   * Pour ouvrir le [!DNL Transformation.cfg] fichier, voir [Modification du fichier](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)de configuration de transformation.

   * Pour ouvrir un [!DNL Dataset Include] fichier, voir [Jeu de données - Fichiers](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)inclus.

1. Dans le fichier de configuration du jeu de données, recherchez le paramètre Condition ou Condition d&#39;entrée dans le journal que vous souhaitez définir.
1. Cliquez avec le bouton droit de la souris sur le paramètre et cliquez sur **[!UICONTROL Add new]**. Choisissez l’un des types de condition suivants :

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. Modifiez les paramètres de la condition selon vos besoins. Pour la description des paramètres de chaque condition, voir la section appropriée de la présente annexe.
1. Pour enregistrer vos modifications, cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement soient prises en compte, cliquez avec le [!DNL Profile Manager,] bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, où nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel le fichier appartient.

   >[!NOTE]
   >
   >N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

## Pour supprimer une condition d’un fichier de configuration d’ensemble de données {#section-677270f93f1648c3a268ca2aea7d4540}

1. Cliquez avec le bouton droit de la souris sur le nom de la condition ou le numéro correspondant à la condition à supprimer.
1. Cliquez sur **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, où nombre correspond au nombre correspondant à la condition à supprimer.

## Pour copier une condition {#section-00617bcf2c274f428686b2ec7f2d1db8}

Vous pouvez copier une condition d’un emplacement vers un autre dans le même fichier ou copier une condition d’un fichier de configuration de jeu de données vers un autre.

1. Cliquez avec le bouton droit de la souris sur le nom de la condition ou le numéro correspondant à la condition à copier, puis cliquez sur **[!UICONTROL Copy]**.
1. Cliquez avec le bouton droit de la souris sur le nom ou le numéro de la condition sous laquelle vous souhaitez placer la condition copiée, puis cliquez sur **[!UICONTROL Paste]**.

