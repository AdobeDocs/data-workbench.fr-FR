---
description: Un jeu de données Adobe contient les données qui ont été chargées et traitées par le serveur de l’outil de données.
solution: Analytics
title: Présentation de la construction de jeux de données
topic: Data workbench
uuid: 540d159d-3f72-49dd-9929-107f1fc62b2b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Présentation de la construction de jeux de données{#understanding-dataset-construction}

Un jeu de données Adobe contient les données qui ont été chargées et traitées par le serveur de l’outil de données.

Les étapes impliquées dans le chargement et le traitement des données par le serveur de l’outil de données (InsightServer64.exe) constituent le processus de construction du jeu de données.

>[!NOTE]
>
>Un serveur de outils de données qui traite et diffuse des données d’un jeu de données Adobe est appelé unité de traitement de données ou DPU. On parle parfois de serveur de traitement ou de serveur de requête. Les outils de données et [!DNL Report] les clients interagissent directement avec les unités de traitement de données.

Lors de la construction d’un jeu de données, le serveur de l’outil de données lit les données source des sources de journal, applique des transformations à des champs de données spécifiques et définit des dimensions étendues à créer à partir des champs transformés. Le processus de construction se déroule en deux phases : Traitement *du* journal *et* transformation. Une fois le jeu de données créé, vous pouvez utiliser les dimensions étendues du jeu de données pour créer des mesures et des dimensions dérivées à des fins d’analyse spécifiques.

La construction d&#39;ensembles de données est comme un processus de fabrication. Vous sélectionnez les données (les matières premières) à utiliser pour créer le jeu de données et vous définissez les transformations de données (étapes de processus) qui manipulent les informations disponibles dans les données pour créer des dimensions étendues (les produits manufacturés).

<!--
c_log_proc.xml
-->

Les journaux sont filtrés et les champs de données à transmettre à la phase de transformation sont identifiés. À la fin de la phase de traitement du journal, les données sont regroupées par ID de suivi (c’est-à-dire que toutes les entrées du journal ayant le même ID de suivi sont regroupées) et triées dans le temps. Pendant la phase de traitement du journal, vous ne pouvez pas accéder aux données traitées à utiliser pour l’analyse.

## Spécification des sources de journal {#section-75279dd6a7304d469735562796741d0f}

Les sources de journal sont des fichiers qui contiennent les données à utiliser pour créer un jeu de données. Les données disponibles dans les sources du journal sont appelées données d’événement, car chaque enregistrement de données représente un enregistrement de transaction ou une instance unique d’un événement. En outre, chaque enregistrement, ou entrée de journal, contient une valeur appelée ID de suivi.

>[!NOTE]
>
>Lors de la sélection des sources de journal, assurez-vous que chaque entrée de journal contient un ID de suivi pour l&#39;entité qui doit représenter le niveau le plus élevé auquel vos données doivent être regroupées. Par exemple, si vous travaillez avec des données collectées à partir du trafic sur le site Web, il est probable que vous choisissiez le visiteur comme cette entité. Chaque visiteur possède un identifiant de suivi unique et toutes les données relatives à un visiteur du site particulier peuvent être regroupées. Pour obtenir de l’aide, contactez Adobe.

Les données d’événement de sources de journal sont collectées en temps réel par [!DNL Sensors] Insight Server ou extraites de sources de données archivées par ce dernier. Les données d’événement collectées par les capteurs à partir des serveurs HTTP et d’applications sont transmises aux serveurs Insight, qui convertissent les données en fichiers journaux ( [!DNL .vsl]) fortement compressés. Les données d’événement qui résident dans un fichier plat, un fichier XML ou une source de données ODBC sont lues par Insight Server, qui fournit des décodeurs que vous définissez pour extraire un ensemble commun de champs de journal de ces différents formats.

## Définition des transformations {#section-55a8cdb47379484081e53087f074778d}

Une transformation est un ensemble d’instructions que vous pouvez définir pour extraire ou manipuler des informations dans les données d’événement. Chaque transformation que vous définissez est appliquée à chaque enregistrement de données d’événement (entrée de journal) afin de mettre à jour les champs de journal existants ou de produire de nouveaux champs. Les résultats des transformations sont utilisés avec les conditions d’entrée du journal pour évaluer les entrées du journal qui sont filtrées hors du jeu de données pendant le traitement du journal.

Tous les types de transformations ne peuvent pas être utilisés pendant la phase de traitement du journal du processus de construction des jeux de données.

## Filtrage des journaux {#section-6172ca0fb0eb4177925151bb49fdbc02}

Le jeu de données contient plusieurs paramètres utilisés pour filtrer les données sortant des transformations. Le filtrage permet de spécifier les entrées de journal à utiliser lors des étapes de traitement suivantes. Par exemple, les filtres peuvent être définis par, période, état de la réponse du serveur ou adresse IP et informations de l’agent utilisateur. Il [!DNL Log Entry Condition] s’agit d’un test de filtrage personnalisable. Le test recherche certaines conditions dans les champs de chaque entrée de journal pour déterminer si cette entrée doit continuer dans le processus de construction du jeu de données. Si une entrée de journal ne satisfait pas à la condition, elle est supprimée du processus de construction.

## Identification des champs pour la transformation {#section-eef98ca723e54547b887aefdf0514c47}

Si un champ de données doit être transmis de la phase de traitement du journal à la phase de transformation pour un traitement ultérieur, vous devez l’identifier lors du traitement du journal. Cette exigence s’applique, que le champ soit disponible à partir des sources du journal ou créé à partir des transformations de données appliquées aux données pendant le traitement du journal.

<!--
c_transformation.xml
-->

Au cours de la phase de transformation de la construction des jeux de données, le traitement se produit sur les données regroupées et triées qui sont générées par le traitement des journaux. Des transformations de données supplémentaires sont effectuées et des dimensions de données étendues sont créées pour être utilisées dans vos analyses. Pendant la phase de transformation, vous pouvez accéder à un échantillon statistique des données qui s’agrandit à mesure que la phase de transformation approche de sa fin.

## Définition des transformations {#section-001b3fd4c1dd4dd38a5536872bc9de68}

Vous pouvez définir les transformations à utiliser pendant la phase de transformation du processus de construction du jeu de données afin de faciliter la création des dimensions étendues. Chaque transformation est appliquée à chaque enregistrement de données d’événement (entrée de journal) transmis à partir du traitement du journal.

## Filtrage des journaux {#section-3fed0a00ca344a719b5e8db363f64f06}

Il [!DNL Log Entry Condition] est possible d’appliquer cette variable pendant la transformation afin de rechercher des conditions spécifiques dans les champs de chaque entrée de journal provenant du traitement du journal. Si une entrée de journal ne satisfait pas à la condition, elle est supprimée du processus de construction.

## Définition de dimensions étendues {#section-25efafd0bfc84c86b9717d453a88c91b}

Les dimensions étendues sont les produits finaux du processus de construction des ensembles de données. Elles représentent des relations entre les champs du journal dans les données. Vous les utilisez pour créer des visualisations, créer des mesures étendues ou effectuer des analyses afin de comprendre les opérations et les problèmes propres à votre entreprise.
