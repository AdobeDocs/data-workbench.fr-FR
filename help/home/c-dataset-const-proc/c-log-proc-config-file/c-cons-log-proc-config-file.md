---
description: Informations conceptuelles à prendre en compte lors de la modification du fichier Log Processing.cfg.
title: Considérations du fichier de configuration de traitement du journal
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
exl-id: 278a4a10-d382-4d9f-b3f4-bcc4783eb50c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# Considérations du fichier de configuration de traitement du journal{#considerations-for-the-log-processing-configuration-file}

{{eol}}

Informations conceptuelles à prendre en compte lors de la modification du fichier Log Processing.cfg.

* Les fichiers de données ne doivent pas être déplacés entre les répertoires une fois les sources d’un jeu de données définies. Les seuls fichiers supplémentaires qu’un répertoire doit recevoir sont ceux qui viennent d’être créés par le serveur Data Workbench recevant des données de Capteur.
* La modification de l’un des paramètres de ce fichier nécessite le retraitement de toutes les données. Le paramètre Pause dans la variable [!DNL Log Processing Mode.cfg] doit être défini sur false pour que le retraitement se produise. (Notez que la valeur par défaut de ce paramètre est false. Il se peut donc que la modification du paramètre ne soit pas requise.) Pour plus d’informations sur la variable [!DNL Log Processing Mode.cfg] fichier, voir [Fichiers de configuration supplémentaires](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* Si vous traitez à nouveau les données, vous pouvez vérifier le paramètre de progression du traitement du journal dans le fichier de [!DNL Processing Legend].

   Pour plus d’informations sur le retraitement de vos données, voir [Retraitement et retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Voir [Légende de traitement](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* Le [!DNL Log Processing.cfg] peut être partagé par plusieurs profils de jeux de données. Transformations définies dans la variable [!DNL Log Processing.cfg] sont appliqués à tous les profils de jeux de données qui partagent ce fichier de configuration.

   >[!NOTE]
   >
   >Adobe recommande de définir des transformations pour le traitement des journaux dans un ou plusieurs traitements de journaux. [!DNL dataset include] fichiers . Pour plus d’informations, voir [Fichiers d’inclusion de jeux de données de traitement journaux](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

* Vous pouvez ajouter l’un des paramètres décrits ci-dessus au [!DNL Log Processing.cfg] en ouvrant et en modifiant le fichier dans le Bloc-notes. Toutes les modifications que vous apportez et enregistrez s’affichent lorsque vous rouvrez le fichier dans Data Workbench. Lors de l’ajout d’un nouveau paramètre, utilisez la touche Espace (et non la touche de tabulation) pour mettre en retrait deux (2) espaces à droite du niveau d’en-tête précédent.

   Toutes les erreurs qui se produisent pendant la phase de traitement du journal du processus de construction du jeu de données pour un profil de jeu de données sont affichées dans la variable [!DNL Profiles] du noeud [!DNL Detailed Status] dans Data Workbench. Pour plus d’informations sur la variable [!DNL Detailed Status] , voir *Guide de l’utilisateur de Data Workbench*.
