---
description: Pour détecter les erreurs de Capteur le plus tôt possible et les réparer avant qu’elles ne provoquent des problèmes majeurs ou des pannes, vous devez régulièrement surveiller vos journaux d’événements.
title: Surveillance des événements administratifs
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
exl-id: 70894074-b8aa-4f6c-87d1-d0403f4c3319
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---

# Surveillance des événements administratifs{#monitoring-administrative-events}

Pour détecter les erreurs de Capteur le plus tôt possible et les réparer avant qu’elles ne provoquent des problèmes majeurs ou des pannes, vous devez régulièrement surveiller vos journaux d’événements.

**Fréquence recommandée :** Au moins une heure

Vous pouvez surveiller ces événements à l’aide du fichier Visionneuse d’événements Windows ou Syslog Unix et des fichiers [!DNL *.sensor-log] situés par défaut dans le dossier [!DNL Logs] du répertoire d’installation [!DNL Sensor]. Ces fichiers indiquent la présence d’erreurs lors de la collecte des données, en particulier si une [!DNL Sensor] ne parvient pas à se connecter à la cible [!DNL data workbench server] et commence à mettre les données en file d’attente.

## Surveillance des événements sous Windows {#section-7c0443a356af4381bf22259654f5cd17}

Le capteur consigne les erreurs dans le journal de l’application de la visionneuse d’événements Windows avec une source &quot;Adobe&quot;.

Les messages sont consignés sous la forme &quot;Informations&quot;, &quot;Avertissement&quot; ou &quot;Erreur&quot; selon leur gravité.

**Pour ouvrir la visionneuse** d’événements Windows :

* Cliquez sur **Démarrer > Panneau de Contrôle > Outils d’administration > Observateur d’événements**.

## Surveillance des événements sur Unix {#section-5de3947891fb47ac88b7c855e545d54a}

Le capteur consigne les erreurs dans le démon [!DNL syslog].

Le démon syslog écrit des messages d’erreur dans les fichiers journaux en fonction des règles que vous avez spécifiées dans votre fichier syslog.conf. Les erreurs sont consignées avec les indicateurs &quot;LOG_DAEMON&quot; et &quot;LOG_NOTICE&quot; ou &quot;LOG_ERR&quot;, selon la gravité.

**Pour ouvrir le syslog Unix**

Le syslog Unix est généralement situé dans [!DNL /var/adm/messages] ou [!DNL /var/log/messages].

Accédez à l’emplacement approprié et ouvrez le journal système.

## Présentation des formats de message {#section-a0899add30fd4b2da58a23b9e3324693}

Tous les messages de Capteur contiennent la chaîne &quot;Capteur&quot; et sont numérotés pour refléter l’importance du message affiché.

| Numéro du message | Signification du message | Chaîne de message |
|---|---|---|
| 1xxx | Informations | Infos sur le capteur |
| 2xxx | Avertissement | Numéro d’avertissement du capteur |
| 3xxx | Erreur de configuration | Numéro d’erreur du capteur |
| 4xxx | Erreur opérationnelle | Numéro d’erreur du capteur |
| 5xxx | Erreur interne | Numéro d’erreur du capteur |

>[!NOTE]
>
>Les avertissements (2xxx) ne sont actuellement pas utilisés. Ces numéros sont réservés à une utilisation ultérieure.

Votre outil de gestion du réseau peut être défini pour surveiller vos messages toutes les 5 à 10 minutes à la recherche d’erreurs avec la source &quot;Capteur&quot; et alerter le personnel approprié sur les problèmes qui peuvent nécessiter une intervention. Vous pouvez choisir de ne surveiller le système que pour certains types de messages d’événement, tels que la chaîne &quot;Erreur du capteur&quot;. Vous pouvez également appliquer différentes règles aux événements prédéfinis avec les chaînes &quot;Infos du capteur&quot;, &quot;Avertissement du capteur&quot; et &quot;Erreur du capteur&quot;.

## Identification des messages importants {#section-5a20f5dc18ca4012931d194db855e54e}

Dans vos logs d’événement, vous devez prêter une attention particulière aux messages concernant la taille de la file d’attente et y répondre immédiatement.

Par exemple, les messages tels que &quot;[!DNL Sensor Info 1012: Adobe disk queue is #% full]&quot; nécessitent une attention particulière.

## Réponse aux messages d’événement de Capteur {#section-0004c4a169dc4a8882d9bd87dd326ad4}

Tableaux décrivant les événements Sensor et suggestions d’actions pour les plateformes de serveur web prises en charge.

**Toutes les plateformes**

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Message d’événement </th> 
   <th colname="col2" class="entry"> Action suggérée </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Infos sur le capteur 1010 : Capteur initialisé. </td> 
   <td colname="col2"> Aucune action requise. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Infos sur le capteur 1011 : Capteur arrêté. Nombre total de clics en file ## </td> 
   <td colname="col2"> Aucune action requise. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Infos sur le capteur 1012 : La file d’attente du disque Adobe est #% pleine </td> 
   <td colname="col2"> Ce message est consigné chaque fois que l’utilisation de la file d’attente de disque dépasse un seuil de 10 %. Si ce pourcentage continue à croître, des actions doivent être entreprises avant que la file d’attente ne soit pleine et que les données soient perdues. Le problème le plus probable est que le capteur a cessé de communiquer avec le serveur Insight. Contactez le service à la clientèle Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Infos sur le capteur 1013 : Configuration du capteur modifiée </td> 
   <td colname="col2"> Aucune action requise. Le Capteur a détecté une modification dans l’un de ses fichiers de configuration et se recharge. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Infos sur le capteur 1014 : Problème d'ensemencement du générateur de nombres aléatoires </td> 
   <td colname="col2"> Contactez le service à la clientèle Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Infos sur le capteur 1016 : Nom du fichier de configuration chargé </td> 
   <td colname="col2"> Aucune action requise. Le Capteur a correctement chargé le fichier de configuration répertorié. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Infos sur le capteur 1017 : Nom du fichier d’expérience chargé </td> 
   <td colname="col2"> Aucune action requise. Le Capteur a correctement chargé le fichier d’expérience répertorié. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur de Capteur 3016 : Impossible de charger le fichier de configuration /mypath/myfile </td> 
   <td colname="col2"> Vérifiez que le fichier de configuration de Capteur spécifié dans la configuration du serveur web existe et dispose des autorisations requises pour être lu par le processus du serveur web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Capteur 3017 : Impossible de charger le fichier de configuration d’expérience contrôlé /mypath/myfile </p> </td> 
   <td colname="col2"> <p>Vérifiez que le fichier d’expérience contrôlé spécifié dans txlogd.conf existe et que le processus txlogd dispose des autorisations nécessaires pour lire le fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur de Capteur 3018 : Impossible d’analyser les listes de filtres de contenu. Vérification du fichier de configuration txlogd </td> 
   <td colname="col2"> Vérifiez la syntaxe des entrées ContentFilterInclude et ContentFilterExclude dans txlogd.conf. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 3023 : Échec de la création du verrouillage (g_lockThrottle) </td> 
   <td colname="col2"> Contactez le service à la clientèle Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur de Capteur 3024 : Échec de la création du verrouillage (g_lockConfigCheck) </td> 
   <td colname="col2"> Contactez le service à la clientèle Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur 4014 du capteur : Impossible d’ouvrir la file d’attente du disque. </td> 
   <td colname="col2"> Vérifiez le nom du fichier QueueFile dans txlogd.conf et, s’il est correct, contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur 4020 du capteur : Pas un fichier de file d’attente </td> 
   <td colname="col2"> Vérifiez le nom du fichier QueueFile dans txlogd.conf et, s’il est correct, contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur 4021 du capteur : La file d’attente est pleine </td> 
   <td colname="col2"> Contactez le service à la clientèle Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur 4022 du capteur : Impossible de mapper le bloc de mémoire de longueur &lt;x&gt; au décalage &lt;y&gt; </td> 
   <td colname="col2"> Contactez le service à la clientèle Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur 5012 du capteur : Impossible de créer un mutex. </td> 
   <td colname="col2"> Contactez le service à la clientèle Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur 5013 du capteur : Impossible d’acquérir le mutex. </td> 
   <td colname="col2"> Contactez le service à la clientèle Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur 5030 du capteur : Erreur de branchement. </td> 
   <td colname="col2"> Contactez le service à la clientèle Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur 5031 du capteur : setsid a échoué. </td> 
   <td colname="col2"> Contactez le service à la clientèle Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur 5032 du capteur : Erreur de branchement. </td> 
   <td colname="col2"> Contactez le service à la clientèle Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur 5033 du capteur : chdir a échoué. </td> 
   <td colname="col2"> Contactez le service à la clientèle Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur 5034 du capteur : Signal reçu </td> 
   <td colname="col2"> Le programme a probablement été arrêté par un signal externe. Si la source de ce signal ne peut pas être déterminée, contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur 5035 du capteur : Quitter appelé de l’extérieur </td> 
   <td colname="col2"> Contactez le service à la clientèle Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur 5036 du capteur : txlogd est déjà en cours d’exécution. </td> 
   <td colname="col2"> Une autre instance du démon txlogd est déjà en cours d’exécution. Arrêtez d’abord l’autre instance si vous souhaitez en exécuter une nouvelle. </td> 
  </tr> 
 </tbody> 
</table>

**Serveur HTTP Apache/IBM**

| Message d’événement | Action suggérée |
|---|---|
| Erreur de Capteur 3015 : La directive VisualSciencesConfig est absente de httpd.conf. | Il s’agit d’une erreur de configuration. La directive VisualSciencesConfig doit être dans httpd.conf avec un paramètre correspondant à l’emplacement de txlogd.conf. |
| Erreur de Capteur 3019 : vys-cookie n’a pas été appelé avant vys-log. Veuillez contacter l’assistance. | Contactez le service à la clientèle Adobe. |
| Erreur du capteur 3025 : La sous-requête renvoie vers elle-même. | Contactez le service à la clientèle Adobe. |

**Serveur AOL**

| Message d’événement | Action suggérée |
|---|---|
| Erreur de Capteur 3015 : La section ns/server/[server]/module/[module] est manquante dans le fichier de configuration AOLServer. | Il s’agit d’une erreur de configuration. Corrigez-le, comme indiqué dans l’erreur. |
| Erreur de Capteur 3019 : vys-cookie n’a pas été appelé avant vys-log. Veuillez contacter l’assistance. Contactez le service à la clientèle Adobe. | Veuillez contacter l’assistance. Contactez le service à la clientèle Adobe. |
| Erreur du capteur 3020 : VisualSciencesConfig est manquant en tant que première entrée dans la section [section] du fichier de configuration AOLServer. | Il s’agit d’une erreur de configuration. Corrigez-le, comme indiqué dans l’erreur. |
| Erreur de Capteur 3021 : Une valeur est manquante dans la section [section] de VisualSciencesConfig dans le fichier de configuration AOLServer. | Il s’agit d’une erreur de configuration. Corrigez-le, comme indiqué dans l’erreur. |

**Serveurs web iPlanet et système Java**

| Message d’événement | Action suggérée |
|---|---|
| Erreur de Capteur 3011 : directive Init requise. Par exemple, Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | Il s’agit d’une erreur de configuration. La directive iPlanet init est manquante. |
| Erreur de Capteur 3015 : config-file n’est pas spécifié dans la directive iPlanet Init | Il s’agit d’une erreur de configuration. Le chemin d’accès au fichier de configuration n’a pas été fourni dans la directive iPlanet Init. |
| Erreur de Capteur 3019 : vys-cookie n’a pas été appelé avant vys-log. Veuillez vérifier le fichier de configuration | vys-cookie doit être spécifié comme première directive NameTrans pour chaque serveur virtuel logiciel. |
