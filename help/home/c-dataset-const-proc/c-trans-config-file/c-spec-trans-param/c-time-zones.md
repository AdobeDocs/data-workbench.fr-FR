---
description: Le paramètre Fuseau horaire du fichier Transformation.cfg contrôle les dimensions temporelles, les conversions temporelles (par exemple, la définition du champ de chaîne x-local) et la mise en forme de toutes les heures locales dans le profil du jeu de données.
title: Fuseaux horaires
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
exl-id: c8dc49d5-3245-428a-bfb9-42970df73d3e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# Fuseaux horaires{#time-zones}

Le paramètre Fuseau horaire du fichier Transformation.cfg contrôle les dimensions temporelles, les conversions temporelles (par exemple, la définition du champ de chaîne x-local) et la mise en forme de toutes les heures locales dans le profil du jeu de données.

>[!NOTE]
>
>Le paramètre Fuseau horaire n’a aucune incidence sur les fonctionnalités de niveau système, telles que les horodatages dans les journaux d’état et d’événement, qui sont exprimés en heure locale du système.

Le paramètre Fuseau horaire prend en charge un format de fuseau horaire indépendant du système (&quot;Heure universelle coordonnée&quot;) au format suivant :

Fuseau horaire = chaîne : Règles UTC +hmm

Le signe (+) peut être un signe plus (+) ou un signe moins (-) et *hhmm* est le décalage par rapport à UTC en heures et en minutes. La variable facultative *dstrules* spécifie un ensemble de règles pour mettre en oeuvre l’heure d’été ou une stratégie de changement d’heure similaire.

Si vous spécifiez *des règles*, un fichier délimité par des tabulations nommé [!DNL dstrules .dst] doit être présent dans le sous-répertoire Dataset\TimeZone du profil de jeu de données. Le fichier spécifie un jeu de règles indépendant des fuseaux horaires pour l’heure d’été. Vous pouvez avoir différents ensembles de règles pour différentes années. Le fichier [!DNL DST.dst] fourni par Adobe dans le profil de base spécifie les règles américaines standard établies par le Energy Policy Act de 2005 (en vigueur depuis 2007) et les règles américaines des années précédentes.

Les exemples d’entrées de fuseau horaire sont répertoriés ci-dessous :

* Heure d’été de l’Est des États-Unis : Fuseau horaire = chaîne : UTC -0500 DST
* Heure UTC sans décalage et sans contours : Fuseau horaire = chaîne : UTC-0000

Lorsque ce format est utilisé, le fuseau horaire système des machines Data Workbench, Data Workbench et [!DNL Report] ne doit pas être identique au fuseau horaire spécifié. En outre, tous les profils de jeu de données principaux sur un serveur Data Workbench n’ont pas besoin de définir le même fuseau horaire.

Adobe ne recommande pas d’exécuter plusieurs profils de jeux de données sur une seule machine de serveur Data Workbench ou grappe de serveurs Data Workbench.

Les utilisateurs de Data Workbench verront les données dans le fuseau horaire du profil du jeu de données au lieu de leur fuseau horaire système. Adobe recommande que le fuseau horaire système d’un serveur Data Workbench soit identique à celui utilisé dans ses jeux de données.

>[!NOTE]
>
>Vous pouvez spécifier un paramètre de fuseau horaire dans le fichier [!DNL Log Processing.cfg], où il est utilisé pour les conversions de l’heure lors du traitement du journal. Pour plus d’informations sur le paramètre Fuseau horaire dans le fichier [!DNL Log Processing.cfg], voir [Fichier de configuration de traitement du journal](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).
