---
description: Si vous utilisez les transformations Catégoriser ou RechercheFichierPlat, la table de recherche est chargée en mémoire et remplie à partir d’un fichier aplati dont vous spécifiez l’emplacement lorsque vous définissez la transformation.
solution: Analytics
title: Renseigner le tableau de recherche
topic: Data workbench
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Renseigner le tableau de recherche{#populating-the-lookup-table}

Si vous utilisez les transformations Catégoriser ou RechercheFichierPlat, la table de recherche est chargée en mémoire et remplie à partir d’un fichier aplati dont vous spécifiez l’emplacement lorsque vous définissez la transformation.

Le fichier plat que vous spécifiez doit répondre aux exigences suivantes :

* Chaque ligne du fichier doit représenter une ligne dans le tableau de recherche.
* Les colonnes du fichier doivent être séparées par un délimiteur ASCII. Vous pouvez utiliser n’importe quel caractère qui n’est pas un caractère de fin de ligne et n’apparaît nulle part dans les données d’événement proprement dites. Lorsque vous définissez la transformation, vous spécifiez le caractère qui a été utilisé pour délimiter les colonnes du fichier aplati.

Si vous utilisez une [!DNL ODBCLookup] transformation, la table de recherche est chargée en mémoire et remplie à partir d’une table ou d’une vue dans une [!DNL ODBC] base de données que vous spécifiez. Lorsque vous définissez la transformation, vous devez également spécifier la source de données, le nom d’utilisateur et le mot de passe que le serveur de l’outil de données doit utiliser pour établir une connexion à la base de données.

>[!NOTE]
>
>Les tables de recherche sont chargées lorsque le serveur de l’outil de données commence à construire le jeu de données. Une fois établis, les fichiers de recherche ne sont pas censés être modifiés. Si vous modifiez le fichier ou le tableau aplati utilisé pour la phase de transformation, vous devez retransformer l’ensemble des jeux de données. [!DNL ODBC] Si vous modifiez un fichier aplati utilisé pendant la phase de traitement du journal, les nouvelles données de recherche sont appliquées à tous les nouveaux enregistrements qui entrent dans le jeu de données, mais les modifications ne sont pas appliquées rétroactivement.

