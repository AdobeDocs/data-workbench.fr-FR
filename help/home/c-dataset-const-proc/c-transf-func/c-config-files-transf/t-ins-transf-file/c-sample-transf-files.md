---
description: Informations sur la définition de paramètres dans le fichier Transform.cfg en fonction des différents scénarios.
solution: Analytics
title: Exemples de fichiers Transform.cfg des outils de données
topic: Data workbench
uuid: cb473a5a-54e2-4bf7-84fb-c9c27910ef64
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exemples de fichiers Transform.cfg des outils de données{#sample-data-workbench-transform-cfg-files}

Informations sur la définition de paramètres dans le fichier Transform.cfg en fonction des différents scénarios.

* [Fichier Simple Insight Transform.cfg](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-b7e83cafa3a947c597bd09d316930190)
* [Sortie avec des valeurs séparées par des virgules](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-03916934ad574efc8695abbae54a1816)
* [Fichiers journaux échantillonnés](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-113b3b0c0c7547ea9536bb2f465c0875)
* [Division des fichiers journaux par section du site Web](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-2cac205cd3934d31abb6c6ed8780196d)

Dans chaque exemple, le fichier s’affiche sous la forme d’une [!DNL Transform.cfg] fenêtre dans les outils de données.

## Un fichier Transform.cfg Simple Data Workbench {#section-b7e83cafa3a947c597bd09d316930190}

La [!DNL Transform.cfg] fenêtre suivante contient des instructions pour lire [!DNL .vsl] les fichiers du [!DNL Logs] répertoire et exporter les champs x-timestring et x-trackingid vers un fichier texte stocké dans le répertoire Logs\VT. Étant donné qu’aucune période de rotation de fichier ni aucun format de nom de fichier de sortie n’est spécifié, chaque fichier contient des données pour un jour calendaire et a un nom dans le format par défaut [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SimpleExample.png)

## Sortie avec des valeurs séparées par des virgules {#section-03916934ad574efc8695abbae54a1816}

La [!DNL Transform.cfg] fenêtre suivante contient des instructions pour lire [!DNL .vsl] les fichiers du répertoire Journaux et exporter les champs 0 à 13 vers un fichier délimité par des virgules ( [!DNL .csv]) stocké dans le dossier Logs\VT\CSV directory. Aucune période de rotation de fichier n’étant spécifiée, chaque fichier contient des données pour un jour calendaire. Les fichiers de sortie sont [!DNL .csv] des fichiers nommés au format [!DNL %yyyy%%mm%%dd%-%x-mask%.csv].

![](assets/cfg_VisualTransform_CSVExample.png)

## Exemples de fichiers journaux {#section-113b3b0c0c7547ea9536bb2f465c0875}

Vous pouvez configurer la fonctionnalité de transformation pour créer et gérer une version compacte et à jour de vos fichiers journaux complets. Cela vous permet de tester rapidement vos configurations de jeux de données, avec des temps de retraitement de secondes ou de minutes au lieu des heures nécessaires pour retraiter l&#39;ensemble du jeu de données. L’exemple suivant montre comment configurer la fonctionnalité de transformation pour ce faire.

La [!DNL Transform.cfg] fenêtre suivante contient des instructions pour lire [!DNL .vsl] les fichiers du répertoire Journaux et exporter les champs x-timestring et x-trackingid vers un fichier texte stocké dans le répertoire Logs\VT. Le seuil de hachage spécifié filtre certains ID de suivi du jeu de données, créant ainsi un jeu de données échantillonné par un facteur de 100. Aucune période de rotation de fichier n’étant spécifiée, chaque fichier contient des données pour un jour calendaire. Les noms des fichiers de sortie sont dans le format par défaut [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SampledExample.png)

## Division des fichiers journaux par section du site Web {#section-2cac205cd3934d31abb6c6ed8780196d}

La [!DNL Transform.cfg] fenêtre suivante contient des instructions pour lire [!DNL .vsl]les fichiers du répertoire Journaux et exporter les champs x-timestring et x-trackingid vers un fichier texte stocké dans le répertoire Logs\VT. La transformation de l’expression régulière ( [!DNL RETransform]) prend comme entrée le champ cs-uri-tige et crée un nouveau champ (x-site) qui définit une section du site. Le champ x-site est inclus dans le nom des fichiers texte de sortie, dont chacun contient des données pour un jour calendaire.

![](assets/cfg_VisualTransform_SplittingExample.png)

