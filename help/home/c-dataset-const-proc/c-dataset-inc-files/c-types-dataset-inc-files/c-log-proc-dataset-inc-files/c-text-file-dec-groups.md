---
description: Le traitement des fichiers journaux en tant que sources de journaux requiert la définition d’un décodeur dans le fichier Log Processing Data Set Include pour extraire des champs de données des entrées de journaux.
solution: Analytics
title: Groupes de décodeurs de fichiers texte
topic: Data workbench
uuid: 3ff9700b-4f34-4098-8827-6856897bdb28
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Groupes de décodeurs de fichiers texte{#text-file-decoder-groups}

Le traitement des fichiers journaux en tant que sources de journaux requiert la définition d’un décodeur dans le fichier Log Processing Data Set Include pour extraire des champs de données des entrées de journaux.

La définition de groupes de décodeurs de fichiers texte pour les sources de journaux de fichiers journaux nécessite une connaissance de la structure et du contenu du fichier journal, des données à extraire et des champs dans lesquels ces données sont stockées. Cette section fournit des descriptions de base des paramètres que vous pouvez spécifier pour les décodeurs, mais la manière dont vous utilisez n’importe quel décodeur dépend du fichier journal contenant vos données source.

Pour plus d’informations sur la configuration requise pour les sources de fichiers journaux, voir Fichiers [](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)journaux. Pour obtenir de l’aide sur la définition de décodeurs de fichiers texte, contactez Adobe.

Un groupe de décodeurs de fichiers texte peut inclure :

* [Décodeurs d’expression régulière](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-67aca2c1f008404da7f845a64abec97c)
* [Décodeurs délimités](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-7e0a23decdbc4c75ae750a42446997a6)

## Décodeurs d’expression régulière {#section-67aca2c1f008404da7f845a64abec97c}

Un décodeur d’expression régulière identifie des modèles de chaîne complexes dans les entrées de journal d’un fichier journal et les extrait sous forme de champs de données. Pour chaque décodeur, le nombre de champs doit être égal au nombre de sous-modèles capturés dans l’expression régulière. La partie de la ligne correspondant au sous-modèle capturant la nth est affectée au énième champ de cette ligne.

**Pour ajouter un décodeur d’expression régulière à un groupe de décodeurs de fichiers texte**

1. Ouvrez le [!DNL Log Processing Dataset Include] fichier comme décrit dans la section [Modification d’un jeu de données existant - Inclure des fichiers](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) et ajoutez un groupe de décodeurs de fichiers texte. Voir l’entrée de tableau Groupes [de décodeur](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. Cliquez avec le bouton droit **[!UICONTROL Decoders]** sous le nouveau groupe de décodeurs, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.

1. Spécifiez les informations suivantes :

   * **Champs :** Liste des champs du fichier journal. Si l&#39;un des champs définis ici doit être transmis à la phase de transformation de la construction du jeu de données, ces champs doivent être répertoriés dans le paramètre Champs de l&#39;un des [!DNL Log Processing Dataset Include] fichiers du jeu de données. Les noms de champ personnalisés doivent commencer par &quot;x-&quot;.

   * **Nom :** Identificateur facultatif du décodeur.
   * **Expression régulière :** Permet d’extraire les champs souhaités de chaque ligne du fichier.

1. Répétez les étapes 4 et 5 pour tous les autres décodeurs que vous souhaitez ajouter au groupe.
1. Pour enregistrer le [!DNL Log Processing Dataset Include] fichier, cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne. Cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, où nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d’inclusion du jeu de données.

N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

>[!NOTE]
>
>Un fichier journal donné peut comporter plusieurs décodeurs d’expression régulière. L’ordre dans lequel vous définissez les décodeurs est important : le premier décodeur à correspondre à une ligne du fichier journal est celui utilisé pour décoder cette ligne.

Cet exemple illustre l’utilisation d’un décodeur d’expression régulière pour extraire des champs de données d’un fichier texte délimité par des tabulations. Vous pouvez obtenir le même résultat en définissant un décodeur délimité avec un délimiteur de tabulation.

![](assets/cfg_LogProcessingInclude_RegExpDecoder.png)

Pour plus d’informations sur les décodeurs d’expression régulière, y compris la terminologie et la syntaxe, voir Expressions [](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)régulières.

## Décodeurs délimités {#section-7e0a23decdbc4c75ae750a42446997a6}

Un décodeur délimité décode un fichier journal dont les champs sont délimités par un seul caractère. Le nombre de champs doit correspondre au nombre de colonnes dans le fichier délimité ; toutefois, tous les champs n’ont pas besoin d’être nommés. Si un champ n’est pas renseigné, la colonne est toujours requise dans le fichier journal, mais le décodeur l’ignore.

**Pour ajouter un décodeur délimité à un groupe de décodeurs de fichiers texte**

1. Ouvrez le [!DNL Log Processing Dataset Include] fichier comme décrit dans la section [Modification d’un jeu de données existant - Inclure des fichiers](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) et ajoutez un groupe de décodeurs de fichiers texte. Voir l’entrée de tableau Groupes [de décodeur](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. Cliquez avec le bouton droit **[!UICONTROL Decoders]** sous le nouveau groupe de décodeurs, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Delimited]**.

1. Spécifiez les informations suivantes :

   * **Champs :** Liste des champs du fichier journal. Si l&#39;un des champs définis ici doit être transmis à la phase de transformation de la construction du jeu de données, ces champs doivent être répertoriés dans le paramètre Champs de l&#39;un des [!DNL Log Processing Dataset Include] fichiers du jeu de données. Les noms de champ personnalisés doivent commencer par &quot;x-&quot;.

   * **Délimiteur :** Caractère utilisé pour séparer les champs du fichier de sortie.

1. Répétez les étapes 4 et 5 pour tous les autres décodeurs que vous souhaitez ajouter au groupe.
1. Pour enregistrer le [!DNL Log Processing Dataset Include] fichier, cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;>**[!UICONTROL profile name]***, où nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données.

>[!NOTE]
>
>N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

Cet exemple illustre l’utilisation d’un décodeur délimité pour extraire des champs de données d’un fichier texte délimité par des virgules contenant des données sur des films.

![](assets/cfg_LogProcessingInclude_DelimitedDecoder.png)

