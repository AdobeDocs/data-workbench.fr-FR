---
description: Vous pouvez utiliser le paramètre Masqué ou Afficher pour masquer les dimensions étendues afin qu’elles ne s’affichent pas dans le menu des dimensions de Data Workbench.
title: Masquage des dimensions étendues
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
exl-id: 5baccf39-6f3b-40a1-b1c0-a8e5d6a61211
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 1%

---

# Masquage des dimensions étendues{#hiding-extended-dimensions}

{{eol}}

Vous pouvez utiliser le paramètre Masqué ou Afficher pour masquer les dimensions étendues afin qu’elles ne s’affichent pas dans le menu des dimensions de Data Workbench.

Lorsque vous saisissez le paramètre approprié pour l’un ou l’autre paramètre, le nom de la dimension n’est pas répertorié dans le menu de Data Workbench, mais il figure toujours dans le profil et peut être utilisé. Tout utilisateur de Data Workbench peut afficher temporairement les dimensions masquées en définissant le paramètre Afficher tout dans le [!DNL Insight.cfg] sur true.

Pour plus d’informations sur le paramètre Afficher tout, reportez-vous à l’ annexe sur les paramètres de configuration de Data Workbench dans la section *Guide de l’utilisateur de Data Workbench*.

Les sections suivantes décrivent l’utilisation des paramètres Masqué et Afficher pour masquer les dimensions étendues.

* [Masquage des Dimensions étendues à l’aide du paramètre masqué](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Masquage des Dimensions étendues à l’aide du paramètre Afficher](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Masquage des Dimensions étendues à l’aide du paramètre masqué {#section-7167a6f6241a4bc78f2f322e048d65cf}

Le paramètre Masqué est un paramètre facultatif que vous pouvez utiliser lors de la définition de dimensions étendues dans [!DNL Transformation Dataset Configuration] fichiers .

1. Ouvrir [!DNL Transformation Dataset Configuration] fichiers dans lesquels la dimension étendue que vous souhaitez masquer est définie. Voir [Modification de fichiers d’inclusion de jeux de données existants](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Recherchez le paramètre Masqué pour la dimension souhaitée dans la fenêtre de configuration et saisissez *true*.
1. Enregistrez le fichier localement, puis enregistrez-le dans le profil approprié sur le serveur. Voir [Modification de fichiers d’inclusion de jeux de données existants](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

Le jeu de données se transforme, après quoi la dimension étendue n’apparaît pas dans le menu de dimension dans Data Workbench. Pour plus d’informations sur le paramètre Masqué, voir [Dimensions étendues](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

Si vous modifiez le paramètre Masqué , vous devez retransformer le jeu de données pour que la modification soit prise en compte.

## Masquage des Dimensions étendues à l’aide du paramètre Afficher {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

Le paramètre Afficher n’est pas l’un des paramètres disponibles pour définir des dimensions étendues dans [!DNL Transformation Dataset Configuration] fichiers . À la place, le paramètre est défini dans la variable [!DNL .dim] fichiers pour toutes les dimensions dérivées que vous créez. Par conséquent, pour utiliser le paramètre Afficher afin de masquer une dimension étendue, vous devez d’abord créer une dimension dérivée basée sur la dimension étendue, comme décrit dans la procédure suivante :

1. Utilisez un éditeur de texte tel que le Bloc-notes pour créer un fichier vide appelé &lt;*nom de la dimension*>.dim Le nom de fichier doit correspondre au nom de la dimension que vous souhaitez masquer. Par exemple, pour masquer la dimension Page suivante, vous devez créer une [!DNL Next Page.dim] fichier .

1. Ajoutez le texte suivant au fichier :

   * entity = ref : wdata/model/dim/Parent/+name
   * show = bool : false

1. Enregistrez le fichier dans le répertoire Dimensions du profil. Si vous le souhaitez, vous pouvez enregistrer le fichier dans un sous-répertoire.

Lorsque vous utilisez le paramètre Afficher pour masquer une dimension étendue, il n’est pas nécessaire de retransformer votre jeu de données pour que la modification soit prise en compte. Vous pouvez choisir de masquer ou d’afficher la dimension dans votre version locale du profil (c’est-à-dire que vous pouvez enregistrer la variable [!DNL .dim] dans votre dossier User), ou vous pouvez enregistrer la variable [!DNL .dim] sur le serveur pour être utilisé par d’autres utilisateurs du profil.

Vous pouvez également utiliser le paramètre Afficher pour masquer les mesures et les filtres. Pour plus d’informations, reportez-vous au chapitre Configuration des fonctions d’interface et d’analyse de la section *Guide de l’utilisateur de Data Workbench*.
