---
description: Cette section est un guide rapide qui vous donne les étapes minimales nécessaires pour configurer et planifier des scripts pour retraiter vos fichiers journaux toutes les semaines. Vous pouvez l’utiliser comme guide de référence pour configurer ou modifier vos profils.
title: Script de retraitement hebdomadaire
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
exl-id: f1b6f12e-629e-47c7-aa15-41f76d1c3192
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 2%

---

# Script de retraitement hebdomadaire{#scripting-to-weekly-reprocess}

{{eol}}

Cette section est un guide rapide qui vous donne les étapes minimales nécessaires pour configurer et planifier des scripts pour retraiter vos fichiers journaux toutes les semaines. Vous pouvez l’utiliser comme guide de référence pour configurer ou modifier vos profils.

## Qu’est-ce que le retraitement ? {#section-7e335aacc199488592e78a835e2649fe}

Chargement des données dans DWB en fonction des modifications apportées aux sources de données, aux sources de données hors ligne ou à la période. Le script traite à nouveau le paramètre de date de début dans *Log Processing.cfg* fichier .

## Conditions préalables {#section-804acce5df4942469c9313535627038a}

Identifiant de suite de rapports, nombre de mois les données doivent être disponibles dans DWB. Le dossier Perl64 doit être disponible dans votre dossier C:\ drive.

## Journaux de retraitement {#section-565d3e1f0df14127a97d9beecd14f02f}

Fournir les détails ci-dessus (conditions préalables) dans le script de commande Windows *Reprocess.bat* disponible dans le dossier *\scripts\Log Processing* sur le serveur FSU principal.

Ce script appelle en interne deux scripts spécifiques au client : L’une pour traiter à nouveau les données et l’autre pour les alertes par e-mail. Ces deux scripts sont également disponibles dans la variable *\scripts\Log Processing* dossier.

Le script modifie les paramètres de retraitement dans la variable *Log Processing.cfg* fichier .

## Fenêtre variable pour les journaux {#section-ed5f44d890b34523ab33da7aa0ae3990}

Fournir des détails (conditions préalables) dans le script de commande Windows *logprocessingdate.bat* disponible dans le dossier *\scripts\Scripository* sur le serveur FSU en cours. Ce script appelle en interne deux scripts spécifiques au client : Un pour configurer la date de début des logs et un autre pour les alertes par email. Ces deux scripts sont également disponibles dans* \scripts\Scripository*

Indiquez l’identifiant de la suite de rapports et le nombre de mois dans le fichier* logprocessingdate.bat*.

Le script modifie le paramètre de date de début dans *Log Processing.cfg*.

>[!NOTE]
>
>Si la variable *Scripository* n’est pas disponible, procédez comme suit pour copier le dossier *Scripository* et apportez des modifications aux fichiers ci-dessus à l’aide de détails spécifiques au client. Indiquez également votre adresse électronique pour obtenir une alerte en cas d’erreur.

## Planification de scripts {#section-063cf0c755dc47d28d60947d8d43d0e9}

Pour planifier les scripts dans le planificateur de tâches Windows, procédez comme suit.

1. Planifiez le script dans le planificateur de tâches de Windows.

   * Ouvrez le planificateur de tâches : Cliquez avec le bouton droit de la souris sur le **Bibliothèque du planificateur de tâches** et cliquez sur **Créer une tâche**.

   * Dans le **Général** Indiquez un nom de tâche et sélectionnez **Options**.

   * Sous , **Triggers** , cliquez sur **Nouveau** et une nouvelle fenêtre s’ouvre.

   * Sous , **Actions** , cliquez sur **Nouveau** et une nouvelle fenêtre s’ouvre. Indiquez ensuite les détails du script et d’autres options. (Le fait de commencer dans aura un chemin où le script est placé).

1. Validation : Cliquez avec le bouton droit de la souris, puis exécutez la tâche et vérifiez les modifications dans la *Log processing.cfg* fichier . Un courrier électronique est envoyé à l’ID de courrier électronique fourni dans le script.
