---
description: Procédure de définition de dimensions étendues.
title: Définition des dimensions étendues
uuid: 25946998-54ca-4595-a2f9-9c593917643a
exl-id: e1664548-e2b4-47bb-8bec-155c16873e08
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 9%

---

# Définition des dimensions étendues{#defining-extended-dimensions}

Procédure de définition de dimensions étendues.

1. Lorsque vous travaillez dans votre profil de jeux de données, ouvrez [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour en afficher le contenu.
1. Ouvrez le fichier [!DNL Transformation.cfg] ou le fichier [!DNL Transformation Dataset Include] dans lequel vous souhaitez définir la dimension étendue.

   * (Recommandé) Pour ouvrir un fichier d’inclusion de dataset, voir [Fichiers d’inclusion de dataset](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

      >[!NOTE]
      >
      >Adobe recommande de définir des dimensions étendues dans un ou plusieurs nouveaux fichiers [!DNL Transformation Dataset Include]. Pour plus d&#39;informations, consultez [Création de nouveaux jeux de données Inclure des fichiers](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e).

   * Pour ouvrir le fichier [!DNL Transformation.cfg], voir [Modification du fichier de configuration de transformation](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Cliquez avec le bouton droit **[!UICONTROL Transformations]** et cliquez sur **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]***.
1. Saisissez les informations appropriées pour votre dimension étendue. Pour obtenir des descriptions des types de transformation et des informations sur leurs paramètres, consultez les sections suivantes :

   * [Dimensions dénombrables](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [Dimensions simples](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [Dimensions multiples-à-multiples](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [Dimensions numériques](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [Dimensions non normalisées](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [Dimensions Heure](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      Pour toute dimension étendue que vous définissez, vous pouvez ajouter une ou plusieurs lignes de commentaire au paramètre Commentaires pour décrire plus en détail la dimension ou ajouter des remarques sur son utilisation. Pour ajouter un commentaire, cliquez avec le bouton droit de la souris sur l&#39;étiquette **[!UICONTROL Comments]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

1. Après avoir défini vos dimensions étendues dans le fichier de configuration, enregistrez le fichier localement et enregistrez-le dans votre profil de données sur le serveur de l’outil de données.
