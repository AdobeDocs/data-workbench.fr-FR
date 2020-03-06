---
description: Liens vers des informations supplémentaires sur des paramètres spécifiques du fichier Log Processing.cfg.
solution: Analytics
title: Paramètres de traitement du journal
topic: Data workbench
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Paramètres de traitement du journal{#log-processing-parameters}

Liens vers des informations supplémentaires sur des paramètres spécifiques du fichier Log Processing.cfg.

<!--
c_data_filters.xml
-->

## Filtres de données {#data-filters}

Les filtres définis dans le [!DNL Log Processing.cfg] fichier sont les suivants :

* Heure de fin
* Seuil de hachage
* Heure de début

Le filtrage défini par ces paramètres se produit après que les entrées du journal aient quitté les décodeurs et après les transformations, mais avant leur évaluation par le [!DNL Log Entry Condition]serveur. En général, la modification de l’un de ces paramètres entraîne des modifications de la composition du jeu de données.

La technique recommandée pour l’utilisation de sources de [!DNL Sensor] données afin de créer un jeu de données couvrant une période spécifique consiste à utiliser les paramètres Heure de début et Heure de fin du jeu de données.

L’utilisation des paramètres Heure de début et Heure de fin est préférable à d’autres techniques, telles que le déplacement des fichiers journaux pour les séparer par répertoire. En définissant les heures de début et de fin du jeu de données, le serveur de l’outil de données utilise automatiquement uniquement les entrées de journal survenues dans l’intervalle donné. En supposant que l’heure de fin soit antérieure, le serveur de l’outil de données met généralement à jour le jeu de données à l’aide du même jeu d’entrées de journal, même si le jeu de données est mis à jour par l’ajout, par exemple, d’une nouvelle transformation.

<!--
c_log_entry_con.xml
-->

## Entrée de journal

Il s’agit essentiellement d’un processus de filtrage des entrées de journal disponibles. Si la [!DNL Log Entry Condition] valeur est false, l’entrée du journal est filtrée en dehors du jeu d’entrées disponibles.

La [!DNL Log Entry Condition] section est décrite à l’aide d’opérations de condition (voir [Conditions](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) et peut utiliser n’importe quel champ d’entrée collecté par [!DNL Sensor] (voir le Guide *des outils de[!DNL Sensor]* données ) ou n’importe quel champ étendu généré par des transformations contenues dans le fichier  pour définir les conditions de test. [!DNL Log Processing.cfg] [!DNL Log Entry] sont appliquées au cours du traitement du journal et peuvent être appliquées au cours de la transformation.

Cet exemple illustre l’utilisation de la variable [!DNL log entry condition] pour les données du site Web. Vous pouvez utiliser le [!DNL Log Entry Condition] pour créer des jeux de données qui se concentrent sur une portion spécifique du site Web ou sur les visiteurs qui effectuent une action spécifique sur le site.

Dans cet [!DNL Log Entry Condition] exemple, crée un jeu de données qui inclut uniquement les entrées de journal qui font partie du magasin du site. En utilisant le modèle [!DNL RECondition test] avec [!DNL "/store/.*"] et le champ correspondant comme entrée de l’expression régulière, seules les pages Web qui commencent par la chaîne [!DNL cs-uri-stem] [!DNL "/store/"] sont incluses dans le jeu de données.

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## Séparation de clé {#key-split}

Le nombre d’identifiants de suivi dans le jeu de données est artificiellement augmenté, mais le nombre total d’entrées de journal traitées par le serveur de l’outil de données n’est pas artificiellement augmenté, préservant ainsi le nombre total d’événements dénombrables dans le jeu de données. Une fois les données d’un élément unique fractionnées, les données sont définitivement associées à deux identifiants de suivi différents et ne peuvent plus être liées.

Par exemple, si vous travaillez avec des données Web, chaque ID de suivi représente un visiteur unique. Si vous activez le fractionnement des clés, les visiteurs de votre jeu de données qui contiennent de grandes quantités de données d’événement sont divisés en plusieurs visiteurs. Le nombre de visiteurs dans le jeu de données augmente artificiellement, mais le nombre total d’événements comptabilisables, tels que les pages vues ou les réservations, n’augmente pas artificiellement. Une fois le fractionnement effectué, les données des sous-visiteurs ne peuvent plus être liées.

Le fractionnement des clés utilise un algorithme probabiliste. En conséquence, il existe un compromis entre l’utilisation de la mémoire, la probabilité d’échec, le seuil de division des clés ( [!DNL Split Key Bytes]) et la taille du jeu de données. Avec les paramètres recommandés (comme indiqué ci-dessous), le taux d’échec est faible. Parmi les éléments dont les données d’événement dépassent le seuil de fractionnement des clés, environ 1 sur 22 000 (généralement moins d’1 par jeu de données) verront leurs données tronquées au lieu d’être fractionnées.

Les valeurs recommandées pour chaque paramètre (sans et avec division de clé) sont présentées dans le tableau suivant.

| Paramètre | Pas de division de clé | Séparation des clés |
|---|---|---|
| Nombre maximal d&#39;octets clés du groupe | 1e6 | 2e6 |
| Split Key Bucket Space | 6e6 | 6e6 |
| Fractionner les octets clés | 0 | 1e6 |
| Proportion de l’espace clé | 10 | 10 |

[!DNL Group Maximum Key Bytes] indique la quantité maximale de données d’événement pouvant être traitées pour un seul ID de suivi. Les données dépassant cette limite sont filtrées à partir du processus de construction des jeux de données. [!DNL Split Key Bytes] représente le nombre d’octets au cours duquel un ID de suivi unique est divisé en plusieurs éléments. Les éléments sont divisés à environ ce nombre d’octets selon une distribution de probabilité. [!DNL Split Key Space Ratio] et [!DNL Split Key Bucket Space] contrôler l&#39;utilisation de la mémoire et le taux d&#39;échec du fractionnement des clés.

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes], [!DNL Split Key Bytes], [!DNL Split Key Space Ratio]et tous [!DNL Split Key Bucket Space] doivent être déclarés pour que le fractionnement des clés fonctionne correctement. Ne modifiez pas les valeurs de ces paramètres sans consulter Adobe.

