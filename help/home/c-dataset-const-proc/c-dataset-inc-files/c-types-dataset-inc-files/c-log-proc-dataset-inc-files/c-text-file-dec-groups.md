---
description: Le traitement des fichiers journaux en tant que sources de journaux requiert la définition d'un décodeur dans le fichier Log Processing Dataset Include pour extraire des champs de données des entrées de journaux.
title: Groupes de décodeur de fichier texte
uuid: 3ff9700b-4f34-4098-8827-6856897bdb28
exl-id: e9f6e02e-7150-455f-96f0-f34d98cc31b7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 0%

---

# Groupes de décodeur de fichier texte{#text-file-decoder-groups}

Le traitement des fichiers journaux en tant que sources de journaux requiert la définition d&#39;un décodeur dans le fichier Log Processing Dataset Include pour extraire des champs de données des entrées de journaux.

La définition de groupes de décodeurs de fichiers texte pour les sources de journaux de fichiers journaux nécessite une connaissance de la structure et du contenu du fichier journal, des données à extraire et des champs dans lesquels ces données sont stockées. Cette section fournit des descriptions de base des paramètres que vous pouvez spécifier pour les décodeurs, mais la manière dont vous utilisez n’importe quel décodeur dépend du fichier journal qui contient vos données source.

Pour plus d’informations sur les exigences de format des sources de journaux de fichiers journaux, voir [Fichiers journaux](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e). Pour obtenir de l’aide sur la définition de décodeurs de fichiers texte, contactez l’Adobe.

Un groupe de décodeurs de fichiers texte peut inclure :

* [Décideurs d&#39;Expression réguliers](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-67aca2c1f008404da7f845a64abec97c)
* [Décodeurs délimités](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-7e0a23decdbc4c75ae750a42446997a6)

## Decoders d&#39;Expression régulière {#section-67aca2c1f008404da7f845a64abec97c}

Un décodeur d’expression classique identifie des modèles de chaînes complexes dans les entrées de journal d’un fichier journal et les extrait sous forme de champs de données. Pour chaque décodeur, le nombre de champs doit être égal au nombre de sous-modèles capturés dans l’expression régulière. La partie de la ligne correspondant au énième sous-modèle capturé est affectée au énième champ de cette ligne.

**Pour ajouter un décodeur d’expression normal à un groupe de décodeurs de fichiers texte**

1. Ouvrez le fichier [!DNL Log Processing Dataset Include] comme décrit dans la section [Modification d&#39;un jeu de données existant Incluez des fichiers](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) et ajoutez un groupe de décodeurs de fichiers texte. Voir l&#39;entrée de tableau [Groupes de décodeurs](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. Cliquez avec le bouton droit **[!UICONTROL Decoders]** sous le nouveau groupe de décodeurs, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.

1. Indiquez les informations suivantes :

   * **Champs :** Liste des champs du fichier journal. Si l&#39;un des champs définis ici doit être transmis à la phase de transformation de la construction du jeu de données, ces champs doivent être répertoriés dans le paramètre Champs de l&#39;un des fichiers [!DNL Log Processing Dataset Include] du jeu de données. Les noms de champ personnalisés doivent commencer par &quot;x-&quot;.

   * **Nom : identifiant** facultatif du décodeur.
   * **Expression régulière :** permet d’extraire les champs souhaités de chaque ligne du fichier.

1. Répétez les étapes 4 et 5 pour tous les autres décodeurs que vous souhaitez ajouter au groupe.
1. Pour enregistrer le fichier [!DNL Log Processing Dataset Include], cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la colonne [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User]. Cliquez sur **[!UICONTROL Save to]** > *&lt; &lt;a2/&quot;*, où le nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données.**[!UICONTROL profile name]**

N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

>[!NOTE]
>
>Un fichier journal donné peut comporter plusieurs décodeurs d’expression réguliers. L’ordre dans lequel vous définissez les décodeurs est important : le premier décodeur à correspondre à une ligne du fichier journal est celui utilisé pour décoder cette ligne.

Cet exemple illustre l’utilisation d’un décodeur d’expression classique pour extraire des champs de données d’un fichier texte délimité par des tabulations. Vous pouvez obtenir le même résultat en définissant un décodeur délimité avec un délimiteur de tabulation.

![](assets/cfg_LogProcessingInclude_RegExpDecoder.png)

Pour plus d&#39;informations sur les décodeurs d&#39;expressions réguliers, y compris la terminologie et la syntaxe, voir [Expressions régulières](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

## Décodeurs délimités {#section-7e0a23decdbc4c75ae750a42446997a6}

Un décodeur délimité décode un fichier journal dont les champs sont délimités par un seul caractère. Le nombre de champs doit correspondre au nombre de colonnes dans le fichier délimité ; toutefois, tous les champs n’ont pas besoin d’être nommés. Si un champ est laissé vide, la colonne est toujours requise dans le fichier journal, mais le décodeur l’ignore.

**Pour ajouter un décodeur délimité à un groupe de décodeurs de fichiers texte**

1. Ouvrez le fichier [!DNL Log Processing Dataset Include] comme décrit dans la section [Modification d&#39;un jeu de données existant Incluez des fichiers](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) et ajoutez un groupe de décodeurs de fichiers texte. Voir l&#39;entrée de tableau [Groupes de décodeurs](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. Cliquez avec le bouton droit **[!UICONTROL Decoders]** sous le nouveau groupe de décodeurs, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Delimited]**.

1. Indiquez les informations suivantes :

   * **Champs :** Liste des champs du fichier journal. Si l&#39;un des champs définis ici doit être transmis à la phase de transformation de la construction du jeu de données, ces champs doivent être répertoriés dans le paramètre Champs de l&#39;un des fichiers [!DNL Log Processing Dataset Include] du jeu de données. Les noms de champ personnalisés doivent commencer par &quot;x-&quot;.

   * **Délimiteur :** caractère utilisé pour séparer les champs du fichier de sortie.

1. Répétez les étapes 4 et 5 pour tous les autres décodeurs que vous souhaitez ajouter au groupe.
1. Pour enregistrer le fichier [!DNL Log Processing Dataset Include], cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, où le nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données.

>[!NOTE]
>
>N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

Cet exemple illustre l’utilisation d’un décodeur délimité pour extraire des champs de données d’un fichier texte délimité par des virgules contenant des données relatives aux séquences vidéo.

![](assets/cfg_LogProcessingInclude_DelimitedDecoder.png)
