---
description: Liens vers des informations supplémentaires sur des paramètres spécifiques du fichier Log Processing.cfg.
title: Paramètres de traitement du journal
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
exl-id: f373e954-6827-4afa-9557-73e0a884a602
translation-type: tm+mt
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

Les filtres définis dans le fichier [!DNL Log Processing.cfg] sont les suivants :

* Heure de fin
* Seuil de hachage
* Heure de début

Le filtrage défini par ces paramètres se produit après que les entrées de journal ont quitté les décodeurs et après les transformations, mais avant leur évaluation par le [!DNL Log Entry Condition]. En général, la modification de l’un de ces paramètres entraîne des modifications de la composition du jeu de données.

La technique recommandée pour utiliser les sources de données [!DNL Sensor] pour créer un jeu de données couvrant une période spécifique consiste à utiliser les paramètres Heure de Début et Heure de fin pour le jeu de données.

Il est préférable d’utiliser les paramètres Heure de Début et Heure de fin plutôt que d’autres techniques, telles que le déplacement des fichiers journaux pour les séparer par répertoire. En définissant le début et les heures de fin du jeu de données, le serveur de l’outil de données utilise automatiquement uniquement les entrées de journal survenues dans l’intervalle donné. En supposant que l’heure de fin ait été utilisée dans le passé, le serveur de l’outil de données met généralement à jour le jeu de données à l’aide du même jeu d’entrées de journal, même si le jeu de données est mis à jour, par exemple en ajoutant une nouvelle transformation.

<!--
c_log_entry_con.xml
-->

## Entrée de journal

Essentiellement, il s&#39;agit d&#39;un processus de filtrage des entrées de journal disponibles. Si [!DNL Log Entry Condition] renvoie la valeur false, l&#39;entrée de journal est filtrée en dehors du jeu d&#39;entrées de journal disponible.

[!DNL Log Entry Condition] est décrit par l&#39;utilisation d&#39;opérations de condition (voir [Conditions](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) et peut utiliser n&#39;importe quel champ d&#39;entrée collecté par [!DNL Sensor] (voir le *Guide du Data Workbench [!DNL Sensor]* ) ou tout champ étendu produit par des transformations contenues dans le fichier [!DNL Log Processing.cfg] pour définir les conditions de test. [!DNL Log Entry] sont appliquées pendant le traitement du journal et peuvent éventuellement être appliquées pendant la transformation.

Cet exemple illustre l&#39;utilisation de [!DNL log entry condition] pour les données du site Web. Vous pouvez utiliser [!DNL Log Entry Condition] pour créer des jeux de données qui se concentrent sur une partie spécifique du site Web ou sur des visiteurs effectuant une action spécifique sur le site.

Dans cet exemple, [!DNL Log Entry Condition] crée un jeu de données qui inclut uniquement les entrées de journal qui font partie du magasin du site. En utilisant [!DNL RECondition test] avec le modèle correspondant [!DNL "/store/.*"] et le champ [!DNL cs-uri-stem] comme entrée à l&#39;expression normale, seules les pages Web qui début avec la chaîne [!DNL "/store/"] sont incluses dans le jeu de données.

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## Séparation de clés {#key-split}

Le nombre d’ID de suivi dans le jeu de données est artificiellement augmenté, mais le nombre total d’entrées de journal traitées par le serveur de l’outil de données n’est pas artificiellement augmenté, ce qui préserve le nombre total de événements comptabilisables dans le jeu de données. Une fois les données d’un élément unique fractionnées, les données sont toujours associées à deux identifiants de suivi différents et ne peuvent plus être liées.

Par exemple, si vous utilisez des données Web, chaque ID de suivi représente un visiteur unique. Si vous activez le fractionnement des clés, les visiteurs de votre jeu de données contenant de grandes quantités de données de événement sont divisés en plusieurs visiteurs. Bien que le nombre de visiteurs dans le jeu de données augmente artificiellement, le nombre total de événements comptabilisables, tels que les vues de page ou les réservations, n’augmente pas artificiellement. Une fois le fractionnement effectué, les données des sous-visiteurs ne peuvent plus être liées.

Le fractionnement des clés utilise un algorithme probabiliste. En conséquence, il existe un compromis entre l&#39;utilisation de la mémoire, la probabilité d&#39;échec, le seuil de division de clé ( [!DNL Split Key Bytes]) et la taille du jeu de données. Avec les paramètres recommandés (comme indiqué ci-dessous), le taux d’échec est faible. Parmi les éléments dont les données de événement dépassent le seuil de fractionnement des clés, environ 1 sur 22 000 (en général moins de 1 par jeu de données) aura certaines de leurs données tronquées plutôt que fractionnées.

Les valeurs recommandées pour chaque paramètre (sans et avec division de clé) sont présentées dans le tableau suivant.

| Paramètre | Aucun fractionnement de clé | Séparation des clés |
|---|---|---|
| Nombre maximal d&#39;octets clés du groupe | 1e6 | 2e6 |
| Split Key Bucket Space | 6e6 | 6e6 |
| Fractionner les octets clés | 0 | 1e6 |
| Proportion d&#39;espace de clé fractionnée | 10 | 10 |

[!DNL Group Maximum Key Bytes] indique la quantité maximale de données de événement pouvant être traitées pour un seul ID de suivi. Les données dépassant cette limite sont filtrées à partir du processus de construction des ensembles de données. [!DNL Split Key Bytes] représente le nombre d’octets au cours duquel un identifiant de suivi unique est divisé en plusieurs éléments. Les éléments sont divisés à environ ce nombre d&#39;octets en fonction d&#39;une distribution des probabilités. [!DNL Split Key Space Ratio] et  [!DNL Split Key Bucket Space] contrôler l&#39;utilisation de la mémoire et le taux d&#39;échec du fractionnement des clés.

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes],  [!DNL Split Key Bytes],  [!DNL Split Key Space Ratio] et  [!DNL Split Key Bucket Space] tous doivent être déclarés pour que le fractionnement des clés fonctionne correctement. Ne modifiez pas les valeurs de ces paramètres sans consulter l’Adobe.
