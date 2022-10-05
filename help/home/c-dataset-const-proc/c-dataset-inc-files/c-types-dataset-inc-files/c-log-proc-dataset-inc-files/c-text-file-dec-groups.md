---
description: Le traitement des fichiers journaux en tant que sources de journaux nécessite la définition d’un décodeur dans le fichier d’inclusion du jeu de données de traitement du journal pour extraire les champs de données des entrées de journal.
title: Groupes de décodeur de fichier texte
uuid: 3ff9700b-4f34-4098-8827-6856897bdb28
exl-id: e9f6e02e-7150-455f-96f0-f34d98cc31b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 0%

---

# Groupes de décodeur de fichier texte{#text-file-decoder-groups}

{{eol}}

Le traitement des fichiers journaux en tant que sources de journaux nécessite la définition d’un décodeur dans le fichier d’inclusion du jeu de données de traitement du journal pour extraire les champs de données des entrées de journal.

La définition de groupes de décodeur de fichier texte pour les sources de journaux de fichiers journaux nécessite une connaissance de la structure et du contenu du fichier journal, des données à extraire et des champs dans lesquels ces données sont stockées. Cette section fournit des descriptions de base des paramètres que vous pouvez spécifier pour les décodeurs, mais la manière dont vous utilisez un décodeur dépend du fichier journal contenant les données source.

Pour plus d’informations sur les exigences de format des sources de journaux de fichiers journaux, voir [Fichiers journaux](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e). Pour obtenir de l’aide sur la définition des décodeurs de fichiers texte, contactez Adobe.

Un groupe de décodeur de fichier texte peut inclure :

* [Décodeurs d’expression régulière](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-67aca2c1f008404da7f845a64abec97c)
* [Décodeurs délimités](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-7e0a23decdbc4c75ae750a42446997a6)

## Décodeurs d’expression régulière {#section-67aca2c1f008404da7f845a64abec97c}

Un décodeur d’expression régulière identifie les modèles de chaîne complexes dans les entrées de journal d’un fichier journal et extrait ces modèles en tant que champs de données. Pour chaque décodeur, le nombre de champs doit être égal au nombre de sous-modèles capturés dans l’expression régulière. La partie de la ligne correspondant au sous-modèle de capture nth est affectée au énième champ de cette ligne.

**Pour ajouter un décodeur d’expression régulière à un groupe de décodeur de fichier texte**

1. Ouvrez le [!DNL Log Processing Dataset Include] comme décrit dans la section [Modification de fichiers d’inclusion de jeux de données existants](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) et ajoutez un groupe de décodeur de fichier texte. Voir l’entrée du tableau [Groupes de décodeur](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. Clic droit **[!UICONTROL Decoders]** sous le groupe de décodeur nouvellement créé, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.

1. Indiquez les informations suivantes :

   * **Champs :** Liste des champs du fichier journal. Si l’un des champs définis ici doit être transmis à la phase de transformation de la construction du jeu de données, ces champs doivent être répertoriés dans le paramètre Champs de l’un des [!DNL Log Processing Dataset Include] fichiers du jeu de données. Les noms de champ personnalisés doivent commencer par &quot;x-&quot;.

   * **Nom :** Identifiant facultatif du décodeur.
   * **Expression régulière :** Utilisé pour extraire les champs de votre choix de chaque ligne du fichier.

1. Répétez les étapes 4 et 5 pour tout autre décodeur à ajouter au groupe.
1. Pour enregistrer le [!DNL Log Processing Dataset Include] fichier, clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la variable [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL User] colonne . Cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, où nom du profil est le nom du profil du jeu de données ou du profil hérité auquel appartient le fichier d’inclusion du jeu de données.

N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.

>[!NOTE]
>
>Un fichier journal donné peut comporter plusieurs décodeurs d’expression régulière. L’ordre dans lequel vous définissez les décodeurs est important : le premier décodeur qui correspond à une ligne du fichier journal est celui utilisé pour décoder cette ligne.

Cet exemple illustre l’utilisation d’un décodeur d’expression régulière pour extraire des champs de données d’un fichier texte délimité par des tabulations. Vous pouvez obtenir le même résultat en définissant un décodeur délimité avec un délimiteur de tabulation.

![](assets/cfg_LogProcessingInclude_RegExpDecoder.png)

Pour plus d’informations sur les décodeurs d’expression régulière, y compris la terminologie et la syntaxe, voir [Expressions régulières](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

## Décodeurs délimités {#section-7e0a23decdbc4c75ae750a42446997a6}

Un décodeur délimité décode un fichier journal dont les champs sont délimités par un seul caractère. Le nombre de champs doit correspondre au nombre de colonnes dans le fichier délimité ; toutefois, tous les champs n’ont pas besoin d’être nommés. Si un champ n’est pas renseigné, la colonne est toujours requise dans le fichier journal, mais le décodeur l’ignore.

**Pour ajouter un décodeur délimité à un groupe de décodeur de fichier texte**

1. Ouvrez le [!DNL Log Processing Dataset Include] comme décrit dans la section [Modification de fichiers d’inclusion de jeux de données existants](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) et ajoutez un groupe de décodeur de fichier texte. Voir l’entrée du tableau [Groupes de décodeur](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. Clic droit **[!UICONTROL Decoders]** sous le groupe de décodeur nouvellement créé, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Delimited]**.

1. Indiquez les informations suivantes :

   * **Champs :** Liste des champs du fichier journal. Si l’un des champs définis ici doit être transmis à la phase de transformation de la construction du jeu de données, ces champs doivent être répertoriés dans le paramètre Champs de l’un des [!DNL Log Processing Dataset Include] fichiers du jeu de données. Les noms de champ personnalisés doivent commencer par &quot;x-&quot;.

   * **Délimiteur :** Caractère utilisé pour séparer les champs dans le fichier de sortie.

1. Répétez les étapes 4 et 5 pour tout autre décodeur à ajouter au groupe.
1. Pour enregistrer le [!DNL Log Processing Dataset Include] fichier, clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la variable [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, où nom du profil est le nom du profil du jeu de données ou du profil hérité auquel appartient le fichier d’inclusion du jeu de données.

>[!NOTE]
>
>N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.

Cet exemple illustre l’utilisation d’un décodeur délimité pour extraire des champs de données d’un fichier texte délimité par des virgules contenant des données relatives aux films.

![](assets/cfg_LogProcessingInclude_DelimitedDecoder.png)
