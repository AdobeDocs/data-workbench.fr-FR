---
description: 'Sensor se compose de trois composants principaux : le collecteur de données, la file d’attente des disques et l’émetteur de données.'
title: Eléments de base
uuid: 32e6e8d9-90ee-4db1-8883-dbdf245df26f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Eléments de base{#what-are-basic-components}

Le capteur se compose de trois éléments principaux : Collecteur de données, file d’attente de disque et émetteur de données.

![](assets/Visual-Sensor.png)

## Collecteur de données {#section-f970eaff30364a3c8106d5ec9c1b5caa}

Le collecteur de données (collecteur) est une servlet de filtre NSAPI, ISAPI, J2EE ou Apache qui s’exécute dans le processus du serveur Web.

Il capture les données d’événement brutes relatives à chaque requête HTTP que le serveur Web traite et consigne ces informations dans la file d’attente du disque. Si vous exécutez plusieurs instances d’un serveur Web sur le même ordinateur, chaque instance charge sa propre instance du module collecteur ; toutefois, toutes les instances du collecteur écrivent leurs données d’événement dans la même file d’attente de disque.

## File d&#39;attente du disque {#section-41aac77ab30e48478d1b31eac288df05}

La file d’attente de disque (file d’attente) est un fichier FIFO (premier entré, premier sorti) de mémoire mappée qui protège les données d’événement brutes collectées par Sensor, fournissant un stockage temporaire pour les données d’événement collectées sur le serveur Web sur lequel il est installé.

Pour éviter que la file d’attente ne se développe sans contrainte (consommant ainsi tout l’espace disque disponible), la file d’attente est conservée dans un fichier de taille fixe, ce qui signifie qu’elle ne contient que la quantité de données d’événement qu’elle a pu conserver. La taille du fichier de file d’attente est configurée dans le paramètre QueueSize du fichier de configuration Sensor, txlogd.conf, lorsque le capteur est installé. Pour plus d’informations sur les paramètres txlogd.conf, voir Paramètres du fichier Sensor Txlogd.conf.

Une fois établi, la longueur physique du fichier ne s’agrandit ni ne diminue. Le collecteur dépose simplement les nouvelles données d’événement dans la file d’attente et l’émetteur en extrait les événements. Si le collecteur atteint la fin du fichier, il arrête d’écrire dans le fichier de file d’attente.

En règle générale, l’émetteur extrait les événements de la file d’attente dès que le collecteur les dépose. Cependant, si la connexion entre l’émetteur et Insight Server est lente ou indisponible, la file d’attente peut être remplie avec des événements non transmis. Dans ce cas, le collecteur arrête de collecter les données jusqu’à ce que l’émetteur trace la file d’attente. Informations sur les requêtes que le serveur Web traite pendant cette période sont définitivement perdues.

**Détermination de la taille de la file d’attente**

Avant d’installer Sensor, vous devez déterminer la taille de la file d’attente. Pour éviter une perte permanente de données, il est important de créer une file d’attente suffisamment grande pour contenir le nombre d’événements pouvant s’accumuler lors de la plus longue interruption probable de la connexion au serveur Insight (c’est-à-dire un stockage suffisant pour plusieurs jours d’activité maximale). La file d’attente doit être configurée pour contenir suffisamment de données d’événement afin que les administrateurs système aient le temps de restaurer l’accessibilité réseau au serveur Insight cible, ou de réparer ou de remplacer le serveur Insight sans perdre de données. Si le capteur a échoué et qu’un fichier de file d’attente valide et accessible n’est pas disponible pour stocker les données d’événement, les données suivantes sont perdues.

>[!NOTE]
>
>Il est important que les administrateurs de chaque machine sur laquelle Sensor s’exécute comprennent la nature unique du fichier de file d’attente local afin de s’assurer qu’ils ne le traitent pas comme un fichier journal ordinaire pouvant être supprimé, archivé ou compressé.

Adobe recommande que la file d’attente soit configurée pour contenir au moins dix (10) jours de pointe de données d’événement produites par le serveur sur lequel le capteur est installé. C&#39;est-à-dire, prenez la quantité de données d&#39;événement de n&#39;importe quel jour de pointe de l&#39;année dernière et multipliez-la par dix.

Cette recommandation suppose les éléments suivants :

* L’équipe Technologie de l’information de votre entreprise surveille chaque capteur de la manière décrite dans la section Administration du capteur du présent guide et le fait au moins une fois par jour. Si tel n&#39;est pas le cas, ce délai devrait être prolongé de manière appropriée.
* L’équipe Technologie de l’information de votre entreprise peut restaurer l’accessibilité du réseau ou remplacer ou réparer les serveurs Insight installés dans les 72 heures. Si tel n&#39;est pas le cas, ce délai devrait être prolongé de manière appropriée.
* La configuration de Sensor reste la même.
* Aucun événement externe (par exemple, une campagne marketing de grande envergure) n’entraîne une augmentation significative de la quantité de données d’événement générées par les serveurs Web.

Le choix de la taille de la file d’attente dépend en grande partie du niveau souhaité de surveillance du système à la lumière des pratiques et des politiques de votre entreprise concernant les temps de réponse et l’administration du système de week-end/vacances. Comme les files d’attente sont plus volumineuses, Adobe conseille à votre entreprise de les agrandir au maximum.

>[!NOTE]
>
>Des fichiers de file d’attente plus volumineux n’ont aucune incidence sur les performances.

Pour plus d’informations sur le dimensionnement de la file d’attente, contactez les services de conseil Adobe.

## Émetteur de données {#section-2dc03d37d73b4cc6bdd5af6b346350d4}

L’émetteur est un processus indépendant (par exemple, un démon sur un ordinateur UNIX ou un service sur un ordinateur Windows) qui s’exécute sur le même ordinateur que le serveur Web.

L’émetteur lit les données d’événement de la file d’attente du disque, les compresse et les envoie via HTTP/S au serveur Insight que vous avez spécifié, où elles sont traitées et stockées dans les fichiers **.vsl** .
