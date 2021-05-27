---
description: Instructions pour installer le profil de surveillance Data Workbench.
title: Installation du profil de surveillance
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
exl-id: 368e489c-75c9-4402-a709-a4f5987459b6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---

# Installation du profil de surveillance{#installing-the-monitoring-profile}

Instructions pour installer le profil de surveillance Data Workbench.

## Étapes d’installation {#section-d4355dbea8a447f48ab168db6ccff612}

1. Configurez une nouvelle instance de Capteur comme si elle était utilisée pour la collecte de données de page web balisée. Assurez-vous que le fichier zig.gif se trouve à la racine du document du serveur Web Sensor. Le capteur peut être exécuté sur le même hôte que les profils de moniteur. (Ceci n’est pas un problème si vous utilisez un fichier texte à cette fin.)

   >[!NOTE]
   >
   >Cette instance de Capteur doit être dédiée uniquement à la réception du trafic provenant des agents de surveillance. En outre, le Capteur peut être configuré pour s’exécuter sur un autre port si vous redéfinissez l’objectif d’un serveur web pour cette collection.

1. Dans le fichier [!DNL txlogd.conf], il existe la ligne par défaut :

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   Pour l’application Data Workbench Monitoring Profile (ou toute mise en oeuvre de page &quot;balisée&quot;), le type d’image doit être supprimé afin d’être collecté via un fichier GIF. La ligne mise à jour est la suivante :

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. Copiez la balise [!DNL insight_monitor.zip/insight_monitor_agent] dans un emplacement temporaire.
1. Mettez à jour le fichier [!DNL insight_monitor_agent.cfg] pour votre environnement. Suivez les commentaires contenus dans le fichier de configuration :

   **Le fichier de configuration Surveillance :**

   ![](assets/monitor_agent_cfg_sensor.png)

   Définissez l’emplacement où vous effectuez la collecte de toutes les informations et indiquez l’adresse URL. Il doit s’agir d’un capteur dédié et il ne doit recevoir aucun trafic, à l’exception de cette application.

   ![](assets/monitor_agent_cfg_dump.png)

   Il existe des chemins supposant qu’il existe un e : disque. Vous pouvez modifier ce chemin pour votre environnement.

   ![](assets/monitor_agent_cfg_quickcheck.png)

   Parfois, lors de l’exécution d’un profil de transformation, Data Workbench peut ne pas répondre. Cette valeur permet d’envoyer une alerte si le processus ne répond pas trois fois de suite. Il s’agit d’un moyen de réduire les alertes de faux positifs.

   ![](assets/monitor_agent_cfg_groups.png)

   C’est là que vous définissez les dimensions d’environnement et de groupe. Cela peut différer d’un hôte à l’autre.

   C’est ![](assets/monitor_agent_cfg_debug.png)ici que vous pouvez voir exactement ce que l’agent de surveillance fait en affichant les journaux d’erreurs dans ce chemin.

   ![](assets/monitor_agent_cfg_tempdb.png)

   Il s’agit d’utiliser la base de données temporaire en interne. Il peut être alerté lorsqu&#39;il atteint sa capacité. Ceci est différent de l’utilisation du disque physique.

1. Copiez le dossier *insight_monitor_agent* dans chaque hôte DPU et FSU exécutant le serveur Data Workbench. L’emplacement par défaut indiqué dans le fichier de configuration est [!DNL e:\insight_monitor_agent], mais vous pouvez le modifier.

1. Ajoutez une tâche Windows planifiée pour appeler l’agent toutes les 10 minutes (cette période est utilisée dans les calculs du taux de traitement). Le programme est [!DNL e:insight_monitor/insight_monitor_agent.exe]. L’argument est config-file e:\insight_monitor\insight_monitor.cfg. Commencez dans e:\insight_monitor. L’utilisateur exécutant la tâche doit disposer de l’autorisation de lecture/écriture [!DNL e:\insight_monitor] et de lecture de l’objet OLE Win32 [!DNL root\CIMV2] (requis pour vérifier le mode de démarrage du service de serveur Data Workbench et pour vérifier le pourcentage d’espace sur les disques locaux).

1. Vérifiez que le fichier VSL commence à se développer au fur et à mesure que les enregistrements du moniteur s’accumulent. Cela prendra du temps, car le volume de trafic sera extrêmement faible dans une petite installation (toutes les 10 minutes, l’agent n’envoie qu’un seul accès pour les données spécifiques à l’hôte, plus un accès par profil de traitement).
1. Décompressez insight_monitor.zip\profiles\Insight Historic to a temporary location.
1. Mettez à jour le nom d’hôte dans [!DNL profile.cfg], [!DNL dataset\cluster.cfg] et dans [!DNL dataset\segment export.cfg].

1. Mettez à jour les fichiers vers le répertoire des profils de Data Workbench.
1. Mettez à jour le serveur de journaux et le chemin d’accès dans [!DNL dataset\log processing.cfg] vers l’emplacement où le VSL du capteur s’accumule.
1. [] Vous pouvez éventuellement faire de même avec les profils  [!DNL Insight Profile Status] et  [!DNL Insight Server Status]. En outre, les profils d’état doivent être retraités de nuit avec une fenêtre de deux jours à la fin. Ajoutez une tâche Windows planifiée : Le programme est [!DNL e:\insight_monitor\insight_reprocess.exe]. L’argument est [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Laissez [!DNL start in] vide. Ajoutez une autre tâche planifiée pour *&quot;insight server status&quot;*. *insight_reprocess.*  nécessite un accès en lecture/écriture au traitement des  *logs.* cfgpour mettre à jour l’heure de début.

1. En outre, les profils d’état doivent être retraités de nuit avec une fenêtre de deux jours à la fin. Ajoutez une tâche Windows planifiée : Le programme est *e:\insight_monitor\insight_reprocess.exe*. L’argument est - [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Laissez *start in* vide. Ajoutez une autre tâche planifiée pour [!DNL "insight server status"]. [!DNL insight_reprocess.exe] nécessite un accès en lecture/écriture à  [!DNL log processing.cfg] pour mettre à jour l’heure de début. Vérifiez que chaque profil lit le VSL du moniteur au fur et à mesure de son accumulation. Encore une fois, cela prendra du temps, probablement des heures, à cause du volume extrêmement faible.

## Notes d’installation {#section-17722441ab0046fcbcb46b957d56230a}

* **Configuration du profil de surveillance dans un environnement** de test sous licence. Le package d’environnement de test est inclus dans votre implémentation de Data Workbench, ce qui vous permet d’installer et de configurer l’application. Si vous effectuez l’installation sur un serveur FSU ou DPU de production, vous devez configurer le serveur pour qu’il s’exécute sur un port distinct.
* **Déploiement d’un nouveau capteur spécifiquement pour le profil de surveillance**. Vous devez installer une nouvelle instance de Capteur sur le serveur exécutant le profil de surveillance. Cela s’ajoute à l’instance de production de Capteur. (L’installation de Capteur sur un serveur de production ou non-production est gratuite, et ce, spécifiquement pour le profil de surveillance.)
* **Désactivez l’agent de moniteur pendant la maintenance** de Data Workbench. Pour éviter de polluer les mesures de temps de disponibilité et de performances, vous pouvez définir le mode de démarrage du service sur manuel pour le service InsightServer (Omniture Insight Server). Une commande PowerShell pratique est *set-service -name insightserver -startuptype manual*. Redéfinissez-le sur automatique après la maintenance : *set-service -name insightserver -startuptype automatique*. Une autre option consiste à désactiver temporairement la tâche planifiée de l’agent de contrôle.
* **Les profils d’état ont besoin d’une** fenêtre de fin pour supprimer les anciens hôtes et profils ainsi que les anciens mappages de profil hôte. Cependant, si la quantité de données d’événement est si faible que Data Workbench ne les met pas en mémoire tampon, vous devrez peut-être étendre assez légèrement la taille de la fenêtre pour qu’elle soit traitée.
* **L’agent collecte l’état** détaillé global et le plus ancien à partir de Data Workbench, qui est signalé en heure d’hôte locale en supposant que les horodatages du journal des données d’événement soient en UTC (comme dans les fichiers VSL). Si les horodatages des données d’événement se trouvent dans un fuseau horaire non UTC, l’heure sera décalée dans le profil d’état du profil Insight résultant. Si **tous** de vos horodatages de données d’événement se trouvent dans le même fuseau horaire, vous pouvez ajouter ce décalage à *Profil d’aperçu Status\metrics\as of delay minutes.metric*.

* **Deux nouvelles dimensions ont été introduites pour aider les clients à regrouper leurs serveurs s’ils se trouvent dans des états** différents, tels que la production, l’évaluation, les serveurs de test et les serveurs dans d’autres états. Par exemple, si vous recherchez &quot;temps de disponibilité&quot;, vous ne regardez les serveurs qu’en mode de production. Par conséquent, la dimension Groupe n’est qu’une autre manière de regrouper arbitrairement des serveurs selon vos besoins. Par exemple, dans le fichier de configuration de surveillance, vous pouvez définir quel hôte votre service assure le service, par exemple Opérations, Développement ou Marketing.
