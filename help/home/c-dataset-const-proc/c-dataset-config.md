---
description: La configuration des jeux de données fait référence au processus de modification des fichiers de configuration dont les paramètres fournissent les règles de construction des jeux de données.
solution: Analytics
title: Présentation de la configuration des jeux de données
topic: Data workbench
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Présentation de la configuration des jeux de données{#understanding-dataset-configuration}

La configuration des jeux de données fait référence au processus de modification des fichiers de configuration dont les paramètres fournissent les règles de construction des jeux de données.

Le jeu de données construit réside physiquement dans le [!DNL temp.db] fichier stocké sur l’ordinateur du serveur de l’outil de données, mais les fichiers de configuration du jeu de données résident dans un répertoire pour un profil. Un profil contient un ensemble de fichiers de configuration qui construit un jeu de données (y compris ses dimensions étendues) à des fins d’analyse spécifiques. En outre, un profil contient les définitions d’entités telles que les mesures, les dimensions dérivées, les espaces de travail, les rapports et les visualisations qui permettent aux analystes d’interagir avec le jeu de données et d’obtenir des informations à partir de celui-ci.

Le profil dont vous modifiez les fichiers de configuration de jeu de données est désigné sous le nom de profil de jeu de données. Un profil de jeu de données fait référence à plusieurs profils hérités, qui peuvent être tous les profils que vous créez et gérez afin que vous puissiez configurer votre application Adobe en fonction de vos besoins d’analyse. Un profil de jeu de données peut également faire référence à des profils internes fournis avec votre application Adobe afin de constituer la base de toutes les fonctionnalités disponibles dans votre application.

Pour plus d’informations sur les différents types de profils disponibles avec les applications Adobe, consultez le Guide *de l’utilisateur des outils de* données.

<!--
c_req_config_files.xml
-->

Un profil de jeu de données pour toute application Adobe doit contenir les fichiers de configuration suivants sur l’ordinateur du serveur Insight :

* **Profile.cfg :** Répertorie les profils hérités et les serveurs de traitement du profil. Les serveurs de traitement sont les DPU du serveur Insight qui traitent les données du profil. Si vous avez installé une grappe de serveurs Insight, vous pouvez spécifier plusieurs ordinateurs serveur Insight pour exécuter un profil unique.

   Pour obtenir des instructions sur l’ajout de profils hérités au [!DNL Profile.cfg] fichier du profil d’un jeu de données, consultez le Guide *d’installation et d’administration des produits* serveur. Pour plus d’informations sur l’installation d’une grappe de serveurs Insight ou la configuration d’un profil de jeu de données à exécuter sur une grappe de serveurs Insight, voir le Guide *d’installation et d’administration des produits* serveur.

* **Dataset\Log Processing.cfg :** Contrôle la phase de traitement du journal du processus de construction du jeu de données. Voir [Traitement des](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061)journaux. Pour plus d’informations sur le [!DNL Log Processing.cfg] fichier, voir Fichier [de configuration de traitement des](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)journaux.

* **Dataset\Transformation.cfg :** Contrôle la phase de transformation du processus de construction du jeu de données. Voir [Transformation](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda). Le [!DNL Transformation.cfg] fichier configure généralement le jeu de données pour une analyse spécifique au profil. Pour plus d’informations sur le [!DNL Transformation.cfg] fichier, voir Fichier [de configuration de](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)transformation.

* **Jeu de données Inclure les fichiers :** Un [!DNL dataset include] fichier contient un sous-ensemble des paramètres contenus dans le [!DNL Log Processing.cfg] fichier ou le [!DNL Transformation.cfg] fichier du profil du jeu de données, mais il est stocké et géré dans un profil hérité. [!DNL Dataset include] complètent les fichiers de configuration des jeux de données principaux. Pour plus d’informations, voir Fichiers [inclus dans le jeu de](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)données.

Le profil de jeu de données fourni lors de l’implémentation de votre application Adobe contient un ensemble de fichiers de configuration de jeu de données que vous pouvez ouvrir, modifier et enregistrer à l’aide du [!DNL Profile Manager].

Pour plus d’informations sur le [!DNL Profile Manager]logiciel, consultez le Guide *de l’utilisateur d’* Insight.

<!--
c_addl_config_files.xml
-->

Bien qu’ils ne soient pas obligatoires pour tous les jeux de données, ces fichiers vous permettent de contrôler d’autres aspects du processus de construction des jeux de données :

* **Mode de traitement du journal.cfg :** Le [!DNL Log Processing Mode.cfg] fichier vous permet de suspendre le traitement des données dans un jeu de données, de spécifier des sources hors ligne ou de spécifier la fréquence à laquelle le serveur de l’outil de données enregistre ses fichiers d’état. Voir Fichiers [de configuration](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)supplémentaires.

* **Server.cfg :** Le [!DNL Server.cfg] fichier spécifie la taille du cache de données par défaut (en octets) pour les ordinateurs de l’outil de données qui se connectent au serveur de l’outil de données. Voir Fichiers [de configuration](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)supplémentaires.

* **Transform.cfg et Transform Mode.cfg :** Ces fichiers ne sont disponibles que si vous avez concédé sous licence la fonctionnalité de transformation des données à utiliser avec votre application Adobe. Le [!DNL Transform.cfg] fichier contient les paramètres qui définissent les sources du journal et les transformations de données pour la fonctionnalité de transformation. Les transformations que vous définissez manipulent les données source et les génèrent dans un format que vous spécifiez. Le [!DNL Insight Transform Mode.cfg] fichier vous permet de suspendre le traitement des données dans un jeu de données, de spécifier des sources hors ligne ou de spécifier la fréquence à laquelle la fonctionnalité de transformation du serveur Insight enregistre ses fichiers d’état. Voir Fonctionnalité [de transformation](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

<!--
c_next_steps.xml
-->

Pour plus d’informations sur les tâches de configuration spécifiques à un jeu de données, consultez le tableau ci-dessous afin de localiser et de lire les tâches qui vous intéressent :

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Si vous voulez... </th> 
   <th colname="col2" class="entry"> Voir... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Définir des sources de journal </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Sources de journal </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Déterminer les entrées du journal qui entrent dans le jeu de données lors du traitement du journal </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtres de données</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condition d’entrée de journal</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Activer le fractionnement des ID de suivi avec de grandes quantités de données d’événement </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Séparation des clés</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configuration d’un serveur Insight pour une exécution en tant qu’unité de serveur de fichiers </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité du serveur de fichiers Insight Server </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configuration d’un serveur Insight pour une exécution en tant que serveur de normalisation centralisé </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité du serveur de fichiers Insight Server </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Définir le fuseau horaire à utiliser pour créer des dimensions temporelles et effectuer des conversions temporelles </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fuseaux horaires </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apporter des modifications mineures aux fichiers de configuration du jeu de données inclus dans les profils internes fournis par Adobe </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> Modification d’un jeu de données existant - Inclure des fichiers </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spécifiez les nouveaux champs de données à transmettre du traitement du journal à la transformation </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Création de nouveaux fichiers d’inclusion de jeux de données </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Jeu de données de traitement du journal Inclure les fichiers </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Définir des transformations </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformations de données </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Création de nouveaux fichiers d’inclusion de jeux de données </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Jeu de données de transformation - Inclure les fichiers </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Création de dimensions étendues </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimensions étendues </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Création de nouveaux fichiers d’inclusion de jeux de données </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Jeu de données de transformation - Inclure les fichiers </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Définir des paramètres à utiliser tout au long du traitement ou de la transformation du journal </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Définition de paramètres dans le jeu de données Inclure des fichiers </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Découvrez les interfaces Insight qui vous permettent de surveiller ou de gérer votre jeu de données </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab"> Utilisation Des Interfaces De Configuration Des Jeu De Données </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Masquer certaines dimensions étendues afin qu’elles ne s’affichent pas dans le menu des dimensions d’Insight </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Masquage des composants de jeux de données </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Remplacez certains fichiers de configuration de jeux de données dans un profil que vous ne pouvez pas modifier ou ne souhaitez pas modifier. </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Masquage des composants de jeux de données </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Retraitement de votre jeu de données </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Retraitement et retransformation </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

