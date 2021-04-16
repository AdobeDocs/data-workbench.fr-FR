---
description: Informations importantes à prendre en compte lors de la modification du fichier Transformation.cfg.
title: Considérations du fichier de configuration de transformation
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 5%

---

# Considérations du fichier de configuration de transformation{#considerations-for-the-transformation-configuration-file}

Informations importantes à prendre en compte lors de la modification du fichier Transformation.cfg.

* La modification des paramètres de ce fichier nécessite une retransformation des données.
* Si vous retraitez les données, vous pouvez vérifier le paramètre [!DNL Transformation Progress] dans l&#39;outil de données [!DNL Processing Legend].

   Pour plus d&#39;informations sur le retraitement de vos données ou sur le [!DNL Processing Legend,] voir [Retraitement et retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows],  [!DNL ODBCLookup],  [!DNL Sessionize] et  [!DNL AppendURI] les transformations ne fonctionnent que lorsqu’elles sont définies dans un  [!DNL Transformation Dataset Configuration] fichier. Pour plus d’informations sur ces transformations, voir [Transformations de données](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe recommande de définir des transformations pour la phase de transformation de la construction des ensembles de données dans un ou plusieurs fichiers [!DNL Transformation Dataset Include]. Pour plus d’informations, voir [Transformation Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* Vous pouvez ajouter n&#39;importe lequel des paramètres décrits ci-dessus au fichier [!DNL Transformation.cfg] en ouvrant et en modifiant le fichier dans le Bloc-notes. Les modifications que vous apportez et enregistrez s’affichent lorsque vous rouvrez le fichier dans l’outil de données. Lors de l’ajout d’un nouveau paramètre, utilisez la touche Espace (et non la touche de tabulation) pour mettre en retrait deux (2) espaces à droite du niveau d’en-tête précédent.

   Toutes les erreurs survenant pendant la phase de transformation du processus de construction des ensembles de données pour un profil de jeux de données sont affichées dans le noeud [!DNL Profiles] de l&#39;interface [!DNL Detailed Status] de l&#39;outil de données. Pour plus d&#39;informations sur l&#39;interface [!DNL Detailed Status], consultez le *Guide de l&#39;utilisateur Data Workbench*.
