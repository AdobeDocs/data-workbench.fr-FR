---
description: Informations sur les commandes de démarrage de l’émetteur Sensor pour UNIX et Windows.
title: Options de ligne de commande de l’émetteur du capteur
uuid: 8d077d76-a709-494e-a176-07ca3e761662
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Options de ligne de commande de l’émetteur du capteur{#sensor-transmitter-command-line-options}

Informations sur les commandes de démarrage de l’émetteur Sensor pour UNIX et Windows.

## Commande de démarrage pour UNIX {#section-e8e7a6e62971499ba5f633d896590949}

Pour démarrer l’émetteur Sensor sur une racine UNIX, utilisez la commande suivante :

```
txlogd -f configFileName
```

où configFileName est le nom qualifié complet du fichier de configuration de l’émetteur (txlogd.conf).

Par défaut, l’émetteur s’exécute en tant que processus d’arrière-plan (un démon) et écrit des messages opérationnels sur syslog.

Vous trouverez ci-dessous la liste complète des commutateurs de ligne de commande pour txlogd :

| Basculer | Description |
|---|---|
| -f | Spécifie le nom qualifié complet du fichier de configuration (txlogd.conf). Si vous ne spécifiez pas ce commutateur, l’émetteur recherche txlogd.conf dans le répertoire actuel. |
| -n | Démarre l’émetteur en mode interactif (et non en tant que processus d’arrière-plan). |
| -i | Démarre l’émetteur en mode interactif et dirige la sortie de débogage vers stdout. |
| -d | Démarre l’émetteur en tant que processus d’arrière-plan et dirige la sortie de débogage vers txlogd-debug.log dans le répertoire actuel. |
| -c | Démarre l’émetteur et crée le fichier de file d’attente de disque s’il n’existe pas. Si la file d&#39;attente de disque existe déjà, ce paramètre est ignoré. |
| -x | Démarre l’émetteur et le fait quitter une fois qu’il a transmis le dernier paquet de la file d’attente du disque. Vous pouvez utiliser cette option pour vider la file d’attente en vue d’une opération administrative, telle que la création d’un fichier de file d’attente. |

## Commande de démarrage pour Windows {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

Pour démarrer Sensor et l’enregistrer en tant que service sur un système Windows, utilisez la commande suivante :

```
txlog /regserver
```

