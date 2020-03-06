---
description: Pour détecter les erreurs du capteur dès que possible et les réparer avant qu’elles ne provoquent des problèmes majeurs ou des pannes, vous devez régulièrement surveiller vos journaux d’événements.
solution: Insight
title: Contrôle des événements administratifs
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Contrôle des événements administratifs{#monitoring-administrative-events}

Pour détecter les erreurs du capteur dès que possible et les réparer avant qu’elles ne provoquent des problèmes majeurs ou des pannes, vous devez régulièrement surveiller vos journaux d’événements.

**Fréquence recommandée :** Au moins horaire

Vous pouvez surveiller ces événements à l’aide du fichier Windows Event Viewer ou du fichier Unix Syslog et des [!DNL *.sensor-log] fichiers situés par défaut dans le [!DNL Logs] dossier du répertoire [!DNL Sensor] d’installation. Ces fichiers indiquent la présence d’erreurs au cours de la collecte des données, en particulier si un [!DNL Sensor] utilisateur ne parvient pas à se connecter à la cible [!DNL data workbench server] et commence à mettre les données en file d’attente.

## Contrôle des événements sous Windows {#section-7c0443a356af4381bf22259654f5cd17}

Sensor consigne les erreurs dans le journal des applications de l’Observateur d’événements Windows à l’aide de la source &quot;Adobe&quot;.

Les messages sont enregistrés sous la forme &quot;Informations&quot;, &quot;Avertissement&quot; ou &quot;Erreur&quot; selon leur gravité.

**Pour ouvrir l’Observateur** d’événements Windows :

* Cliquez sur **Démarrer > Panneau de configuration > Outils d’administration > Observateur** d’événements.

## Evénements de surveillance sur Unix {#section-5de3947891fb47ac88b7c855e545d54a}

Le capteur consigne les erreurs dans le [!DNL syslog] démon.

Le démon syslog écrit des messages d&#39;erreur dans les fichiers journaux en fonction des règles que vous avez spécifiées dans votre fichier syslog.conf. Les erreurs sont consignées avec les indicateurs &quot;LOG_DAEMON&quot; et &quot;LOG_NOTICE&quot; ou &quot;LOG_ERR&quot;, selon la gravité.

**Pour ouvrir le journal système Unix**

Le syslog Unix se trouve généralement dans [!DNL /var/adm/messages] ou [!DNL /var/log/messages].

Accédez à l’emplacement approprié et ouvrez le journal système.

## Présentation des formats de message {#section-a0899add30fd4b2da58a23b9e3324693}

Tous les messages du capteur contiennent la chaîne &quot;Sensor&quot; et sont numérotés pour refléter l’importance du message affiché.

| Numéro du message | Signification du message | Chaîne de message |
|---|---|---|
| 1xxx | Informations | Infos sur le capteur |
| 2xxx | Avertissement | Avertissement du capteur # |
| 3xxx | Erreur de configuration | Erreur du capteur n° |
| 4xxx | Erreur opérationnelle | Erreur du capteur n° |
| 5xxx | Erreur interne | Erreur du capteur n° |

>[!NOTE]
>
>Les avertissements (2xxx) ne sont pas utilisés actuellement. Ces numéros sont réservés à une utilisation ultérieure.

Votre outil de gestion de réseau peut être configuré pour surveiller vos messages toutes les 5 à 10 minutes pour détecter les erreurs avec la source &quot;Sensor&quot; et alerter le personnel approprié sur les problèmes qui peuvent nécessiter une intervention. Vous pouvez choisir de surveiller le système uniquement pour certains types de messages d’événement, tels que la chaîne &quot;Erreur du capteur&quot;. Vous pouvez également appliquer différentes règles aux événements prédéfinis avec les chaînes &quot;Informations sur le capteur&quot;, &quot;Avertissement sur le capteur&quot; et &quot;Erreur du capteur&quot;.

## Identification des messages importants {#section-5a20f5dc18ca4012931d194db855e54e}

Dans vos journaux d’événements, vous devez prêter une attention particulière aux messages concernant la taille de la file d’attente et y répondre immédiatement.

Par exemple, les messages tels que &quot; [!DNL Sensor Info 1012: Adobe disk queue is #% full]&quot; nécessitent une attention particulière.

## Réponse aux messages d’événement Sensor {#section-0004c4a169dc4a8882d9bd87dd326ad4}

Tableaux décrivant les événements Sensor et suggestions d’actions pour les plateformes de serveur Web prises en charge.

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
   <td colname="col1"> Informations sur le capteur 1010 : Capteur initialisé. </td> 
   <td colname="col2"> Aucune action n’est requise. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1011 : Le capteur s'est arrêté. Nombre total de clics en file d'attente ## </td> 
   <td colname="col2"> Aucune action n’est requise. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1012 : La file d'attente du disque Adobe est #% pleine </td> 
   <td colname="col2"> Ce message est consigné chaque fois que l’utilisation de la file d’attente de disque dépasse un seuil de 10 %. Si ce pourcentage continue d’augmenter, des actions doivent être entreprises avant que la file d’attente soit pleine et que les données soient perdues. Le problème le plus probable est que le capteur a cessé de communiquer avec le serveur Insight. Contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informations sur le capteur 1013 : Configuration du capteur modifiée </td> 
   <td colname="col2"> Aucune action n’est requise. Le capteur a détecté un changement dans l’un de ses fichiers de configuration et se recharge. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1014 : Problème d'ensemencement du générateur de nombres aléatoires </td> 
   <td colname="col2"> Contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1016 : Nom du fichier de configuration chargé </td> 
   <td colname="col2"> Aucune action n’est requise. Le capteur a correctement chargé le fichier de configuration répertorié. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Info 1017 : Nom du fichier d’expérience chargé </td> 
   <td colname="col2"> Aucune action n’est requise. Le capteur a correctement chargé le fichier d’expérience répertorié. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 3016 : Impossible de charger le fichier de configuration /mypath/myfile </td> 
   <td colname="col2"> Vérifiez que le fichier de configuration Sensor spécifié dans la configuration du serveur Web existe et dispose des autorisations requises pour être lu par le processus du serveur Web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensor 3017 : Impossible de charger le fichier de configuration d'expérience contrôlée /mypath/myfile </p> </td> 
   <td colname="col2"> <p>Vérifiez que le fichier d’expérience contrôlé spécifié dans txlogd.conf existe et que le processus txlogd dispose des autorisations nécessaires pour lire le fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 3018 : Impossible d'analyser les listes de filtrage de contenu. Vérification du fichier de configuration txlogd </td> 
   <td colname="col2"> Vérifiez la syntaxe des entrées ContentFilterInclude et ContentFilterExclude dans txlogd.conf. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 3023 : Échec de création du verrouillage (g_lockThrottle) </td> 
   <td colname="col2"> Contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 3024 : Échec de création du verrouillage (g_lockConfigCheck) </td> 
   <td colname="col2"> Contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 4014 : Impossible d'ouvrir la file d'attente du disque. </td> 
   <td colname="col2"> Vérifiez le nom du fichier QueueFile dans txlogd.conf et, s’il est correct, contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 4020 : Pas un fichier de file d'attente </td> 
   <td colname="col2"> Vérifiez le nom du fichier QueueFile dans txlogd.conf et, s’il est correct, contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 4021 : La file d'attente est pleine </td> 
   <td colname="col2"> Contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 4022 : Impossible de mapper le bloc mémoire de longueur &lt;x&gt; au décalage &lt;y&gt; </td> 
   <td colname="col2"> Contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 5012 : Impossible de créer le mutex. </td> 
   <td colname="col2"> Contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 5013 : Impossible d'acquérir le mutex. </td> 
   <td colname="col2"> Contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 5030 : Erreur de fourchette de frai. </td> 
   <td colname="col2"> Contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 5031 : setsid a échoué. </td> 
   <td colname="col2"> Contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 5032 : Erreur de fourchette de frai. </td> 
   <td colname="col2"> Contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 5033 : chdir a échoué. </td> 
   <td colname="col2"> Contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 5034 : Signal reçu </td> 
   <td colname="col2"> Le programme a probablement été interrompu par un signal externe. Si la source de ce signal ne peut pas être déterminée, contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 5035 : Sortie appelée depuis l’extérieur du principal </td> 
   <td colname="col2"> Contactez Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreur du capteur 5036 : txlogd est déjà en cours d'exécution </td> 
   <td colname="col2"> Une autre instance du démon txlogd est déjà en cours d'exécution. Arrêtez d’abord l’autre instance si vous souhaitez en exécuter une nouvelle. </td> 
  </tr> 
 </tbody> 
</table>

**Serveur HTTP Apache/IBM**

| Message d’événement | Action suggérée |
|---|---|
| Erreur du capteur 3015 : La directive VisualSciencesConfig est absente de httpd.conf. | Erreur de configuration. La directive VisualSciencesConfig doit être dans httpd.conf avec un paramètre qui correspond à l&#39;emplacement de txlogd.conf. |
| Erreur du capteur 3019 : vys-cookie n&#39;a pas été appelé avant vys-log. Veuillez contacter l&#39;assistance. | Contactez Adobe ClientCare. |
| Erreur du capteur 3025 : La sous-requête pointe vers elle-même | Contactez Adobe ClientCare. |

**AOL Server**

| Message d’événement | Action suggérée |
|---|---|
| Erreur du capteur 3015 : la section ns/server/[server]/module/[module] est absente du fichier de configuration AOLServer. | Erreur de configuration. Corrigez comme indiqué dans l’erreur. |
| Erreur du capteur 3019 : vys-cookie n&#39;a pas été appelé avant vys-log. Veuillez contacter l&#39;assistance. Contactez Adobe ClientCare. | Veuillez contacter l&#39;assistance. Contactez Adobe ClientCare. |
| Erreur du capteur 3020 : VisualSciencesConfig est manquant en tant que première entrée dans la section [de la section] du fichier de configuration AOLServer. | Erreur de configuration. Corrigez comme indiqué dans l’erreur. |
| Erreur du capteur 3021 : VisualSciencesConfig manque une valeur dans la section [de section] du fichier de configuration AOLServer. | Erreur de configuration. Corrigez comme indiqué dans l’erreur. |

**Serveurs Web iPlanet et Java System**

| Message d’événement | Action suggérée |
|---|---|
| Erreur du capteur 3011 : Directive Init requise. Par exemple, Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | Erreur de configuration. La directive iPlanet init est absente. |
| Erreur du capteur 3015 : config-file n&#39;est pas spécifié dans la directive iPlanet Init | Erreur de configuration. Le chemin d’accès au fichier de configuration n’était pas fourni dans la directive iPlanet Init. |
| Erreur du capteur 3019 : vys-cookie n&#39;a pas été appelé avant vys-log. Veuillez vérifier le fichier de configuration | vys-cookie doit être spécifié comme première directive NameTrans pour chaque serveur virtuel logiciel. |

