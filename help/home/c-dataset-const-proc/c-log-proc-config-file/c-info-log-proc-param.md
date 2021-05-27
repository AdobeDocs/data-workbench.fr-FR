---
description: Liens vers des informations supplémentaires sur des paramètres spécifiques du fichier Log Processing.cfg.
title: Paramètres de traitement du journal
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
exl-id: f373e954-6827-4afa-9557-73e0a884a602
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 2%

---

# Paramètres de traitement du journal{#log-processing-parameters}

Liens vers des informations supplémentaires sur des paramètres spécifiques du fichier Log Processing.cfg.

<!--
c_data_filters.xml
-->

## Filtres de données {#data-filters}

Les filtres définis dans le fichier [!DNL Log Processing.cfg] incluent les éléments suivants :

* Heure de fin
* Seuil de hachage
* Heure de début

Le filtrage défini par ces paramètres se produit une fois que les entrées de journal ont quitté les décodeurs et après les transformations, mais avant leur évaluation par la balise [!DNL Log Entry Condition]. En règle générale, la modification de l’un de ces paramètres entraîne des modifications de la composition du jeu de données.

La technique recommandée pour utiliser des sources de données [!DNL Sensor] afin de créer un jeu de données couvrant une période spécifique consiste à utiliser les paramètres Heure de début et Heure de fin pour le jeu de données.

L’utilisation des paramètres Heure de début et Heure de fin est préférable à d’autres techniques, telles que le déplacement des fichiers journaux pour les séparer par répertoire. En définissant les heures de début et de fin du jeu de données, le serveur Data Workbench utilise automatiquement uniquement les entrées de journal survenues pendant l’intervalle donné. En supposant que l’heure de fin ait été passée, le serveur Data Workbench met généralement à jour le jeu de données à l’aide du même ensemble d’entrées de journal, même si le jeu de données est mis à jour en ajoutant, par exemple, une nouvelle transformation.

<!--
c_log_entry_con.xml
-->

## Entrée de journal

Il s’agit essentiellement d’un processus de filtrage sur les entrées de journal disponibles. Si la valeur [!DNL Log Entry Condition] est false, l’entrée du journal est filtrée à partir du jeu d’entrées de journal disponible.

[!DNL Log Entry Condition] est décrit à l’aide des opérations de condition (voir [Conditions](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) et peut utiliser n’importe quel champ d’entrée collecté par [!DNL Sensor] (voir le *Guide du Data Workbench [!DNL Sensor]* ) ou n’importe quel champ étendu produit par des transformations contenues dans le fichier [!DNL Log Processing.cfg] pour définir les conditions de test. [!DNL Log Entry] Les conditions sont appliquées lors du traitement du journal et peuvent éventuellement être appliquées lors de la transformation.

Cet exemple illustre l’utilisation de [!DNL log entry condition] pour les données du site web. Vous pouvez utiliser [!DNL Log Entry Condition] pour créer des jeux de données qui se concentrent sur une partie spécifique du site web ou sur les visiteurs effectuant une action spécifique sur le site.

La balise [!DNL Log Entry Condition] de cet exemple crée un jeu de données qui inclut uniquement les entrées de journal qui font partie de la boutique du site. En utilisant [!DNL RECondition test] avec le modèle correspondant [!DNL "/store/.*"] et le champ [!DNL cs-uri-stem] comme entrée de l’expression régulière, seules les pages web commençant par la chaîne [!DNL "/store/"] sont incluses dans le jeu de données.

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## Partage de clés {#key-split}

Le nombre d’identifiants de suivi dans le jeu de données augmente artificiellement, mais le nombre total d’entrées de journal traitées par le serveur Data Workbench n’augmente pas artificiellement, préservant ainsi le nombre total d’événements dénombrables dans le jeu de données. Une fois que les données d’un seul élément sont fractionnées, les données sont définitivement associées à deux ID de suivi différents et ne peuvent plus être liées.

Par exemple, si vous utilisez des données web, chaque ID de suivi représente un visiteur unique. Si vous activez le fractionnement des clés, les visiteurs de votre jeu de données contenant de grandes quantités de données d’événement sont divisés en plusieurs visiteurs. Bien que le nombre de visiteurs dans le jeu de données ait été artificiellement augmenté, le nombre total d’événements dénombrables tels que les pages vues ou les réservations n’a pas été artificiellement augmenté. Une fois le partage effectué, les données des sous-visiteurs ne peuvent pas être liées.

Le fractionnement des clés utilise un algorithme probabiliste. Par conséquent, il existe un compromis entre l’utilisation de la mémoire, la probabilité d’échec, le seuil de division de clé ( [!DNL Split Key Bytes]) et la taille du jeu de données. Avec les paramètres recommandés (comme répertoriés ci-dessous), le taux d’échec est faible. Parmi les éléments dont les données d’événement dépassent le seuil de division de clé, environ 1 sur 22 000 (généralement moins de 1 par jeu de données) auront certaines de leurs données tronquées plutôt que fractionnées.

Les valeurs recommandées pour chaque paramètre (sans et avec fractionnement de clé) sont présentées dans le tableau suivant.

| Paramètre | Aucun découpage de clés | Fractionnement des clés |
|---|---|---|
| Nombre maximal d’octets de clé du groupe | 1e6 | 2e6 |
| Split Key Bucket Space | 6e6 | 6e6 |
| Fractionner les octets clés | 0 | 1e6 |
| Split Key Space Ratio | 10 | 10 |

[!DNL Group Maximum Key Bytes] spécifie la quantité maximale de données d’événement pouvant être traitées pour un seul ID de suivi. Les données dépassant cette limite sont filtrées à partir du processus de construction du jeu de données. [!DNL Split Key Bytes] représente le nombre d’octets au cours duquel un identifiant de suivi unique est divisé en plusieurs éléments. Les éléments sont fractionnés à environ ce nombre d’octets selon une distribution de probabilité. [!DNL Split Key Space Ratio] et  [!DNL Split Key Bucket Space] contrôler l’utilisation de la mémoire et le taux d’échec du fractionnement des clés.

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes],  [!DNL Split Key Bytes],  [!DNL Split Key Space Ratio] et  [!DNL Split Key Bucket Space] tous doivent être déclarés pour que le fractionnement des clés fonctionne correctement. Ne modifiez pas les valeurs de ces paramètres sans Adobe de consultant.
