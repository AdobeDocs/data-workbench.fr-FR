---
description: Un jeu de données Adobe contient les données qui ont été chargées et traitées par le serveur Data Workbench.
title: Compréhension de la construction des jeux de données
uuid: 540d159d-3f72-49dd-9929-107f1fc62b2b
exl-id: 111e98b5-d899-4f79-90ce-70f520d527d6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 0%

---

# Compréhension de la construction des jeux de données{#understanding-dataset-construction}

{{eol}}

Un jeu de données Adobe contient les données qui ont été chargées et traitées par le serveur Data Workbench.

Les étapes impliquées dans le chargement et le traitement des données par le serveur Data Workbench (InsightServer64.exe) constituent le processus de construction du jeu de données.

>[!NOTE]
>
>Un serveur Data Workbench qui traite et diffuse des données d’un jeu de données d’Adobe est appelé unité de traitement des données ou DPU. On parle parfois de serveur de traitement ou de serveur de requête. Outils de données et [!DNL Report] Les clients interagissent directement avec les DPU.

Lors de la construction du jeu de données, le serveur Data Workbench lit les données sources à partir de sources de journal, applique des transformations à des champs de données spécifiques et définit des dimensions étendues à créer à partir des champs transformés. Le processus de construction se déroule en deux phases : *Traitement du journal* et *Transformation*. Une fois le jeu de données créé, vous pouvez utiliser les dimensions étendues du jeu de données pour créer des mesures et des dimensions dérivées à des fins d’analyse spécifiques.

La construction d&#39;un jeu de données est comme un processus de fabrication. Vous sélectionnez les données (les matières premières) à utiliser pour créer le jeu de données, et vous définissez les transformations de données (les étapes du processus) qui manipulent les informations disponibles dans les données pour créer des dimensions étendues (les produits manufacturés).

<!--
c_log_proc.xml
-->

Les journaux sont filtrés et les champs de données à transmettre à la phase de transformation sont identifiés. A la fin de la phase de traitement des logs, les données sont regroupées par identifiant de tracking (c&#39;est-à-dire que toutes les entrées de logs ayant le même identifiant de tracking sont regroupées) et classées dans le temps. Pendant la phase de traitement du journal, vous ne pouvez pas accéder aux données traitées à utiliser pour l’analyse.

## Spécification des sources de journal {#section-75279dd6a7304d469735562796741d0f}

Les sources de journal sont des fichiers qui contiennent les données à utiliser pour créer un jeu de données. Les données disponibles dans les sources de journal sont appelées données d’événement, car chaque enregistrement de données représente un enregistrement de transaction ou une instance unique d’un événement. En outre, chaque enregistrement, ou entrée de journal, contient une valeur appelée ID de suivi.

>[!NOTE]
>
>Lorsque vous sélectionnez des sources de journal, assurez-vous que chaque entrée de journal contient un ID de suivi pour l’entité qui doit représenter le niveau le plus élevé auquel vos données doivent être regroupées. Par exemple, si vous travaillez avec des données collectées à partir du trafic du site web, il est probable que vous choisissiez le visiteur comme cette entité. Chaque visiteur possède un identifiant de suivi unique et toutes les données relatives à un visiteur de site particulier peuvent être regroupées. Pour obtenir de l’aide, contactez l’Adobe.

Les données d’événement de sources de journal sont collectées en temps réel par [!DNL Sensors] ou extraites de sources de données archivées par Insight Server. Les données d’événement collectées par les capteurs à partir des serveurs HTTP et d’applications sont transmises aux serveurs Insight, qui convertissent les données en fichiers journaux hautement compressés ( [!DNL .vsl]). Les données d’événement résidant dans un fichier plat, un fichier XML ou une source de données ODBC sont lues par Insight Server, qui fournit des décodeurs que vous définissez pour extraire un ensemble commun de champs de journal à partir de ces différents formats.

## Définition des transformations {#section-55a8cdb47379484081e53087f074778d}

Une transformation est un ensemble d’instructions que vous pouvez définir pour extraire ou manipuler des informations dans les données d’événement. Chaque transformation que vous définissez est appliquée à chaque enregistrement de données d’événement (entrée de journal) pour mettre à jour les champs de journal existants ou produire de nouveaux champs. Les résultats des transformations sont utilisés avec les conditions d’entrée de journal pour évaluer les entrées de journal qui sont filtrées hors du jeu de données pendant le traitement du journal.

Tous les types de transformations ne peuvent pas être utilisés pendant la phase de traitement des journaux du processus de construction du jeu de données.

## Filtrage des journaux {#section-6172ca0fb0eb4177925151bb49fdbc02}

Le jeu de données contient plusieurs paramètres utilisés pour filtrer les données qui sortent des transformations. Le filtrage permet de spécifier les entrées de journal utilisées dans les étapes de traitement suivantes. Par exemple, les filtres peuvent être définis par, période, état de la réponse du serveur ou adresse IP et informations agent-utilisateur. Le [!DNL Log Entry Condition] est un test de filtrage personnalisable. Le test recherche certaines conditions dans les champs de chaque entrée de journal pour déterminer si cette entrée doit continuer dans le processus de construction du jeu de données. Si une entrée de journal ne respecte pas la condition, elle est supprimée du processus de construction.

## Identification des champs pour la transformation {#section-eef98ca723e54547b887aefdf0514c47}

Si un champ de données doit être transmis de la phase de traitement du journal à la phase de transformation pour un traitement ultérieur, vous devez l’identifier lors du traitement du journal. Cette exigence s’applique, que le champ soit disponible à partir des sources du journal ou créé à partir des transformations de données appliquées aux données lors du traitement du journal.

<!--
c_transformation.xml
-->

Au cours de la phase de transformation de la construction du jeu de données, le traitement a lieu sur les données groupées et ordonnées qui sont générées par le traitement du journal. Des transformations de données supplémentaires sont effectuées et des dimensions de données étendues sont créées pour être utilisées dans vos analyses. Au cours de la phase de transformation, vous pouvez accéder à un échantillon statistique des données qui s’agrandit à mesure que la phase de transformation s’approche de la fin.

## Définition des transformations {#section-001b3fd4c1dd4dd38a5536872bc9de68}

Vous pouvez définir des transformations à utiliser pendant la phase de transformation du processus de construction du jeu de données afin de faciliter la création de dimensions étendues. Chaque transformation est appliquée à chaque enregistrement de données d’événement (entrée de journal) transmis à partir du traitement du journal.

## Filtrage des journaux {#section-3fed0a00ca344a719b5e8db363f64f06}

Le [!DNL Log Entry Condition] peut être appliqué pendant la transformation pour rechercher des conditions spécifiques dans les champs de chaque entrée de journal provenant du traitement des logs. Si une entrée de journal ne respecte pas la condition, elle est supprimée du processus de construction.

## Définition des dimensions étendues {#section-25efafd0bfc84c86b9717d453a88c91b}

Les dimensions étendues sont les produits finaux du processus de construction du jeu de données. Elles représentent les relations entre les champs du journal dans les données. Utilisez-les pour créer des visualisations, créer des mesures étendues ou effectuer des analyses afin de comprendre les opérations et les problèmes spécifiques à votre entreprise.
