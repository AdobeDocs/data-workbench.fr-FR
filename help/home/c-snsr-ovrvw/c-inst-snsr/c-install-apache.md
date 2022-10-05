---
description: Instructions sur l’installation et la configuration d’Apache Server 2.0.40, 2.0.42 ou version ultérieure, Apache Server 2.2 ou Apache Server 2.4 sous Linux, Sun Solaris ou FreeBSD.
title: Apache Server 2.0.40, 2.0.42 ou ultérieur et Apache Server 2.2 ou 2.4 sous Linux, Solaris ou FreeBSD
uuid: 3703e2c1-5b8d-4def-b146-49e59d78a669
exl-id: d5b943be-e9ca-4601-88c7-bb2bfdc0d080
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1546'
ht-degree: 2%

---

# Apache Server 2.0.40, 2.0.42 ou ultérieur et Apache Server 2.2 ou 2.4 sous Linux, Solaris ou FreeBSD{#apache-server-or-later-and-apache-server-or-on-linux-solaris-or-freebsd}

{{eol}}

Instructions sur l’installation et la configuration d’Apache Server 2.0.40, 2.0.42 ou version ultérieure, Apache Server 2.2 ou Apache Server 2.4 sous Linux, Sun Solaris ou FreeBSD.

Les fichiers de programme pour Capteur sont contenus dans un fichier d’installation que vous obtenez sur le site de téléchargement de l’Adobe. Si vous ne disposez pas déjà du fichier d’installation de Capteur pour votre serveur web en particulier, téléchargez-le (ou procurez-le auprès de votre représentant d’Adobe) avant de commencer les procédures suivantes.

Pour installer et configurer Capteur, vous devez effectuer les étapes de haut niveau suivantes :

Les serveurs Apache suivants sont pris en charge :

* Apache Server 2.0.40 s’exécutant sous RedHat Linux 7.x ou version ultérieure, ou Sun Solaris SPARC 2.6 ou version ultérieure.
* Apache Server 2.0.40, 2.0.42 ou ultérieur, Apache Server 2.2 ou Apache Server 2.4 sous Linux, Sun Solaris ou FreeBSD
* Apache Server 2.0.42 ou version ultérieure s’exécutant sous RedHat Linux 7.x ou version ultérieure, Sun Solaris SPARC 2.6 ou version ultérieure, SUSE Linux 9.x ou version ultérieure, ou FreeBSD 5.3.
* Apache Server 2.0.42 ou version ultérieure s’exécutant sous les versions 64 bits de RedHat Linux ES 4 et ES 5.
* Apache Server 2.2 s’exécutant sous RedHat Linux 7.x ou version ultérieure ou Sun Solaris SPARC 2.6 ou version ultérieure.
* Apache Server 2.4 s’exécutant sous RedHat Linux 7.x ou version ultérieure, ou Sun Solaris x86_64 ou FreeBSD

>[!NOTE]
>
>Bien que les instructions d’installation de Capteurs sur les serveurs Web exécutant les versions 2.0.40, 2.0.42 ou ultérieures (32 et 64 bits) ou 2.2 du serveur Apache soient les mêmes (sauf indication contraire dans les procédures suivantes), les fichiers d’installation pour chaque version diffèrent. Avant d’installer Capteur, assurez-vous d’avoir reçu les fichiers d’installation corrects pour les versions du serveur Apache et du système d’exploitation en cours d’exécution.

## Installation des fichiers de programme {#section-2f3e85083b4f4aa989a85997330e86ae}

Procédure d’extraction et d’installation des fichiers de programme pour Capteur.

1. Connectez-vous en tant qu’utilisateur root ou en tant qu’utilisateur disposant de l’autorisation root.
1. Décompressez et décompressez le fichier d’installation à l’aide de la commande suivante :

   * Sous Linux :

      ```
      tar -zxf installationFilename
      ```

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

   * Sous Solaris :

1. Copiez les fichiers de programme décompressés dans les répertoires identifiés dans le tableau suivant :

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Répertoire cible </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_Visual_sciences.so </td> 
   <td colname="col2"> Module de chargement du collecteur. </td> 
   <td colname="col3"> <i> IBMHttpServer/modules</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Le programme de l'émetteur. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--OR--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Le fichier de configuration de Capteur. </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificat utilisé pour valider le certificat numérique qu’Insight Server présente pendant le processus de connexion </td> 
   <td colname="col3"> <i>/usr/local/visuel_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le package d’installation contient un fichier de feuille de calcul appelé TestExperiment.xls. Cette feuille de calcul est un outil que les architectes utilisent pour configurer une expérience contrôlée. Sensor n’utilise pas ce fichier. Il n’est donc pas nécessaire d’installer le fichier sur l’ordinateur sur lequel Sensor est exécuté (bien que vous puissiez choisir de le faire). Vous pouvez plutôt copier le fichier vers un emplacement accessible par vos architectes ou simplement extraire le fichier du package d’installation, si nécessaire. Pour plus d’informations sur l’expérimentation contrôlée, consultez le guide des expériences contrôlées Insight .

**Autorisations sur les fichiers de programme**

>[!NOTE]
>
>Des autorisations incorrectes sur les fichiers de programme entraînent la plupart des problèmes lors de l’installation de Capteur. Veillez à définir les autorisations exactement comme indiqué dans cette section.
>
>Par défaut, les fichiers de programme du fichier tar disposent des autorisations suivantes. Selon la configuration de votre système, ces paramètres peuvent être modifiés (non masqués) lors de l’extraction des fichiers. Pour réinitialiser les autorisations aux paramètres par défaut recommandés, utilisez les commandes chmod ci-dessous. Vérifiez que les répertoires dans lesquels vous avez installé les fichiers permettent au moins ce niveau d’accès.

| Fichier | Autorisations par défaut | chmod, commande |
|---|---|---|
| mod_Visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- r— r— | chmod 664 |
| trust_ca_cert.pem | rw- r— r— | chmod 664 |

## Activation de la journalisation sur le même serveur {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Cette procédure vous permet de vous connecter au serveur Sametime.

1. Utilisez le client administrateur Lotus Domino pour vous connecter au serveur Lotus Domino qui exécute Sametime.
1. Dans l’administrateur Lotus Domino, cliquez sur l’onglet Fichiers , puis double-cliquez sur Configuration en temps réel - stconfig.nsf pour ouvrir le fichier de configuration en temps réel.
1. Dans le fichier de configuration en même temps, ouvrez le formulaire Services de la communauté et double-cliquez n’importe où sur le formulaire pour passer en mode d’édition.
1. Définissez l’indicateur de journalisation de conversation sur &quot;strict&quot; et le type de service de capture sur &quot;0x1000&quot;.
1. Enregistrez et fermez le formulaire Services de communauté, puis fermez le fichier de configuration en même temps.
1. Redémarrez le serveur Sametime.

## Modification du fichier de configuration du capteur {#section-de0eb4a646394b61abb6cd5a2b706de0}

Le [!DNL txlogd.conf] contient les paramètres de configuration de Capteur.

Vous devez modifier ce fichier pour indiquer, entre autres, la taille et l’emplacement du fichier de file d’attente du disque, l’adresse du serveur Insight et l’identifiant qui sera joint aux données d’événement générées par ce capteur.

Le fichier de configuration contient les paramètres requis et les paramètres facultatifs.

* **Paramètres requis** sont des paramètres que vous devez spécifier lors de l’installation de Capteur. Sans ces paramètres, Capteur ne s’exécute pas correctement.
* **Paramètres facultatifs** sont des paramètres qui activent par défaut des valeurs prédéfinies (que vous pouvez modifier) ou des fonctionnalités facultatives.

**Modification du fichier de configuration du capteur**

* Ouvrez le [!DNL /etc/txlogd.conf] dans un éditeur de texte et définissez les paramètres requis ainsi que les paramètres facultatifs souhaités.
* Enregistrez le fichier, puis fermez-le.

**Modification du fichier de configuration du capteur**

1. Ouvrez le [!DNL /etc/txlogd.conf] dans un éditeur de texte et définissez les paramètres requis ainsi que les paramètres facultatifs souhaités.
1. Enregistrez le fichier, puis fermez-le.

## Démarrez l’émetteur et créez la file d’attente du disque {#section-55630de65f264274aefd771da2002852}

Après avoir configuré le fichier txlogd.conf, vous pouvez démarrer le programme d&#39;émetteur, l&#39;enregistrer en tant que service Windows et créer la file d&#39;attente du disque.

1. Si le répertoire dans lequel se trouve la file d’attente de disque n’existe pas déjà, créez-le. Assurez-vous que le répertoire fournit au module collecteur et au programme d’émetteur un accès en lecture/écriture au fichier.

   Pour plus d’informations sur les autorisations requises par les fichiers de file d’attente de disque, voir Autorisations des fichiers UNIX de Capteur.
1. Sur l’ordinateur sur lequel Sensor est installé, exécutez la commande suivante pour démarrer l’émetteur :

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * L&#39;option &quot;i&quot; de cette commande démarre l&#39;émetteur en &quot;mode interactif&quot;. Ce mode affiche les messages de l&#39;émetteur à l&#39;écran et permet également d&#39;interagir avec l&#39;émetteur à l&#39;aide des commandes du clavier.
   * L&#39;option &quot;c&quot; demande à l&#39;émetteur de créer la file d&#39;attente du disque.
   * L’option &quot;f&quot; spécifie l’emplacement du fichier de configuration.

   Pour plus d’informations sur les options que vous pouvez utiliser lors du démarrage de l’émetteur, voir Options de ligne de commande de l’émetteur de Capteur.

1. Vérifiez que l’émetteur a créé la file d’attente du disque à l’emplacement spécifié dans le paramètre QueueFile et à la taille spécifiée dans le paramètre QueueSize .
1. Si la file d&#39;attente n&#39;a pas été correctement créée, tapez Ctrl+C pour arrêter l&#39;émetteur, puis procédez comme suit :

   1. Examinez le fichier txtlogd.conf et vérifiez que les paramètres QueueFile et QueueSize sont correctement définis.
   1. Vérifiez que le périphérique auquel la file d’attente de disque est affectée est opérationnel et dispose de suffisamment d’espace disponible pour contenir un fichier de la taille spécifiée dans le paramètre QueueSize .
   1. Effectuez les corrections nécessaires et répétez cette procédure.

## Ajout du collecteur au serveur web {#section-c5b83ae4ebce430aa764f951e849b333}

Pour les serveurs HTTP IBM, le collecteur est un objet partagé dynamique que vous chargez dans le processus de votre serveur web.

Pour ajouter le collecteur à votre serveur web, vous devez modifier le fichier httpd.conf comme décrit ci-dessous, puis redémarrer votre serveur web.

Si Capteur capture des données pour plusieurs serveurs Web sur l’ordinateur serveur, vous devez effectuer la procédure suivante pour chaque serveur Web.

1. A l’aide d’un éditeur de texte, ouvrez le fichier httpd.conf pour le serveur web dont le Capteur d’événements capture les données.
1. Ajoutez les deux lignes suivantes à la fin du fichier :

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Ces lignes sont sensibles à la casse. Saisissez-les exactement comme ils apparaissent ci-dessus.

1. Redémarrez le processus du serveur web (il n’est pas nécessaire de redémarrer l’ensemble de l’ordinateur serveur, il suffit de redémarrer le processus du serveur web). Le collecteur est chargé avec le serveur web et commence à collecter les données d’événement et à les écrire dans la file d’attente du disque.

## Test du capteur {#section-0dae181ef8884f10a57f6cfda8500969}

Vérifiez que le collecteur collecte les données d’événement et que l’émetteur les transmet au serveur Insight cible.

>[!NOTE]
>
>Pour vérifier que l’émetteur peut envoyer des données d’événement au serveur Insight, assurez-vous que le serveur Insight cible est installé et en cours d’exécution avant de lancer le test suivant.

1. Si l&#39;émetteur n&#39;est pas déjà en cours d&#39;exécution, redémarrez-le à l&#39;aide de la commande suivante :

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Ouvrez un navigateur (sur n’importe quel ordinateur) et demandez une page au serveur Web sur lequel le Capteur est en cours d’exécution (veillez à sélectionner une page que le Capteur surveille).
1. Après avoir émis la requête, vérifiez dans la console de l’émetteur les messages indiquant qu’il envoie des données d’événement au serveur Insight cible.
1. Si le capteur ne transmet pas correctement les données, vérifiez que :

   * Le serveur Insight cible est en cours d’exécution.
   * Les paramètres ServerAddress et ServerPort sont correctement définis dans txtlogd.conf. Si vous avez spécifié ServerAddress à l’aide d’un nom de serveur, essayez plutôt d’utiliser son adresse IP numérique.
   * La valeur du paramètre CertName correspond exactement au nom commun qui apparaît sur le certificat numérique du serveur Insight cible.

## Ajout de l’émetteur au script de démarrage du système {#section-19a38f27c9f44adf88f8910f5ed483a3}

Informations sur le chargement automatique de l’émetteur dans le script de démarrage du système.

Pour vous assurer que l&#39;émetteur se charge automatiquement au redémarrage de l&#39;ordinateur du serveur web, ajoutez la commande suivante (qui lance l&#39;émetteur) au script de démarrage de votre système :

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Cette commande lance l&#39;émetteur comme démon. Les messages d&#39;exploitation et d&#39;erreur générés par l&#39;émetteur sont écrits dans syslog.
