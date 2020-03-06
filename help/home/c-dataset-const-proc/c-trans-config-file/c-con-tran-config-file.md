---
description: Informations importantes à prendre en compte lors de la modification du fichier Transformation.cfg.
solution: Analytics
title: Considérations relatives au fichier de configuration de transformation
topic: Data workbench
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Considérations relatives au fichier de configuration de transformation{#considerations-for-the-transformation-configuration-file}

Informations importantes à prendre en compte lors de la modification du fichier Transformation.cfg.

* La modification de l’un des paramètres de ce fichier nécessite une retransformation des données.
* Si vous retraitez les données, vous pouvez vérifier le [!DNL Transformation Progress] paramètre dans les outils de données [!DNL Processing Legend].

   Pour plus d’informations sur le retraitement de vos données ou sur la [!DNL Processing Legend,] section [Retraitement et retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]et [!DNL AppendURI] les transformations ne fonctionnent que lorsqu’elles sont définies dans un [!DNL Transformation Dataset Configuration] fichier. Pour plus d’informations sur ces transformations, voir Transformations [de données](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe recommande de définir les transformations de la phase de transformation de la construction d’un jeu de données dans un ou plusieurs [!DNL Transformation Dataset Include] fichiers. Pour plus d&#39;informations, reportez-vous à la page [Transformation Data Set Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)(Jeu de données de transformation - Inclusion de fichiers).

* Vous pouvez ajouter n’importe lequel des paramètres décrits ci-dessus au [!DNL Transformation.cfg] fichier en ouvrant et en modifiant le fichier dans le Bloc-notes. Les modifications que vous apportez et enregistrez s’affichent lorsque vous rouvrez le fichier dans l’outil de données. Lors de l’ajout d’un nouveau paramètre, utilisez la touche Espace (et non la touche de tabulation) pour mettre en retrait deux (2) espaces à droite du niveau d’en-tête précédent.

   Toute erreur survenant pendant la phase de transformation du processus de construction d’un jeu de données pour un profil de jeu de données est affichée dans le [!DNL Profiles] noeud de l’ [!DNL Detailed Status] interface dans l’outil de données. Pour plus d’informations sur l’ [!DNL Detailed Status] interface, consultez le Guide *de l’utilisateur des outils de* données.

