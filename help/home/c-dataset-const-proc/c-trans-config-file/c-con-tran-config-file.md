---
description: Informations importantes à prendre en compte lors de la modification du fichier Transformation.cfg.
title: Considérations du fichier de configuration de transformation
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 5%

---

# Considérations du fichier de configuration de transformation{#considerations-for-the-transformation-configuration-file}

{{eol}}

Informations importantes à prendre en compte lors de la modification du fichier Transformation.cfg.

* La modification des paramètres de ce fichier nécessite une retransformation des données.
* Si vous retraitez les données, vous pouvez vérifier la variable [!DNL Transformation Progress] dans les [!DNL Processing Legend].

   Pour plus d’informations sur le retraitement de vos données ou de la variable [!DNL Processing Legend,] see [Retraitement et retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize], et [!DNL AppendURI] les transformations ne fonctionnent que lorsqu’elles sont définies dans une [!DNL Transformation Dataset Configuration] fichier . Pour plus d’informations sur ces transformations, voir [Transformations de données](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe recommande de définir des transformations pour la phase de transformation de la construction d’un jeu de données dans un ou plusieurs jeux de données. [!DNL Transformation Dataset Include] fichiers . Pour plus d’informations, voir [Fichiers d’inclusion de jeux de données de transformation](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* Vous pouvez ajouter l’un des paramètres décrits ci-dessus au [!DNL Transformation.cfg] en ouvrant et en modifiant le fichier dans le Bloc-notes. Toutes les modifications que vous apportez et enregistrez s’affichent lorsque vous rouvrez le fichier dans Data Workbench. Lors de l’ajout d’un nouveau paramètre, utilisez la touche Espace (et non la touche de tabulation) pour mettre en retrait deux (2) espaces à droite du niveau d’en-tête précédent.

   Toutes les erreurs qui se produisent pendant la phase de transformation du processus de construction du jeu de données pour un profil de jeu de données sont présentées dans la variable [!DNL Profiles] du noeud [!DNL Detailed Status] dans Data Workbench. Pour plus d’informations sur la variable [!DNL Detailed Status] , voir *Guide de l’utilisateur de Data Workbench*.
