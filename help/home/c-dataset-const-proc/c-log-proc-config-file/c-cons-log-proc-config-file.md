---
description: Informations conceptuelles à prendre en compte lors de la modification du fichier Log Processing.cfg.
title: Considérations du fichier de configuration de traitement du journal
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
exl-id: 278a4a10-d382-4d9f-b3f4-bcc4783eb50c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# Considérations du fichier de configuration de traitement du journal{#considerations-for-the-log-processing-configuration-file}

Informations conceptuelles à prendre en compte lors de la modification du fichier Log Processing.cfg.

* Les fichiers de données ne doivent pas être déplacés entre les répertoires une fois que les sources d&#39;un jeu de données ont été définies. Les seuls fichiers supplémentaires qu’un répertoire doit recevoir sont ceux qui viennent d’être créés et qui proviennent du serveur de l’outil de données recevant des données de Sensor(s).
* La modification des paramètres de ce fichier nécessite le retraitement de toutes les données. Le paramètre Pause du fichier [!DNL Log Processing Mode.cfg] doit être défini sur false pour que le retraitement se produise. (Notez que la valeur par défaut de ce paramètre est false ; il se peut donc que la modification du paramètre ne soit pas nécessaire.) Pour plus d&#39;informations sur le fichier [!DNL Log Processing Mode.cfg], consultez [Autres fichiers de configuration](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* Si vous retraitez les données, vous pouvez vérifier le paramètre Progression du traitement du journal dans [!DNL Processing Legend] de l’outil de données.

   Pour plus d’informations sur le retraitement de vos données, voir [Retraitement et retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Voir [Légende de traitement](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* Le fichier [!DNL Log Processing.cfg] peut être partagé par plusieurs profils de jeux de données. Les transformations définies dans le fichier [!DNL Log Processing.cfg] sont appliquées à tous les profils de jeux de données qui partagent ce fichier de configuration.

   >[!NOTE]
   >
   >Adobe recommande de définir des transformations pour le traitement du journal dans un ou plusieurs fichiers de traitement du journal [!DNL dataset include]. Pour plus d’informations, voir [Jeu de données de traitement du journal Inclure les fichiers](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

* Vous pouvez ajouter n&#39;importe lequel des paramètres décrits ci-dessus au fichier [!DNL Log Processing.cfg] en ouvrant et en modifiant le fichier dans le Bloc-notes. Les modifications que vous apportez et enregistrez s’affichent lorsque vous rouvrez le fichier dans l’outil de données. Lors de l’ajout d’un nouveau paramètre, utilisez la touche Espace (et non la touche de tabulation) pour mettre en retrait deux (2) espaces à droite du niveau d’en-tête précédent.

   Toutes les erreurs survenant pendant la phase de traitement du journal du processus de construction des jeux de données pour un profil de jeux de données sont affichées dans le noeud [!DNL Profiles] de l&#39;interface [!DNL Detailed Status] de l&#39;outil de données. Pour plus d&#39;informations sur l&#39;interface [!DNL Detailed Status], consultez le *Guide de l&#39;utilisateur Data Workbench*.
