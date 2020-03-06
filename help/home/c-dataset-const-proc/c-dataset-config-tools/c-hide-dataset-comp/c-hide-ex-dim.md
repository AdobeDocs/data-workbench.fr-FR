---
description: Vous pouvez utiliser le paramètre Masqué ou Afficher pour masquer les dimensions étendues afin qu’elles ne s’affichent pas dans le menu des dimensions de l’outil de données.
solution: Analytics
title: Masquage des dimensions étendues
topic: Data workbench
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Masquage des dimensions étendues{#hiding-extended-dimensions}

Vous pouvez utiliser le paramètre Masqué ou Afficher pour masquer les dimensions étendues afin qu’elles ne s’affichent pas dans le menu des dimensions de l’outil de données.

Lorsque vous saisissez le paramètre approprié pour l’un ou l’autre paramètre, le nom de la dimension n’est pas répertorié dans le menu de l’outil de données, mais il figure toujours dans le profil et peut être utilisé. Tout utilisateur de l’outil de données peut afficher temporairement les dimensions masquées en définissant le paramètre Tout afficher dans le [!DNL Insight.cfg] fichier sur true.

Pour plus d’informations sur le paramètre Tout afficher, voir l’annexe sur les paramètres de configuration des outils de données dans le Guide *de l’utilisateur des outils de* données.

Les sections suivantes décrivent l’utilisation des paramètres Masqué et Afficher pour masquer les dimensions étendues.

* [Masquage des dimensions étendues à l’aide du paramètre masqué](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Masquage des dimensions étendues à l’aide du paramètre Afficher](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Masquage des dimensions étendues à l’aide du paramètre masqué {#section-7167a6f6241a4bc78f2f322e048d65cf}

Le paramètre Masqué est un paramètre facultatif que vous pouvez utiliser lors de la définition de dimensions étendues dans [!DNL Transformation Dataset Configuration] des fichiers.

1. Ouvrez [!DNL Transformation Dataset Configuration] des fichiers dans lesquels la dimension étendue que vous souhaitez masquer est définie. Voir [Modification d’un jeu de données existant : Inclure des fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Recherchez le paramètre Masqué pour la dimension souhaitée dans la fenêtre de configuration et saisissez *true*.
1. Enregistrez le fichier localement, puis enregistrez-le dans le profil approprié sur le serveur. Voir [Modification d’un jeu de données existant : Inclure des fichiers](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

Le jeu de données se transforme, après quoi la dimension étendue n’apparaît pas dans le menu de dimension dans l’outil de données. Pour plus d’informations sur le paramètre Masqué, voir Dimensions [étendues](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

Si vous modifiez le paramètre Masqué, vous devez retransformer le jeu de données pour que la modification soit prise en compte.

## Masquage des dimensions étendues à l’aide du paramètre Afficher {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

Le paramètre Afficher n’est pas l’un des paramètres disponibles pour la définition de dimensions étendues dans [!DNL Transformation Dataset Configuration] des fichiers. Le paramètre est défini dans les [!DNL .dim] fichiers pour toutes les dimensions dérivées que vous créez. Par conséquent, pour utiliser le paramètre Afficher pour masquer une dimension étendue, vous devez d’abord créer une dimension dérivée basée sur la dimension étendue, comme décrit dans la procédure suivante :

1. Utilisez un éditeur de texte tel que le Bloc-notes pour créer un fichier vide intitulé &lt;nom *de la* dimension>.dim. Le nom du fichier doit correspondre au nom de la dimension à masquer. Par exemple, pour masquer la dimension Page suivante, vous devez créer un [!DNL Next Page.dim] fichier.

1. Ajoutez le texte suivant au fichier :

   * entity = ref : wdata/model/dim/Parent/+name
   * show = bool : false

1. Enregistrez le fichier dans le répertoire Dimensions du profil. Vous pouvez enregistrer le fichier dans un sous-répertoire, le cas échéant.

Lorsque vous utilisez le paramètre Afficher pour masquer une dimension étendue, vous n’avez pas à retransformer votre jeu de données pour que la modification soit prise en compte. Vous pouvez choisir de masquer ou d’afficher la dimension dans votre version locale du profil (c’est-à-dire que vous pouvez enregistrer le [!DNL .dim] fichier dans votre dossier Utilisateur), ou vous pouvez enregistrer le [!DNL .dim] fichier sur le serveur pour l’utiliser par d’autres utilisateurs du profil.

Vous pouvez également utiliser le paramètre Afficher pour masquer les mesures et les filtres. Pour plus d’informations, voir le chapitre Configuration des fonctionnalités d’interface et d’analyse du Guide *de l’utilisateur des outils de* données.
