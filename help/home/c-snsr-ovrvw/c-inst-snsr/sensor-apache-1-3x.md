---
description: Instructions détaillées pour l’installation et la configuration de Sensor pour Apache Server 1.3.x sur RedHat Linux 7.x ou version ultérieure, SUSE Linux 9.x ou version ultérieure, Sun Solaris SPARC 2.6 ou version ultérieure, Sun Solaris x86 9 ou version ultérieure, FreeBSD 4 ou version ultérieure, ou Mac OS X PowerPC.
title: Apache Server 1.3.x sous Linux, Sun Solaris, FreeBSD ou Mac OS X
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Apache Server 1.3.x sous Linux, Sun Solaris, FreeBSD ou Mac OS X{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

Instructions détaillées pour l’installation et la configuration de Sensor pour Apache Server 1.3.x sur RedHat Linux 7.x ou version ultérieure, SUSE Linux 9.x ou version ultérieure, Sun Solaris SPARC 2.6 ou version ultérieure, Sun Solaris x86 9 ou version ultérieure, FreeBSD 4 ou version ultérieure, ou Mac OS X PowerPC.

Les fichiers programme de Sensor sont compressés dans un fichier d’installation que vous obtenez du site de téléchargement d’Adobe. Si vous ne disposez pas déjà du fichier d’installation de Sensor pour votre serveur Web particulier, téléchargez-le (ou obtenez-le auprès de votre représentant Adobe) avant de commencer les procédures suivantes.

Pour installer et configurer Sensor, vous devez effectuer les étapes de haut niveau suivantes :

## Installation des fichiers du programme {#section-aae323e252394212bf4096d65fdd280c}

Instructions pour extraire et installer les fichiers programme pour Sensor sur le serveur.

1. Connectez-vous en tant qu’utilisateur root ou en tant qu’utilisateur disposant de l’autorité racine.
1. Décompressez et décompressez le fichier d’installation à l’aide de la commande suivante :

   * Sous Linux :

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * Sous Solaris :

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

1. Copiez les fichiers de programme décompressés dans les répertoires identifiés dans le tableau suivant :

<table id="table_A97CF630633C4543A742D96C302D1138"> 
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
   <td colname="col2"> Module de chargement du collecteur </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Le programme transmetteur </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OU-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Fichier de configuration de Sensor </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificat utilisé pour valider le certificat numérique présenté par Insight Server pendant le processus de connexion </td> 
   <td colname="col3"> /usr/local/Visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le package d’installation contient un fichier de feuille de calcul appelé TestExperiment.xls. Cette feuille de calcul est un outil que les architectes utilisent pour configurer une expérience contrôlée. Sensor n’utilise pas ce fichier, il n’est donc pas nécessaire d’installer le fichier sur l’ordinateur sur lequel Sensor est en cours d’exécution (bien que vous puissiez choisir de le faire). Vous souhaiterez peut-être copier le fichier vers un emplacement accessible par vos architectes ou simplement extraire le fichier du package d’installation, le cas échéant. Pour plus d&#39;informations sur l&#39;expérimentation contrôlée, consultez le Guide des expériences contrôlées Insight.

**Autorisations sur les fichiers du programme**

Des autorisations incorrectes sur les fichiers programme provoquent la plupart des problèmes rencontrés lors de l’installation de Sensor.

Veillez à définir les autorisations exactement comme indiqué dans cette section.

Par défaut, les fichiers programme du fichier tar possèdent les autorisations suivantes. Selon la configuration de votre système, ces paramètres peuvent être modifiés (non masqués) lors de l’extraction des fichiers. Pour réinitialiser les autorisations sur les paramètres par défaut recommandés, utilisez les commandes chmod ci-dessous. Vérifiez que les répertoires dans lesquels vous avez installé les fichiers permettent au moins ce niveau d&#39;accès.

| Fichier | Autorisations par défaut | chmod, commande |
|---|---|---|
| mod_Visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

## Modification du fichier de configuration de Sensor {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

Le [!DNL txlogd.conf] fichier contient les paramètres de configuration de Sensor.

Vous devez modifier le fichier pour indiquer, entre autres, la taille de la file d’attente du disque, l’adresse du serveur Insight et l’ID qui sera joint aux données produites par ce capteur.

Le fichier de configuration contient les paramètres obligatoires et facultatifs.

* Les paramètres requis sont des paramètres que vous devez spécifier lorsque vous installez Sensor. Sans ces paramètres, Sensor ne fonctionne pas correctement.
* Les paramètres facultatifs sont des paramètres qui, par défaut, utilisent des valeurs prédéfinies (que vous pouvez modifier) ou activent des fonctionnalités facultatives.

Pour modifier le fichier de configuration de Sensor

1. Ouvrez le fichier /etc/txlogd.conf dans un éditeur de texte et définissez les paramètres requis ainsi que les paramètres facultatifs de votre choix.
1. Enregistrez et fermez le fichier.

## Démarrage de l&#39;émetteur et création de la file d&#39;attente du disque {#section-a453d912ec3d47aa8e40ccacf527119d}

Instructions pour créer la file d’attente de disque après avoir configuré le fichier txlogd.conf.

1. Si le répertoire dans lequel se trouve la file d&#39;attente de disque n&#39;existe pas déjà, créez-le. Assurez-vous que le répertoire fournit à la fois le module collecteur et le programme émetteur l&#39;accès en lecture/écriture au fichier.
1. Sur l’ordinateur sur lequel Sensor est installé, exécutez la commande suivante pour démarrer l’émetteur :

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * L’option &quot;i&quot; de cette commande démarre l’émetteur en mode interactif. Ce mode affiche les messages d’émetteur à l’écran et vous permet également d’interagir avec l’émetteur à l’aide des commandes du clavier.
   * L’option &quot;c&quot; indique à l’émetteur de créer la file d’attente du disque.
   * L’option &quot;f&quot; spécifie l’emplacement du fichier de configuration.

1. Vérifiez que l’émetteur a créé la file d’attente du disque à l’emplacement spécifié dans le paramètre QueueFile et à la taille spécifiée dans le paramètre QueueSize.
1. Si la file d’attente n’a pas été créée correctement, tapez Ctrl+C pour arrêter l’émetteur, puis procédez comme suit :

   1. Examinez le fichier txtlogd.conf et vérifiez que les paramètres QueueFile et QueueSize sont définis correctement.
   1. Vérifiez que le périphérique auquel la file d&#39;attente de disque est affectée est opérationnel et dispose de suffisamment d&#39;espace disponible pour stocker un fichier de la taille spécifiée dans le paramètre QueueSize.
   1. Effectuez les corrections nécessaires et répétez cette procédure.

## Ajout du collecteur au serveur Web {#section-a7fb6425956f4f518ae3a7db091b33d2}

Pour les serveurs Apache, le collecteur est un objet partagé dynamique que vous chargez dans le processus de votre serveur Web.

Pour ajouter le collecteur à votre serveur Web, vous devez modifier le fichier httpd.conf comme décrit ci-dessous et redémarrer votre serveur Web.

Si Sensor capture des données pour plusieurs serveurs Web sur l’ordinateur serveur, vous devez effectuer la procédure suivante pour chaque serveur Web.

1. A l’aide d’un éditeur de texte, ouvrez le [!DNL httpd.conf] fichier pour le serveur Web dont Sensor capture les événements.
1. Ajoutez les lignes suivantes à la fin du fichier :

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >Ces lignes sont sensibles à la casse. Tapez-les exactement comme ils apparaissent ci-dessus.

1. Redémarrez le serveur Web. Le collecteur est chargé avec le serveur Web et commencera à collecter les données d’événement et à les écrire dans la file d’attente du disque.

## Test du capteur {#section-83d9f60b39a6474f9c76bee3e19b2575}

Démarrez l’émetteur et vérifiez qu’il peut se connecter au serveur Insight et lui transmettre les données d’événement.

>[!NOTE]
>
>Pour vérifier que l’émetteur peut envoyer des données d’événement au serveur Insight, assurez-vous que le serveur Insight cible est installé et en cours d’exécution avant de commencer le test suivant.

1. Si l’émetteur n’est pas en cours d’exécution, redémarrez-le à l’aide de la commande suivante :

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Ouvrez un navigateur (sur n’importe quel ordinateur) et demandez une page au serveur Web sur lequel Sensor est en cours d’exécution (veillez à sélectionner une page que Sensor surveille).
1. Une fois la requête émise, vérifiez dans la console de l’émetteur les messages indiquant qu’elle envoie des données d’événement au serveur Target Insight.
1. Si Sensor ne transmet pas correctement les données, vérifiez que :

   * Le serveur Insight cible est en cours d’exécution.
   * Les paramètres [!DNL ServerAddress] et [!DNL ServerPort] sont définis correctement dans [!DNL txtlogd.conf].

   * Si vous avez spécifié [!DNL ServerAddress] à l’aide d’un nom de serveur, essayez plutôt d’utiliser son adresse IP numérique. La valeur du [!DNL CertName] paramètre correspond exactement au nom commun qui apparaît sur le certificat numérique du serveur cible Insight.

## Ajout de l’émetteur au script de démarrage du système {#section-4e1ffa6e043941ab91411d91d596477a}

Informations permettant de s’assurer que l’émetteur se charge automatiquement au redémarrage de l’ordinateur du serveur Web.

Ajoutez la commande suivante (qui lance l’émetteur) au script de démarrage du système.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Cette commande démarre l&#39;émetteur en tant que démon. Les messages d’exploitation et d’erreur générés par l’émetteur sont écrits sur syslog.

>[!NOTE]
>
>Certains utilisateurs de Solaris peuvent rencontrer une erreur &quot;Impossible d’acquérir le mutex&quot;. Pour que Sensor fonctionne correctement sur ces systèmes, la ligne suivante doit être ajoutée ou modifiée dans le fichier /etc/system : >
>
```>
>semsys:seminfo_semmnu=1024
>```>
>The default Solaris setting is 60. Based on tests conducted with Sensor, which uses three semaphores for each instance, Adobe recommends that you use 1024 as your setting. This number is high enough for Sensor to function along with any other applications on the server that may require semaphores, but does not affect performance. To support this recommendation, please note that Adrian Cockcroft stated the following in his book Sun Performance and Tuning (Prentice Hall, October 1994): “Databases tend to use lots of shared memory and semaphore settings. These do not affect performance; as long as they are big enough, the programs will run.”



