---
description: Cette section est un guide rapide qui vous donne les étapes minimales nécessaires pour configurer et programmer des scripts pour retraiter vos fichiers journaux chaque semaine. Il peut servir de guide de référence pour configurer ou modifier vos profils.
title: Script vers retraitement hebdomadaire
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Script vers retraitement hebdomadaire{#scripting-to-weekly-reprocess}

Cette section est un guide rapide qui vous donne les étapes minimales nécessaires pour configurer et programmer des scripts pour retraiter vos fichiers journaux chaque semaine. Il peut servir de guide de référence pour configurer ou modifier vos profils.

## Qu’est-ce que le retraitement ? {#section-7e335aacc199488592e78a835e2649fe}

Chargement des données vers DWB en fonction des modifications apportées aux sources de données, aux sources de données hors ligne ou à la période. Le script va retraiter le paramètre de date de début dans le fichier *Log Processing.cfg* .

## Conditions préalables {#section-804acce5df4942469c9313535627038a}

Identifiant de suite de rapports, nombre de mois les données doivent être disponibles dans DWB. Le dossier Perl64 doit être disponible dans votre dossier C:\ drive.

## Journaux de retraitement {#section-565d3e1f0df14127a97d9beecd14f02f}

Fournissez les détails ci-dessus (conditions préalables) dans le script de commande Windows *Reprocess.bat* disponible dans le dossier \scripts\Log Processing *sur le serveur FSU principal* .

Ce script appellera en interne deux scripts client spécifiques : l’une pour retraiter les données et l’autre pour l’alerte par courrier électronique. Ces deux scripts sont également disponibles dans le dossier *\scripts\Log Processing* .

Le script modifie les paramètres de retraitement dans le fichier *Log Processing.cfg* .

## Fenêtre flottante pour les journaux {#section-ed5f44d890b34523ab33da7aa0ae3990}

Fournissez des détails (prérequis) dans le script de commande Windows *logprocessingdate.bat* disponible dans le dossier *\scripts\Scripository* sur le serveur FSU de gestion. Ce script appellera en interne deux scripts client spécifiques : L’une consiste à configurer la date de début des journaux et l’autre pour les alertes par courrier électronique. Ces deux scripts sont également disponibles dans* \scripts\Scripository*

Indiquez l’identifiant de suite de rapports et le nombre de mois dans le fichier * logprocessingdate.bat*.

Le script modifie le paramètre de date de début dans *Log Processing.cfg*.

>[!NOTE]
>
>Si le dossier *Scripository* n’est pas disponible, suivez la procédure ci-dessous pour copier le dossier *Scripository* et apporter des modifications aux fichiers ci-dessus à l’aide des détails propres au client. Indiquez également votre adresse électronique pour obtenir une alerte en cas d’erreur.

## Planification des scripts {#section-063cf0c755dc47d28d60947d8d43d0e9}

Pour planifier les scripts dans le planificateur de tâches Windows, procédez comme suit.

1. Planifiez le script dans le planificateur de tâches de Windows.

   * Ouvrir le planificateur de tâches : Cliquez avec le bouton droit sur la bibliothèque **du planificateur de** tâches et cliquez sur **Créer une tâche**.

   * Dans l’onglet **Général** , indiquez un nom de tâche et sélectionnez **Options**.

   * Sous l’onglet **Déclencheurs** , cliquez sur **Nouveau** et une nouvelle fenêtre s’ouvre.

   * Sous l’onglet **Actions** , cliquez sur **Nouveau** pour ouvrir une nouvelle fenêtre. Fournissez ensuite les détails du script et d’autres options. (Le chemin d’accès où le script est placé est indiqué).

1. Validation : Cliquez avec le bouton droit de la souris et exécutez la tâche et vérifiez les modifications dans le fichier *Log processing.cfg* . Un courrier électronique sera envoyé à l’ID de courrier électronique fourni dans le script.

