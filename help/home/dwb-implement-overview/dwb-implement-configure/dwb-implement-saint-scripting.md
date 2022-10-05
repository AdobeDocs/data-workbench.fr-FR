---
description: Cette section explique le script Saint Scrubber.
title: Script de la barre de défilement SAINT
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
exl-id: 5f6d92b1-baaa-4d67-a1c2-ce7d51affb17
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 1%

---

# Script de la barre de défilement SAINT{#scripting-for-the-saint-scrubber}

{{eol}}

Cette section explique le script Saint Scrubber.

## Présentation de la classification des SAINTS {#section-b840a99f10684bb4b58e844a515d0d79}

La classification est également connue sous l’acronyme SAINT pour l’outil d’importation et de dénomination des attributs de SiteCatalyst.

Lorsque nous &quot;classifions&quot; une variable de SiteCatalyst, vous établissez une relation entre une variable et les métadonnées associées à cette variable. Les classifications sont le plus souvent utilisées dans la zone Campagnes. Je les utiliserai donc pour les expliquer. La plupart des clients envoient du trafic de campagne vers leur site à l’aide d’un code de suivi. Ce code de suivi est un identifiant qui peut représenter un mot-clé spécifique acheté sur Google, tel que &quot;goog123&quot;. Cet identifiant est transmis dans la variable s.campaigns afin que vous puissiez déterminer les événements de succès du site qui se produisent une fois que les visiteurs sont venus sur votre site à partir de ce code de campagne.

Mais que se passe-t-il si, au lieu d’afficher les campagnes uniquement selon le code de suivi, vous souhaitez voir les résultats de campagne par moteur de recherche, mot-clé ou canal de campagne ? Devez-vous créer une variable de conversion pour le moteur de recherche, un autre pour le mot-clé et un autre pour le canal Campaign ? Si c’est le cas, vous utiliserez un grand nombre de vos cinquante variables sur les seules campagnes ! Heureusement, vous pouvez utiliser les classifications pour faciliter votre vie ! Puisque chaque code de suivi peut comporter un moteur de recherche, un mot-clé ou un canal de campagne, vous pouvez simplement créer trois classifications de la variable Campagnes pour représenter chacune d’elles. Vous dites essentiellement au SiteCatalyst qu’il existe une relation directe entre la variable Campagnes et ces trois autres valeurs &quot;métadonnées&quot;. Ce faisant, SiteCatalyst vous permettra de découper les événements de succès du site en fonction des quatre variables sans aucun balisage supplémentaire.

## Script de défilement de SAINT dans DWB {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

Ce script est utilisé lorsque vous incorporez des données de classification de SAINT dans la base de données. Le script *SaintScrubber.dat* est normalement placé sous le *\Scripts\Scripository* sur le FSU.

L’objectif principal de ce script est de supprimer l’en-tête dans la variable `<discoiqbr>` Fichiers de classification de SAINT. Il comptabilise également le nombre si la colonne mentionnée dans la ligne d’en-tête de la colonne vérifie toutes les lignes de données. S’il existe des lignes comportant moins ou plus de colonnes, il supprime ces lignes du fichier.

Le *SaintScrubber.dat* appelle en interne le script *saint_scrubber.pl*. Vous trouverez ci-dessous les détails de ce fichier de script :

Chemin : *E:\Scripts\Scripository\Library\Perl*

Arguments de script :

1. Input Folder (obligatoire) : source_directory
1. Output Folder (obligatoire) : destination_directory
1. Délimiteur (obligatoire) : délimiteur
1. Rejeter le dossier (facultatif)(le paramètre peut être laissé vide ou omis de la ligne de commande)
1. Dossier de journal (facultatif)(le paramètre peut être laissé vide ou omis de la ligne de commande)

Étapes exécutées dans le script Perl :

1. Remplacez les flux de formulaire avec échappement, les nouvelles lignes, les retours chariot, les onglets par des espaces.
1. Supprimez les doublons d’octets interprétés comme un caractère de contrôle dans le plan multilingue de base UTF-8, à l’exception des éléments suivants :

   * Onglet horizontal 9
   * Flux de 10 lignes
   * 12 flux de formulaire
   * 13 retours chariot
   * Utilisez le mot-clé barre verticale comme délimiteur pour | par exemple : barre délimiteuse
   * Suppression d’autres caractères problématiques
   * Après le défilement ci-dessus, déposez toutes les lignes comportant un certain nombre de colonnes différentes de la première ligne de données (non vide ni commentaire).
   * Prise en charge des fichiers de rejet facultatifs pour contenir les lignes rejetées au lieu de les ignorer
   * prendre en charge le dossier d’entrée récursif ; générer des dossiers de sortie de la même structure ;
   * Déplacez les fichiers d’entrée traités vers les sous-dossiers traités afin que le script ne répète pas l’opération lors d’une nouvelle exécution sur le même dossier d’entrée existant.
   * Reconnaître la date dans les noms de fichier de Workbench ; trier le traitement par date puis par alpha, quel que soit le nom du dossier ; Cela permet de s’assurer que la séquence est correcte quel que soit le type de fichier (ecom, non-ecom) ou l’identifiant de suite de rapports (si vous traitez plusieurs suites de rapports dans un seul jeu de données Insight).
   * Prise en charge des alertes par email `<discoiqbr>`
