---
description: Le fichier Transformation.cfg contrôle la phase de transformation de la construction des jeux de données au cours de laquelle des transformations de données supplémentaires sont appliquées aux données déjà traitées au cours du traitement des journaux afin de créer des dimensions étendues à utiliser dans l’analyse.
solution: Analytics
title: A propos du fichier de configuration de transformation
topic: Data workbench
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# A propos du fichier de configuration de transformation{#about-the-transformation-configuration-file}

Le fichier Transformation.cfg contrôle la phase de transformation de la construction des jeux de données au cours de laquelle des transformations de données supplémentaires sont appliquées aux données déjà traitées au cours du traitement des journaux afin de créer des dimensions étendues à utiliser dans l’analyse.

Vous devez modifier le [!DNL Transformation.cfg] fichier pour effectuer l’une des tâches suivantes de configuration du jeu de données :

* Filtrage des données à partir du traitement du journal en définissant le [!DNL log entry condition] pour la transformation.
* Définition du fuseau horaire à utiliser pour créer des dimensions temporelles et effectuer des conversions temporelles. Voir Fuseaux [horaires](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] peuvent contenir des instructions supplémentaires pour la phase de transformation de la construction des jeux de données. Ces fichiers existent dans le répertoire Dataset\Transformation pour tout profil hérité et ils définissent généralement des paramètres spécifiques à l’application (tels que les paramètres de configuration spécifiques au Web pour l’ [!DNL Site] application). Pour plus d’informations sur [!DNL Transformation Dataset Include] les fichiers, voir Fichiers [inclus dans le jeu de](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)données. Pour plus d’informations sur les paramètres de configuration spécifiques au Web pour Site, voir Paramètres [de configuration pour les données](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)Web.

