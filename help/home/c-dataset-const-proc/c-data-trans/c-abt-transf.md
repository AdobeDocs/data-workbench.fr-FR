---
description: Les transformations vous permettent d’extraire les informations disponibles dans vos fichiers de données et de les manipuler sous une forme plus utile.
title: À propos des transformations
uuid: 9366f607-741d-4512-9e1b-4165f4291246
exl-id: 9bd533ef-a87e-400a-9bb0-5af1851cca0a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 1%

---

# À propos des transformations{#about-transformations}

Les transformations vous permettent d’extraire les informations disponibles dans vos fichiers de données et de les manipuler sous une forme plus utile.

Les transformations fonctionnent sur les entrées de journal (vous pouvez considérer les entrées de journal comme des lignes de données) dans vos sources de journaux. Pour chaque ligne de données, la transformation prend la valeur du champ d’entrée spécifié, effectue un ensemble d’étapes de traitement et enregistre le résultat dans le champ de sortie que vous spécifiez. Vous pouvez définir des transformations à exécuter pendant la phase de traitement des journaux ou de transformation du processus de construction du jeu de données :

* **Pendant le traitement du journal :**  les transformations exécutées pendant la phase de traitement du journal de la construction du jeu de données sont appliquées à chaque enregistrement de données d’événement (entrée de journal) pour mettre à jour les champs du journal existants ou produire de nouveaux champs. Les résultats des transformations sont utilisés avec les conditions d’entrée de journal pour évaluer les entrées de journal qui sont filtrées hors du jeu de données pendant le traitement du journal.
* **Pendant la transformation :**  les transformations exécutées lors de la phase de transformation de la construction du jeu de données fonctionnent sur les champs de données transmis par le traitement du journal pour créer des dimensions étendues que vous pouvez utiliser dans vos analyses. Voir [Dimensions étendues](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

>[!NOTE]
>
>L’entrée des données pour la transformation à partir du traitement des logs est ordonnée par heure et regroupée par identifiant de suivi dans vos données source. Plusieurs transformations nécessitent que les données se trouvent dans ce formulaire et fonctionnent uniquement lorsqu’elles sont définies dans pendant la transformation.

Les modifications apportées aux transformations doivent être effectuées avec soin. Les transformations n’affectent pas les entrées de journal qui s’écoulent dans le processus de construction du jeu de données, mais elles affectent les résultats présentés. Cela permet d’apporter des modifications à ce qui est analysé sans modifier les données sur lesquelles repose l’analyse. Cependant, les changements dans les transformations peuvent fondamentalement modifier les valeurs produites dans les analyses.
