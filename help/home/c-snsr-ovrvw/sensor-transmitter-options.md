---
description: Informations sur les commandes de démarrage de l’émetteur Capteur pour UNIX et Windows.
title: Options de ligne de commande d’émetteur de Capteur
uuid: 8d077d76-a709-494e-a176-07ca3e761662
exl-id: f4b27859-8fab-42cd-bad0-b32f87764668
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 6%

---

# Options de ligne de commande d’émetteur de Capteur{#sensor-transmitter-command-line-options}

{{eol}}

Informations sur les commandes de démarrage de l’émetteur Capteur pour UNIX et Windows.

## Commande de démarrage pour UNIX {#section-e8e7a6e62971499ba5f633d896590949}

Pour démarrer l’émetteur Capteur sur une tige UNIX, utilisez la commande suivante :

```
txlogd -f configFileName
```

où configFileName est le nom qualifié complet du fichier de configuration de l&#39;émetteur (txlogd.conf).

Par défaut, l&#39;émetteur s&#39;exécute en tant que processus d&#39;arrière-plan (un démon) et écrit les messages opérationnels sur syslog.

Voici une liste complète des commutateurs de ligne de commande pour txlogd :

| Basculer | Description |
|---|---|
| -f | Indique le nom qualifié complet du fichier de configuration (txlogd.conf). Si vous ne spécifiez pas ce commutateur, l’émetteur recherche txlogd.conf dans le répertoire actuel. |
| -n | Démarre l&#39;émetteur en mode interactif (et non en tant que processus d&#39;arrière-plan). |
| -i | Démarre l’émetteur en mode interactif et redirige la sortie de débogage vers stdout. |
| -d | Démarre l’émetteur en tant que processus d’arrière-plan et redirige la sortie de débogage vers txlogd-debug.log dans le répertoire actuel. |
| -c | Démarre l’émetteur et crée le fichier de file d’attente du disque s’il n’existe pas. Si la file d’attente du disque existe déjà, ce paramètre est ignoré. |
| -x | Démarre l’émetteur et le fait quitter une fois qu’il a transmis le dernier paquet de la file d’attente du disque. Vous pouvez utiliser cette option pour vider la file d’attente en vue d’une opération d’administration, telle que la création d’un nouveau fichier de file d’attente. |

## Commande de démarrage pour Windows {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

Pour démarrer Capteur et l’enregistrer en tant que service sur un système Windows, utilisez la commande suivante :

```
txlog /regserver
```
