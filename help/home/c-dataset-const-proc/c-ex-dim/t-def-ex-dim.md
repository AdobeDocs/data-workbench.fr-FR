---
description: Cette section décrit la procédure à suivre pour définir des dimensions étendues.
solution: Analytics
title: Définition de dimensions étendues
topic: Data workbench
uuid: 25946998-54ca-4595-a2f9-9c593917643a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Définition de dimensions étendues{#defining-extended-dimensions}

Cette section décrit la procédure à suivre pour définir des dimensions étendues.

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez le fichier [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour en afficher le contenu.
1. Ouvrez le [!DNL Transformation.cfg] fichier ou le [!DNL Transformation Dataset Include] fichier dans lequel vous souhaitez définir la dimension étendue.

   * (Recommandé) Pour ouvrir un fichier d’inclusion de jeu de données, voir Fichiers [inclus dans le jeu de](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)données.

      >[!NOTE]
      >
      >Adobe recommande de définir des dimensions étendues dans un ou plusieurs nouveaux [!DNL Transformation Dataset Include] fichiers. Pour plus d’informations, voir [Création de nouveaux fichiers](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e)d’inclusion de jeux de données.

   * Pour ouvrir le [!DNL Transformation.cfg] fichier, voir [Modification du fichier](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)de configuration de transformation.

1. Cliquez avec le bouton droit de la souris **[!UICONTROL Transformations]** , puis cliquez sur **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]**>*.
1. Saisissez les informations appropriées pour votre dimension étendue. Pour obtenir des descriptions des types de transformation et des informations sur leurs paramètres, consultez les sections suivantes :

   * [Dimensions dénombrables](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [Dimensions simples](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [Dimensions multiples](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [Dimensions numériques](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [Dimensions Denormal](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [Dimensions Heure](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      Pour toute dimension étendue que vous définissez, vous pouvez ajouter une ou plusieurs lignes de commentaire au paramètre Commentaires afin de décrire plus en détail la dimension ou d’ajouter des remarques sur son utilisation. Pour ajouter un commentaire, cliquez avec le bouton droit de la souris sur l’ **[!UICONTROL Comments]** étiquette et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

1. Après avoir défini vos dimensions étendues dans le fichier de configuration, enregistrez le fichier localement et enregistrez-le dans votre profil de jeu de données sur le serveur de l’outil de données.
