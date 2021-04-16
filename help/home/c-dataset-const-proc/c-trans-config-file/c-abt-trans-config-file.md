---
description: Le fichier Transformation.cfg contrôle la phase de transformation de la construction des jeux de données au cours de laquelle des transformations de données supplémentaires sont appliquées aux données déjà traitées pendant le traitement des journaux afin de créer des dimensions étendues à utiliser en analyse.
title: À propos du fichier de configuration de transformation
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
exl-id: 860562d7-6ed3-486b-9f62-1bd06878bf7e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 5%

---

# À propos du fichier de configuration de transformation{#about-the-transformation-configuration-file}

Le fichier Transformation.cfg contrôle la phase de transformation de la construction des jeux de données au cours de laquelle des transformations de données supplémentaires sont appliquées aux données déjà traitées pendant le traitement des journaux afin de créer des dimensions étendues à utiliser en analyse.

Vous devez modifier le fichier [!DNL Transformation.cfg] pour exécuter l&#39;une des tâches de configuration de jeu de données suivantes :

* Filtrage des données à partir du traitement du journal en définissant [!DNL log entry condition] pour la transformation.
* Définition du fuseau horaire à utiliser pour créer des dimensions temporelles et effectuer des conversions temporelles. Voir [Fuseaux horaires](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] Les fichiers peuvent contenir des instructions supplémentaires pour la phase de transformation de la construction des jeux de données. Ces fichiers existent dans le répertoire Dataset\Transformation pour tout profil hérité et ils définissent généralement des paramètres spécifiques à l&#39;application (tels que des paramètres de configuration spécifiques au Web pour l&#39;application [!DNL Site]). Pour plus d&#39;informations sur les fichiers [!DNL Transformation Dataset Include], consultez [Jeu de données Inclure les fichiers](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Pour plus d’informations sur les paramètres de configuration spécifiques au Web pour le site, voir [Paramètres de configuration pour les données Web](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).
