---
description: Vous pouvez utiliser le paramètre Masqué ou Afficher pour masquer les dimensions étendues afin qu’elles ne s’affichent pas dans le menu de dimension dans l’outil de données.
title: Masquage des dimensions étendues
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
exl-id: 5baccf39-6f3b-40a1-b1c0-a8e5d6a61211
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 1%

---

# Masquage des dimensions étendues{#hiding-extended-dimensions}

Vous pouvez utiliser le paramètre Masqué ou Afficher pour masquer les dimensions étendues afin qu’elles ne s’affichent pas dans le menu de dimension dans l’outil de données.

Lorsque vous saisissez le paramètre approprié pour l’un ou l’autre paramètre, le nom de la dimension n’est pas répertorié dans le menu des outils de données, mais il est toujours dans le profil et peut être utilisé. Tout utilisateur de l’outil de données peut afficher temporairement les dimensions masquées en définissant le paramètre Tout afficher dans le fichier [!DNL Insight.cfg] sur true.

Pour plus d’informations sur le paramètre Afficher tout, voir l’annexe relative aux paramètres de configuration des outils de données dans le *Guide de l’utilisateur Data Workbench*.

Les sections suivantes décrivent comment utiliser les paramètres Masqué et Afficher pour masquer les dimensions étendues.

* [Masquage des Dimensions étendues à l’aide du paramètre masqué](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Masquage des Dimensions étendues à l’aide du paramètre Afficher](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Masquage des Dimensions étendues à l’aide du paramètre masqué {#section-7167a6f6241a4bc78f2f322e048d65cf}

Le paramètre Masqué est un paramètre facultatif que vous pouvez utiliser lors de la définition de dimensions étendues dans des fichiers [!DNL Transformation Dataset Configuration].

1. Ouvrez les fichiers [!DNL Transformation Dataset Configuration] dans lesquels la dimension étendue que vous souhaitez masquer est définie. Voir [Modification d&#39;un jeu de données existant : Inclure des fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Recherchez le paramètre Masqué pour la dimension souhaitée dans la fenêtre de configuration et saisissez *true*.
1. Enregistrez le fichier localement, puis enregistrez-le au profil approprié sur le serveur. Voir [Modification d&#39;un jeu de données existant : Inclure des fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

Le jeu de données se transforme, après quoi la dimension étendue n’apparaît plus dans le menu de dimension dans les outils de données. Pour plus d’informations sur le paramètre Masqué, voir [Dimensions étendues](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

Si vous modifiez le paramètre Masqué, vous devez retransformer le jeu de données pour que la modification soit prise en compte.

## Masquage des Dimensions étendues à l’aide du paramètre Afficher {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

Le paramètre Afficher n&#39;est pas l&#39;un des paramètres disponibles pour la définition de dimensions étendues dans des fichiers [!DNL Transformation Dataset Configuration]. Le paramètre est à la place défini dans les fichiers [!DNL .dim] pour toutes les dimensions dérivées que vous créez. Par conséquent, pour utiliser le paramètre Afficher pour masquer une dimension étendue, vous devez d’abord créer une dimension dérivée basée sur la dimension étendue, comme décrit dans la procédure suivante :

1. Utilisez un éditeur de texte tel que Notepad pour créer un fichier vide intitulé &quot;a0/>nom de dimension *.dim. Le nom du fichier doit correspondre au nom de la dimension que vous souhaitez masquer.* Par exemple, pour masquer la dimension Page suivante, vous devez créer un fichier [!DNL Next Page.dim].

1. Ajoutez le texte suivant dans le fichier :

   * entity = ref : wdata/model/dim/Parent/+name
   * show = bool : false

1. Enregistrez le fichier dans le répertoire des Dimensions du profil. Vous pouvez enregistrer le fichier dans un sous-répertoire si vous le souhaitez.

Lorsque vous utilisez le paramètre Afficher pour masquer une dimension étendue, il n’est pas nécessaire de retransformer votre jeu de données pour que la modification prenne effet. Vous pouvez choisir de masquer ou d&#39;afficher la dimension dans votre version locale du profil (c&#39;est-à-dire que vous pouvez enregistrer le fichier [!DNL .dim] dans votre dossier Utilisateur), ou vous pouvez enregistrer le fichier [!DNL .dim] sur le serveur pour l&#39;utiliser par d&#39;autres utilisateurs du profil.

Vous pouvez également utiliser le paramètre Afficher pour masquer les mesures et les filtres. Pour plus d&#39;informations, consultez le chapitre Configuration des fonctionnalités d&#39;interface et d&#39;Analyse du *Guide de l&#39;utilisateur Data Workbench*.
