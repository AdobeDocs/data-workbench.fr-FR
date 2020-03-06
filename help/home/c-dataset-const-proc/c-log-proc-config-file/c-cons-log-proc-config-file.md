---
description: Informations conceptuelles à prendre en compte lors de la modification du fichier Log Processing.cfg.
solution: Analytics
title: Remarques relatives au fichier de configuration de traitement du journal
topic: Data workbench
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Remarques relatives au fichier de configuration de traitement du journal{#considerations-for-the-log-processing-configuration-file}

Informations conceptuelles à prendre en compte lors de la modification du fichier Log Processing.cfg.

* Les fichiers de données ne doivent pas être déplacés entre les répertoires une fois que les sources d’un jeu de données ont été définies. Les seuls fichiers supplémentaires qu’un répertoire doit recevoir sont ceux qui viennent d’être créés et qui proviennent du serveur de l’outil de données recevant des données de Sensor(s).
* La modification des paramètres de ce fichier nécessite le retraitement de toutes les données. Le paramètre Pause du [!DNL Log Processing Mode.cfg] fichier doit être défini sur false pour que le retraitement se produise. (Notez que la valeur par défaut de ce paramètre est false. Il se peut donc que la modification du paramètre ne soit pas obligatoire.) Pour plus d’informations sur le [!DNL Log Processing Mode.cfg] fichier, voir Fichiers [de configuration](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)supplémentaires.

* Si vous retraitez les données, vous pouvez vérifier le paramètre Progression du traitement du journal dans les outils de données [!DNL Processing Legend].

   Pour plus d’informations sur le retraitement de vos données, voir [Retraitement et retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Voir [Traitement de la légende](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* Le [!DNL Log Processing.cfg] fichier peut être partagé par plusieurs profils de jeux de données. Les transformations définies dans le [!DNL Log Processing.cfg] fichier sont appliquées à tous les profils de jeux de données qui partagent ce fichier de configuration.

   >[!NOTE]
   >
   >Adobe recommande de définir les transformations pour le traitement des journaux dans un ou plusieurs [!DNL dataset include] fichiers de traitement des journaux. Pour plus d&#39;informations, reportez-vous à la section [Journal des jeux de données Inclure les fichiers](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

* Vous pouvez ajouter n’importe lequel des paramètres décrits ci-dessus au [!DNL Log Processing.cfg] fichier en ouvrant et en modifiant le fichier dans le Bloc-notes. Les modifications que vous apportez et enregistrez s’affichent lorsque vous rouvrez le fichier dans l’outil de données. Lors de l’ajout d’un nouveau paramètre, utilisez la touche Espace (et non la touche de tabulation) pour mettre en retrait deux (2) espaces à droite du niveau d’en-tête précédent.

   Toute erreur survenant pendant la phase de traitement du journal du processus de construction d’un jeu de données pour un profil de jeu de données s’affiche dans le [!DNL Profiles] noeud de l’ [!DNL Detailed Status] interface dans l’outil de données. Pour plus d’informations sur l’ [!DNL Detailed Status] interface, consultez le Guide *de l’utilisateur des outils de* données.

