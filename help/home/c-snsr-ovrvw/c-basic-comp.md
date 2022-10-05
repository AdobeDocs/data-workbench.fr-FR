---
description: 'Le capteur se compose de trois composants principaux : le collecteur de données, la file d’attente du disque et l’émetteur de données.'
title: Quels sont les composants de base ?
uuid: 32e6e8d9-90ee-4db1-8883-dbdf245df26f
exl-id: aee6a601-590a-43e0-aeeb-42a4522e55c8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 0%

---

# Quels sont les composants de base ?{#what-are-basic-components}

{{eol}}

Le capteur se compose de trois composants principaux : Collecteur de données, file d’attente de disque et émetteur de données.

![](assets/Visual-Sensor.png)

## Collecteur de données {#section-f970eaff30364a3c8106d5ec9c1b5caa}

Le collecteur de données (collecteur) est un servlet de filtre NSAPI, ISAPI, J2EE ou Apache qui s’exécute dans le processus du serveur web.

Il capture les données d’événement brutes sur chaque requête HTTP que le serveur Web traite et dépose ces informations dans la file d’attente du disque. Si vous exécutez plusieurs instances d’un serveur web sur le même ordinateur, chaque instance charge sa propre instance du module collecteur ; toutefois, toutes les instances du collecteur écrivent leurs données d’événement dans la même file d’attente de disque.

## File d’attente du disque {#section-41aac77ab30e48478d1b31eac288df05}

La file d’attente du disque (file d’attente) est un fichier de file d’attente mappé sur la mémoire (premier entré, premier sorti) qui permet de mettre en mémoire tampon les données d’événement brutes collectées par Capteur, ce qui permet un stockage temporaire des données d’événement collectées sur le serveur web sur lequel il est installé.

Pour empêcher la file d’attente de se développer sans contrainte (consommant ainsi tout l’espace disque disponible), la file d’attente est conservée dans un fichier de taille fixe, ce qui signifie qu’elle ne contient que autant de données d’événement qu’elle a pu en contenir. La taille du fichier de file d’attente est configurée dans le paramètre QueueSize du fichier de configuration du capteur, txlogd.conf, lorsque le capteur est installé. Pour plus d’informations sur les paramètres txlogd.conf, voir Paramètres de fichier Txlogd.conf de Capteur.

Une fois établi, la longueur physique du fichier ne s’agrandit pas ou ne se réduit pas. Le collecteur dépose simplement les nouvelles données d’événement dans la file d’attente et l’émetteur en extrait les événements. Si le collecteur atteint la fin du fichier, il cesse d’écrire dans le fichier de file d’attente.

En règle générale, l’émetteur extrait les événements de la file d’attente aussi rapidement que le collecteur les dépose. Cependant, si la connexion entre l’émetteur et Insight Server est lente ou indisponible, la file d’attente peut se remplir d’événements non transmis. Dans cet événement, le collecteur arrête la collecte des données jusqu’à ce que l’émetteur trace la file d’attente. Informations sur les demandes que le serveur web traite pendant cette période, définitivement perdues.

**Définition de la taille de la file d’attente**

Avant d’installer Capteur, vous devez déterminer la taille de la file d’attente. Pour éviter toute perte permanente de données, il est important de créer une file d’attente suffisamment grande pour accueillir le nombre d’événements pouvant s’accumuler lors de la plus longue interruption probable de la connexion à Insight Server (c’est-à-dire un stockage suffisant pour plusieurs jours d’activité de pointe). La file d’attente doit être configurée pour contenir suffisamment de données d’événement afin que les administrateurs système aient le temps de restaurer l’accessibilité réseau au serveur Insight cible, ou de réparer ou remplacer le serveur Insight sans perdre de données. Si le capteur a échoué et qu’un fichier de file d’attente valide et accessible n’est pas disponible pour contenir les données d’événement, les données suivantes sont perdues.

>[!NOTE]
>
>Il est important que les administrateurs de chaque ordinateur sur lequel Sensor s’exécute comprennent la nature unique du fichier de file d’attente local pour s’assurer qu’ils ne le traitent pas comme un fichier journal ordinaire pouvant être supprimé, archivé ou compressé.

Adobe recommande que la file d’attente soit configurée pour contenir au moins dix (10) jours de pointe de données d’événement générées par le serveur sur lequel le capteur est installé. C&#39;est-à-dire, prenez la quantité de données d&#39;événement de n&#39;importe quel jour de pointe de l&#39;année dernière et multipliez-la par dix.

Cette recommandation suppose les éléments suivants :

* L’équipe informatique de votre entreprise surveille chaque capteur de la manière décrite dans la section Administration de Capteur de ce guide et le fait au moins une fois par jour. Si ce n&#39;est pas le cas, ce délai doit être prolongé de manière appropriée.
* L’équipe informatique de votre entreprise peut restaurer l’accessibilité réseau ou remplacer ou réparer les serveurs Insight installés dans les 72 heures. Si ce n&#39;est pas le cas, ce délai doit être prolongé de manière appropriée.
* La configuration de Capteur reste la même.
* Aucun événement externe (par exemple, une campagne marketing importante) n’entraînera une augmentation significative de la quantité de données d’événement générées par les serveurs web.

Le choix de la taille de la file d’attente dépend largement du niveau de surveillance du système souhaité, en fonction des pratiques et des politiques de votre entreprise concernant les temps de réponse et l’administration du système week-end/vacances. Comme les tailles de file d’attente sont plus grandes, Adobe recommande à votre entreprise de rendre la file d’attente aussi grande que possible.

>[!NOTE]
>
>Les tailles de fichiers de file d’attente plus grandes n’ont aucune incidence sur les performances.

Pour obtenir des recommandations supplémentaires sur le dimensionnement de la file d’attente, contactez les services de conseil d’Adobe.

## Émetteur de données {#section-2dc03d37d73b4cc6bdd5af6b346350d4}

L’émetteur est un processus indépendant (par exemple, un démon sur un ordinateur UNIX ou un service sur un ordinateur Windows) qui s’exécute sur la même machine que le serveur web.

L’émetteur lit les données d’événement de la file d’attente du disque, les compresse et les envoie via HTTP/S au serveur Insight que vous avez spécifié, où elles sont traitées et stockées dans . **.vsl** fichiers .
