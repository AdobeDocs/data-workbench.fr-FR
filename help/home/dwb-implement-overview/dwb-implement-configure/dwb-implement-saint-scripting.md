---
description: Cette section explique le script Saint Scrubber.
title: Script pour la barre de défilement SAINT
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Script pour la barre de défilement SAINT{#scripting-for-the-saint-scrubber}

Cette section explique le script Saint Scrubber.

## Présentation de la classification SAINT {#section-b840a99f10684bb4b58e844a515d0d79}

La classification est également connue sous l’acronyme SAINT pour SiteCatalyst Attribute Importing and Naming Tool (Outil d’importation et de nommage d’attributs de SiteCatalyst).

Lorsque nous classifions une variable SiteCatalyst, vous établissez une relation entre une variable et les métadonnées qui y sont associées. Les classifications sont le plus souvent utilisées dans la zone Campagnes. Je les utiliserai donc pour les expliquer. La plupart des clients envoient du trafic de campagne vers leur site à l’aide d’un code de suivi. Ce code de suivi est un identifiant qui peut représenter un mot-clé spécifique acheté sur Google, tel que &quot;goog123&quot;. Cet identifiant est transmis à la variable s.campaigns afin que vous puissiez déterminer les événements de réussite du site qui se produisent une fois que les visiteurs sont venus sur votre site à partir de ce code de campagne.

Mais que se passe-t-il si, au lieu d&#39;afficher les campagnes uniquement en fonction du code de suivi, vous souhaitez afficher les résultats des campagnes par moteur de recherche, mot-clé ou canal de campagne ? Devez-vous créer une nouvelle variable de conversion pour le moteur de recherche, une autre pour le mot-clé et une autre pour le canal de campagne ? Si c’est le cas, vous utiliseriez une grande partie de vos cinquante variables sur les seules campagnes ! Heureusement, vous pouvez utiliser les Classifications pour vous faciliter la vie ! Chaque code de suivi pouvant comporter un moteur de recherche, un mot-clé ou un canal de campagne, vous pouvez simplement créer trois classifications de la variable Campagnes pour représenter chacune d&#39;elles. Vous dites essentiellement à SiteCatalyst qu’il existe une relation directe entre la variable Campagnes et ces trois autres valeurs de métadonnées. Ce faisant, SiteCatalyst vous permettra de trier et de découper les événements de réussite du site en fonction des quatre variables sans balisage supplémentaire.

## Script de défilement SAINT dans DWB {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

Ce script est utilisé lorsque vous importez des données de classification SAINT dans DWB. Le script *SaintScrubber.dat* est normalement placé sous le dossier *\Scripts\Scripository* sur le FSU.

L’objectif principal de ce script est de supprimer l’en-tête dans les fichiers de classification `<discoiqbr>` SAINT. Il comptabilise également le nombre si la colonne mentionnée dans la ligne d’en-tête de colonne vérifie toutes les lignes de données. S’il y a des lignes avec moins ou plus de colonnes, il supprime ces lignes du fichier.

Le *SaintScrubber.dat* appelle en interne le script *saint_scrubber.pl. Vous trouverez ci-dessous les détails de ce fichier de script :

Chemin : *E:\Scripts\Scripository\Library\Perl*

Arguments de script :

1. Dossier d’entrée (obligatoire) : source_directory
1. Dossier de sortie (obligatoire) : destination_directory
1. Délimiteur (obligatoire) : délimiteur
1. Rejeter le dossier (facultatif) (le paramètre peut être laissé vide ou omis de la ligne de commande)
1. Dossier journal (facultatif) (le paramètre peut être laissé vide ou omis dans la ligne de commande)

Etapes effectuées dans le script Perl :

1. Remplacez les flux de formulaire avec séquence d’échappement, les nouvelles lignes, les retours chariot, les onglets par des espaces.
1. Supprimez les octets doubles interprétés comme un caractère de contrôle dans le BMP UTF-8 (Basic Multilingual Plane), à l’exception des éléments suivants :

   * Onglet horizontal 9
   * Flux 10 lignes
   * 12 flux de formulaire
   * 13 retour chariot
   * Utilisez le mot-clé pipe comme délimiteur pour| par ex. : barre délimiteuse
   * Suppression d’autres caractères gênants
   * Après le défilement ci-dessus, déposez toutes les lignes dont le nombre de colonnes diffère de la première ligne de données (non vide ou commentaire).
   * Prendre en charge les fichiers de rejet facultatifs pour conserver les lignes rejetées au lieu de simplement les ignorer
   * Prise en charge du dossier d’entrée récursive ; générer des dossiers de sortie de la même structure
   * Déplacer les fichiers d’entrée traités vers les sous-dossiers traités de sorte que le script ne répète pas l’opération lorsqu’il est exécuté de nouveau sur le même dossier d’entrée existant
   * Reconnaître la date dans les noms de fichier Workbench ; triez d’abord le traitement par date, puis par alpha, quel que soit le nom du dossier. Cela garantit que la séquence est correcte quel que soit le type de fichier du workbench (ecom, non-ecom) ou l’identifiant de la suite de rapports (si vous traitez plusieurs suites de rapports dans un seul jeu de données Insight).
   * Prise en charge des alertes par courrier électronique `<discoiqbr>`

