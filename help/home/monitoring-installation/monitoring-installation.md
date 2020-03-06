---
description: Instructions d’installation du profil de surveillance des outils de données.
solution: Analytics
title: Installation du profil de surveillance
topic: Data workbench
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installation du profil de surveillance{#installing-the-monitoring-profile}

Instructions d’installation du profil de surveillance des outils de données.

## Étapes d’installation {#section-d4355dbea8a447f48ab168db6ccff612}

1. Configurez une nouvelle instance Sensor comme si elle était utilisée pour la collecte de données de page Web balisée. Assurez-vous que le fichier zig.gif se trouve à la racine du document du serveur Web Sensor. Le capteur peut être exécuté sur le même hôte que les profils du moniteur. (Ceci n’est pas un problème si vous utilisez un fichier texte à cette fin.)

   >[!NOTE]
   >
   >Cette instance Sensor doit être dédiée à la réception du trafic uniquement par les agents de surveillance. En outre, le capteur peut être configuré pour s’exécuter sur un port différent si vous redéfinissez l’objectif d’un serveur Web pour cette collection.

1. Dans le [!DNL txlogd.conf] fichier se trouve la ligne par défaut :

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   Pour l’application de profil de surveillance de l’outil de données (ou toute implémentation de page &quot;balisée&quot;), le type d’image doit être supprimé pour pouvoir être collecté via un fichier GIF. La ligne mise à jour est :

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. Copiez le fichier [!DNL insight_monitor.zip/insight_monitor_agent] dans un emplacement temporaire.
1. Mettre à jour [!DNL insight_monitor_agent.cfg] le fichier pour votre environnement. Suivez les commentaires contenus dans le fichier de configuration :

   **Le fichier de configuration Monitoring :**

   ![](assets/monitor_agent_cfg_sensor.png)

   Définissez l’emplacement où vous collectez toutes les informations et indiquez l’adresse URL. Il doit s&#39;agir d&#39;un capteur dédié et ne doit recevoir aucun trafic, sauf pour cette application.

   ![](assets/monitor_agent_cfg_dump.png)

   Il existe des chemins en supposant qu’il existe un e : disque. Vous pouvez modifier ce chemin pour votre environnement.

   ![](assets/monitor_agent_cfg_quickcheck.png)

   Lors de l’exécution d’un profil de transformation, les outils de données peuvent ne pas répondre. Cette valeur vous permet d’envoyer une alerte si le processus ne répond pas trois fois de suite. Il s’agit d’un moyen de réduire les fausses alertes positives.

   ![](assets/monitor_agent_cfg_groups.png)

   C’est là que vous définissez les dimensions de l’environnement et du groupe. Cela peut être différent d’un hôte à l’autre.

   C&#39;est ici que vous ![](assets/monitor_agent_cfg_debug.png)pouvez voir exactement ce que l&#39;agent moniteur fait en affichant les journaux d&#39;erreurs dans ce chemin.

   ![](assets/monitor_agent_cfg_tempdb.png)

   Il s’agit d’utiliser la base de données temporaire en interne. Il peut être averti lorsqu&#39;il atteint sa capacité. Ceci diffère de l’utilisation du disque physique.

1. Copiez le dossier *insight_monitor_agent* sur chaque hôte DPU et FSU exécutant le serveur de l’outil de données. L’emplacement par défaut indiqué dans le fichier de configuration est [!DNL e:\insight_monitor_agent] mais vous pouvez le modifier.

1. Ajoutez une tâche planifiée Windows pour appeler l&#39;agent toutes les 10 minutes (cette période est prise en compte dans les calculs du taux de traitement). Le programme est [!DNL e:insight_monitor/insight_monitor_agent.exe]. L’argument est config-file e:\insight_monitor\insight_monitor.cfg. Commencez dans e:\insight_monitor. L&#39;utilisateur exécutant la tâche doit être autorisé à lire/écrire [!DNL e:\insight_monitor] et à lire l&#39;objet OLE Win32 [!DNL root\CIMV2] (requis pour vérifier le mode de démarrage du service de serveur de l&#39;outil de données et pour vérifier le pourcentage d&#39;espace sur les disques locaux).

1. Vérifiez que le fichier VSL commence à s’étendre au fur et à mesure que les enregistrements du moniteur s’accumulent. Cette opération prendra du temps car le volume de trafic sera extrêmement faible dans une petite installation (toutes les 10 minutes, l’agent n’envoie qu’un seul accès pour les données spécifiques à l’hôte, plus un accès par profil de traitement).
1. Décompressez insight_monitor.zip\profiles\Insight Historic to a temporary location.
1. Mettez à jour le nom d’hôte dans [!DNL profile.cfg], [!DNL [!DNL dataset\cluster.cfg]] et le [!DNL [!DNL dataset\segment export.cfg]].

1. Mettez à jour les fichiers vers le répertoire des profils de l’outil de données.
1. Mettez à jour le serveur de journaux et le chemin [!DNL dataset\log processing.cfg] vers l’emplacement où les fichiers VSL Sensor s’accumulent.
1. [Vous pouvez] faire de même avec les profils [!DNL Insight Profile Status] et [!DNL Insight Server Status]. En outre, les profils d’état doivent être retraités chaque nuit avec une fenêtre de deux jours à la fin. Ajouter une tâche planifiée Windows : Le programme est [!DNL e:\insight_monitor\insight_reprocess.exe]. L&#39;argument est [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Laissez [!DNL start in] vide. Ajoutez une autre tâche planifiée pour *&quot;Insight server status&quot;*. *insight_reprocess.exe* nécessite un accès en lecture/écriture au fichier *de traitement.cfg* pour mettre à jour l&#39;heure de début.

1. En outre, les profils d’état doivent être retraités chaque nuit avec une fenêtre de deux jours à la fin. Ajouter une tâche planifiée Windows : Le programme est *e:\insight_monitor\insight_reprocess.exe*. L&#39;argument est - [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Laissez *commencer par* vide. Ajoutez une autre tâche planifiée pour [!DNL "insight server status"]. [!DNL insight_reprocess.exe] nécessite un accès en lecture/écriture pour [!DNL log processing.cfg] mettre à jour l’heure de début. Vérifiez que chaque profil lit les VSL du moniteur au fur et à mesure de leur accumulation. Encore une fois, cela prendra du temps, probablement des heures, en raison du volume extrêmement faible.

## Notes d’installation {#section-17722441ab0046fcbcb46b957d56230a}

* **Configuration du profil de surveillance dans un environnement** de test sous licence. Le package de l’environnement de test est inclus dans votre implémentation des outils de données, ce qui vous permet d’installer et de configurer l’application. Si vous effectuez l’installation sur un serveur FSU ou DPU de production, vous devez configurer le serveur pour qu’il s’exécute sur un port distinct.
* **Déploiement d’un nouveau capteur spécifiquement pour le profil** de surveillance. Vous devez installer une nouvelle instance de Sensor sur le serveur exécutant le profil de surveillance. Ceci s’ajoute à l’instance de production de Sensor. (L’installation de Sensor sur un serveur de production ou non-production spécifique au profil de surveillance n’entraîne aucun frais supplémentaire.)
* **Désactivez l’agent moniteur pendant la maintenance** des outils de données. Pour éviter de polluer les mesures de disponibilité et de performances, vous pouvez définir le mode de démarrage du service sur manuel pour le service InsightServer (Omniture Insight Server). Une commande PowerShell pratique est *set-service -name insightserver -startuptype Manual*. Redéfinissez cette option sur Automatique après la maintenance : *set-service -name insightserver -startuptype automatique*. Une autre option consiste à désactiver temporairement la tâche planifiée de l&#39;agent de surveillance.
* **Les profils d’état ont besoin d’une fenêtre** de fin pour supprimer les anciens hôtes et profils ainsi que les anciens mappages de profil hôte. Cependant, si la quantité de données d’événement est si petite que les outils de données ne les mettent pas en mémoire tampon, vous devrez peut-être étendre un peu la taille de la fenêtre pour qu’elle soit traitée.
* **L’agent collecte l’heure globale et la plus ancienne à partir du statut** détaillé des outils de données, qui est rapporté dans le temps hôte local en supposant que les horodatages du journal des données d’événement sont en UTC (comme dans les fichiers VSL). Si l’horodatage des données d’événement se trouve dans un fuseau horaire non UTC, le décalage au moment de l’heure sera compensé dans le profil d’état du profil Insight résultant. Si **tous** vos horodatages de données d’événement se trouvent dans le même fuseau horaire, vous pouvez ajouter ce décalage au profil *Insight Status\metrics\as of delay minutes.metric*.

* **Deux nouvelles dimensions ont été introduites pour aider les clients à regrouper leurs serveurs s’ils se trouvent dans des états** différents, tels que la production, l’évaluation, les serveurs de test et les serveurs dans d’autres états. Si, par exemple, vous recherchez &quot;temps de fonctionnement&quot;, vous ne regardez que les serveurs en mode de production. Par conséquent, la dimension Groupe n’est qu’une autre manière de regrouper arbitrairement les serveurs en fonction de vos besoins. Par exemple, dans le fichier Configuration de la surveillance, vous pouvez définir l’hôte de votre service, tel que Opérations, Développement ou Marketing.
