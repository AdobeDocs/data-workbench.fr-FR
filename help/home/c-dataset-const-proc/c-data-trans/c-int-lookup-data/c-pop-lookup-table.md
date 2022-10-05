---
description: Si vous utilisez les transformations Catégorisation ou FlatFileLookup , la table de recherche est chargée en mémoire et renseignée à partir d’un fichier plat dont vous spécifiez l’emplacement lorsque vous définissez la transformation.
title: Génération du tableau Lookup
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
exl-id: e83d9feb-44fe-4fa1-b559-e1f5606637b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 2%

---

# Génération du tableau Lookup{#populating-the-lookup-table}

{{eol}}

Si vous utilisez les transformations Catégorisation ou FlatFileLookup , la table de recherche est chargée en mémoire et renseignée à partir d’un fichier plat dont vous spécifiez l’emplacement lorsque vous définissez la transformation.

Le fichier plat que vous spécifiez doit répondre aux exigences suivantes :

* Chaque ligne du fichier doit représenter une ligne dans le tableau de recherche.
* Les colonnes du fichier doivent être séparées par un délimiteur ASCII. Vous pouvez utiliser n’importe quel caractère qui n’est pas un caractère de fin de ligne et n’apparaît nulle part dans les données d’événement elles-mêmes. Lorsque vous définissez la transformation, vous spécifiez le caractère qui a été utilisé pour délimiter les colonnes du fichier plat.

Si vous utilisez un [!DNL ODBCLookup] transformation, la table de recherche est chargée en mémoire et remplie à partir d’un tableau ou d’une vue dans un [!DNL ODBC] base de données que vous spécifiez. Lorsque vous définissez la transformation, vous devez également spécifier la source de données, le nom d’utilisateur et le mot de passe que le serveur Data Workbench doit utiliser pour établir une connexion à la base de données.

>[!NOTE]
>
>Les tables de recherche sont chargées lorsque le serveur Data Workbench commence initialement à créer le jeu de données. Une fois établis, les fichiers de recherche ne sont pas censés être modifiés. Si vous modifiez le fichier plat ou [!DNL ODBC] qui est utilisé pour la phase de transformation, vous devez retransformer l’ensemble du jeu de données. Si vous modifiez un fichier plat utilisé pendant la phase de traitement du journal, les nouvelles données de recherche sont appliquées à tous les nouveaux enregistrements qui entrent dans le jeu de données, mais les modifications ne sont pas appliquées rétroactivement.
