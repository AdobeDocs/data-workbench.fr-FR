---
description: Instructions pour installer et configurer Sensor for Sun Java System Application Server Standard Edition 7 sous Windows Server 2000 ou version ultérieure.
title: Serveur Sun Java sous Windows Server 2000 ou ultérieur
uuid: 43f3eee0-2633-4bda-af6c-6c15433dd539
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 2%

---


# Serveur Sun Java sous Windows Server 2000 ou ultérieur{#sun-java-server-on-windows-server-or-later}

Instructions pour installer et configurer Sensor for Sun Java System Application Server Standard Edition 7 sous Windows Server 2000 ou version ultérieure.

Les fichiers de programme de Sensor sont inclus dans un fichier d’installation que vous obtenez du site de téléchargement de l’Adobe. Si vous ne disposez pas déjà du fichier d’installation de Sensor pour votre serveur Web particulier, téléchargez-le (ou procurez-le auprès de votre représentant d’Adobe) avant de commencer les procédures suivantes.

Sensor prend en charge les serveurs suivants sous RedHat Linux 7.x ou version ultérieure ou Sun Solaris SPARC 2.6 ou version ultérieure :

Pour installer et configurer Sensor, procédez comme suit :

## Installation des fichiers de Programme {#section-2f3e85083b4f4aa989a85997330e86ae}

Procédure d’extraction et d’installation des fichiers de programme pour Sensor sur le serveur.

1. Sur votre serveur Netscape Enterprise, iPlanet, Sun ONE ou Sun Java System Server, créez un répertoire dans lequel installer les fichiers du programme Sensor. Gardez à l’esprit que votre file d’attente de disque se trouve dans ce répertoire. Assurez-vous donc que le périphérique choisi dispose de suffisamment d’espace pour contenir une file d’attente de la taille dont vous avez besoin.

   ```
   C:\VisualSensor
   ```

1. Extrayez le contenu du fichier d&#39;installation dans le répertoire que vous venez de créer. Au cours de cette étape, Sensor installe les fichiers suivants :

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Cible Directory </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> saf_visual_sciences.dll </td> 
   <td colname="col2"> Module de chargement du collecteur. </td> 
   <td colname="col3"> <i>/usr/local/aolserver/ visual_sciences</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Programme de l'émetteur. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--OU--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Fichier de configuration du capteur. </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificat utilisé pour valider le certificat numérique présenté par Insight Server lors du processus de connexion </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le package d’installation contient un fichier de feuille de calcul appelé TestExperiment.xls. Cette feuille de calcul est un outil que les architectes utilisent pour configurer une expérience contrôlée. Sensor n’utilise pas ce fichier, il n’est donc pas nécessaire d’installer le fichier sur l’ordinateur sur lequel Sensor est en cours d’exécution (bien que vous puissiez choisir de le faire). Vous pouvez, à la place, copier le fichier vers un emplacement où vos architectes peuvent y accéder ou simplement extraire le fichier du package d&#39;installation si nécessaire. Pour plus d’informations sur l’expérimentation contrôlée, consultez le Guide des expériences contrôlées d’Insight.

## Edit the Sensor Configuration File {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Le [!DNL txlogd.conf] fichier contient les paramètres de configuration de Sensor.

Vous devez modifier ce fichier pour indiquer, entre autres, la taille et l’emplacement du fichier de file d’attente de disque, l’adresse du serveur Insight et l’identifiant qui sera joint aux données de événement produites par ce capteur.

Le fichier de configuration contient les paramètres requis et les paramètres facultatifs.

* **Les paramètres** requis sont des paramètres que vous devez spécifier lors de l’installation de Sensor. Sans ces paramètres, Sensor ne s’exécute pas correctement.
* **Les paramètres** facultatifs sont des paramètres qui, par défaut, utilisent des valeurs prédéfinies (que vous pouvez modifier) ou activent des fonctionnalités facultatives.

**Pour modifier le fichier de configuration de Sensor**

* Ouvrez le [!DNL /etc/txlogd.conf] fichier dans un éditeur de texte et définissez les paramètres requis ainsi que les paramètres facultatifs de votre choix.
* Enregistrez et fermez le fichier.

**Pour modifier le fichier de configuration de Sensor**

1. Ouvrez le [!DNL /etc/txlogd.conf] fichier dans un éditeur de texte et définissez les paramètres requis ainsi que les paramètres facultatifs de votre choix.
1. Enregistrez et fermez le fichier.

## Début de l&#39;émetteur et création de la file d&#39;attente de disque {#section-55630de65f264274aefd771da2002852}

Après avoir configuré le fichier txlogd.conf, vous pouvez début le programme de l’émetteur, l’enregistrer en tant que service Windows et créer la file d’attente du disque.

1. Dans le menu Début de Windows, sélectionnez Accessoires > Invite de commandes.
1. Dans la fenêtre d’invite de commande, accédez au répertoire dans lequel vous avez installé Sensor et exécutez la commande suivante :

   ```
   txlog /regserver
   ```

   Cette commande début l’émetteur, crée la file d’attente de disque et enregistre Sensor en tant que service Windows.

1. Pour vérifier que l’émetteur s’exécute correctement, cliquez sur Début > Panneau de Contrôle > Outils d’administration > Services. Dans la liste de service, recherchez l’entrée de Sensor et vérifiez que son état est Démarré et que son type de démarrage est Automatique. Fermez ensuite le panneau de configuration Services.
1. Pour vérifier si l’émetteur a rencontré des erreurs au cours d’un début, cliquez sur Début > Panneau de Contrôle > Outils d’administration > Visionneuse de Événements pour ouvrir la visionneuse de Événements.

   1. Dans le volet gauche de la fenêtre du lecteur de Événement, sélectionnez le journal des applications.
   1. Dans le volet de droite, recherchez des événements avec &quot;Adobe&quot; dans la colonne Source.
   1. Si vous trouvez une erreur dans &quot;Adobe&quot;, cliquez sur l&#39;erreur en doublon pour afficher la fenêtre Propriétés du Événement. Cette fenêtre fournit des informations détaillées sur l&#39;erreur.

1. Une fois que vous avez terminé d’examiner le journal des applications, fermez le lecteur de Événement.
1. Vérifiez que l’émetteur a créé la file d’attente de disque (Diskq2000.log) dans le répertoire dans lequel vous avez installé les fichiers de programme Sensor et que c’est la taille que vous avez spécifiée dans le paramètre QueueSize du fichier txlogd.conf.

   Si la file d&#39;attente n&#39;a pas été créée correctement :

   1. Examinez le fichier txtlogd.conf et vérifiez que le paramètre QueueSize est défini correctement.
   1. Vérifiez que le périphérique sur lequel vous avez installé Sensor dispose de suffisamment d’espace pour contenir un fichier de la taille spécifiée dans le paramètre QueueSize.
   1. A l’aide du panneau de configuration Services de Windows, arrêtez l’émetteur.
   1. Supprimez le fichier de file d&#39;attente.
   1. Réinscrivez Sensor en tant que service Windows : dans le menu Début de Windows, sélectionnez Accessoires > Invite de commandes. Dans la fenêtre d’invite de commande, accédez au répertoire dans lequel vous avez installé Sensor et exécutez la commande suivante :

      ```
      txlog /regserver
      ```

L&#39;émetteur est conçu pour fonctionner en continu. Si vous redémarrez l’ordinateur, l’émetteur redémarre automatiquement. Si vous devez début et arrêter l’émetteur manuellement, vous pouvez le faire à l’aide du panneau de configuration Services de Windows.

## Modification du script de démarrage {#section-19a38f27c9f44adf88f8910f5ed483a3}

Dans le fichier init.conf (par exemple, C:\Sun\AppServer7\domains\domain1\server1\config\ init.conf), ajoutez les lignes suivantes à la fin du fichier :

```
Init fn="load-modules" shlib="C:/VisualSciences/saf_visual_sciences.dll" 
funcs="vys-cookie,vys-log,vys-init,vys-content-type" 
Init fn="vys-init" config-file="C:/VisualSciences/txlogd.conf"
```

Dans le fichier obj.conf (par exemple, C:\Sun\AppServer7\domains\domain1\server1\config\ server1-obj.conf), ajoutez les lignes suivantes directement sous la `<Object name="default">` ligne existante :

```
NameTrans fn="vys-cookie" 
ObjectType fn="vys-content-type" 
AddLog fn="vys-log"
```

