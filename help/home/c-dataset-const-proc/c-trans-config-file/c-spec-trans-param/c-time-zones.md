---
description: Le paramètre Fuseau horaire dans le fichier Transformation.cfg contrôle les dimensions temporelles, les conversions temporelles (par exemple, la définition du champ x-local-timestring) et la mise en forme de toutes les heures locales dans le profil du jeu de données.
title: Fuseaux horaires
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
exl-id: c8dc49d5-3245-428a-bfb9-42970df73d3e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# Fuseaux horaires{#time-zones}

Le paramètre Fuseau horaire dans le fichier Transformation.cfg contrôle les dimensions temporelles, les conversions temporelles (par exemple, la définition du champ x-local-timestring) et la mise en forme de toutes les heures locales dans le profil du jeu de données.

>[!NOTE]
>
>Le paramètre Fuseau horaire n’affecte pas les fonctionnalités de niveau système, telles que les horodatages dans les journaux d’état et de événement, qui sont exprimés en heure locale du système.

Le paramètre Fuseau horaire prend en charge un format de fuseau horaire indépendant du système (&quot;Heure universelle coordonnée&quot;) au format suivant :

Fuseau horaire = chaîne : UTC +hmm dstrules

Le signe (+) peut être un signe plus (+) ou un signe moins (-) et *hhmm* est le décalage par rapport à l&#39;heure UTC en heures et minutes. La variable facultative *dstrules* spécifie un ensemble de règles pour implémenter l&#39;heure d&#39;été ou une stratégie similaire de changement d&#39;horloge.

Si vous spécifiez *dstrules*, un fichier délimité par des tabulations nommé [!DNL dstrules .dst] doit être présent dans le sous-répertoire Dataset\TimeZone du jeu de données. Le fichier spécifie un ensemble de règles indépendant du fuseau horaire pour l’heure d’été. Vous pouvez avoir différents ensembles de règles pour différentes années. Le fichier [!DNL DST.dst] fourni par l&#39;Adobe dans le profil de base précise les règles américaines standard établies par le Energy Policy Act de 2005 (en vigueur depuis 2007) et les règles américaines pour les années précédentes.

Les exemples d’entrées de fuseau horaire sont répertoriés ci-dessous :

* Heure avancée de l&#39;Est des États-Unis : Fuseau horaire = chaîne : UTC -0500 DST
* Heure UTC sans décalage et sans déformation : Fuseau horaire = chaîne : UTC -0000

Lorsque ce format est utilisé, le fuseau horaire système des serveurs de l’outil de données, des outils de données et des machines [!DNL Report] ne doit pas être identique au fuseau horaire spécifié. En outre, tous les profils de jeux de données principaux sur un ordinateur serveur de l’outil de données ne doivent pas avoir le même paramètre de fuseau horaire.

L’Adobe ne recommande pas l’exécution de plusieurs profils de jeux de données sur un seul ordinateur serveur de l’outil de données ou sur une seule grappe de serveurs de l’outil de données.

Les utilisateurs des outils de données verront les données dans le fuseau horaire du profil du jeu de données au lieu de leur fuseau horaire système. L’Adobe recommande que le fuseau horaire système d’un serveur de l’outil de données soit identique à celui utilisé dans ses jeux de données.

>[!NOTE]
>
>Vous pouvez spécifier un paramètre de fuseau horaire dans le fichier [!DNL Log Processing.cfg], où il est utilisé pour les conversions temporelles pendant le traitement du journal. Pour plus d’informations sur le paramètre Fuseau horaire dans le fichier [!DNL Log Processing.cfg], voir [Fichier de configuration de traitement du journal](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).
