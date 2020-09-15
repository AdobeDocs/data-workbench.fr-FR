---
description: Instructions détaillées pour l'installation et la configuration de Sensor for an Apache Server 1.3.x sur RedHat Linux 7.x ou version ultérieure, SUSE Linux 9.x ou version ultérieure, Sun Solaris SPARC 2.6 ou version ultérieure, Sun Solaris x86 9 ou version ultérieure, FreeBSD 4 ou version ultérieure, ou Mac OS X PowerPC.
title: Apache Server 1.3.x sous Linux, Sun Solaris, FreeBSD ou Mac OS X
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
translation-type: tm+mt
source-git-commit: 98452ba81d71db65c75e3d07712eefa18c003f53
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---


# Apache Server 1.3.x sous Linux, Sun Solaris, FreeBSD ou Mac OS X{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

Instructions détaillées pour l&#39;installation et la configuration de Sensor for an Apache Server 1.3.x sur RedHat Linux 7.x ou version ultérieure, SUSE Linux 9.x ou version ultérieure, Sun Solaris SPARC 2.6 ou version ultérieure, Sun Solaris x86 9 ou version ultérieure, FreeBSD 4 ou version ultérieure, ou Mac OS X PowerPC.

Les fichiers de programme de Sensor sont inclus dans un fichier d’installation que vous obtenez du site de téléchargement de l’Adobe. Si vous ne disposez pas déjà du fichier d’installation de Sensor pour votre serveur Web particulier, téléchargez-le (ou procurez-le auprès de votre représentant d’Adobe) avant de commencer les procédures suivantes.

Pour installer et configurer Sensor, vous devez effectuer les étapes de haut niveau suivantes :

## Installation des fichiers de Programme {#section-aae323e252394212bf4096d65fdd280c}

Instructions d’extraction et d’installation des fichiers de programme pour Sensor sur l’ordinateur serveur.

1. Connectez-vous en tant qu’utilisateur root ou en tant qu’utilisateur disposant de l’autorisation root.
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

1. Copiez les fichiers de programme non compressés dans les répertoires identifiés dans le tableau suivant :

<table id="table_A97CF630633C4543A742D96C302D1138"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Cible Directory </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> Module de chargement du collecteur </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Programme de l'émetteur </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OU-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Fichier de configuration du capteur </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificat utilisé pour valider le certificat numérique présenté par Insight Server lors du processus de connexion </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le package d’installation contient un fichier de feuille de calcul appelé TestExperiment.xls. Cette feuille de calcul est un outil que les architectes utilisent pour configurer une expérience contrôlée. Sensor n’utilise pas ce fichier, il n’est donc pas nécessaire d’installer le fichier sur l’ordinateur sur lequel Sensor est en cours d’exécution (bien que vous puissiez choisir de le faire). Vous pouvez, à la place, copier le fichier vers un emplacement où vos architectes peuvent y accéder ou simplement extraire le fichier du package d&#39;installation si nécessaire. Pour plus d’informations sur l’expérimentation contrôlée, consultez le Guide des expériences contrôlées d’Insight.

**Autorisations sur les fichiers de Programme**

Des autorisations incorrectes sur les fichiers de programme provoquent la plupart des problèmes rencontrés lors de l’installation de Sensor.

Assurez-vous de définir les autorisations exactement comme indiqué dans cette section.

Par défaut, les fichiers de programme du fichier tar disposent des autorisations suivantes. Selon la configuration de votre système, ces paramètres peuvent être modifiés (non masqués) lors de l’extraction des fichiers. Pour réinitialiser les autorisations aux paramètres par défaut recommandés, utilisez les commandes chmod ci-dessous. Vérifiez que les répertoires dans lesquels vous avez installé les fichiers permettent au moins ce niveau d&#39;accès.

| Fichier | Autorisations par défaut | chmod, commande |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

## Edit the Sensor configuration file {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

Le [!DNL txlogd.conf] fichier contient les paramètres de configuration de Sensor.

Vous devez modifier le fichier pour indiquer, entre autres, la taille de la file d’attente de disque, l’adresse du serveur Insight et l’identifiant qui sera associé aux données produites par ce capteur.

Le fichier de configuration contient les paramètres requis et les paramètres facultatifs.

* Les paramètres requis sont des paramètres que vous devez spécifier lors de l’installation de Sensor. Sans ces paramètres, Sensor ne s’exécute pas correctement.
* Les paramètres facultatifs sont des paramètres qui, par défaut, correspondent à des valeurs prédéfinies (que vous pouvez modifier) ou qui activent des fonctionnalités facultatives.

Pour modifier le fichier de configuration de Sensor

1. Ouvrez le fichier /etc/txlogd.conf dans un éditeur de texte et définissez les paramètres requis ainsi que les paramètres facultatifs de votre choix.
1. Enregistrez et fermez le fichier.

## Début de l&#39;émetteur et création de la file d&#39;attente de disque {#section-a453d912ec3d47aa8e40ccacf527119d}

Instructions pour créer la file d&#39;attente de disque après avoir configuré le fichier txlogd.conf.

1. Si le répertoire dans lequel se trouve la file d&#39;attente de disque n&#39;existe pas déjà, créez-le. Assurez-vous que le répertoire fournit à la fois le module collecteur et le programme émetteur un accès en lecture/écriture au fichier.
1. Sur l’ordinateur sur lequel Sensor est installé, exécutez la commande suivante pour début de l’émetteur :

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * L’option &quot;i&quot; de cette commande début l’émetteur en mode interactif. Ce mode affiche des messages d&#39;émetteur à l&#39;écran et vous permet également d&#39;interagir avec l&#39;émetteur à l&#39;aide des commandes du clavier.
   * L&#39;option &quot;c&quot; indique à l&#39;émetteur de créer la file d&#39;attente de disque.
   * L’option &quot;f&quot; spécifie l’emplacement du fichier de configuration.

1. Vérifiez que l&#39;émetteur a créé la file d&#39;attente de disque à l&#39;emplacement spécifié dans le paramètre QueueFile et de la taille spécifiée dans le paramètre QueueSize.
1. Si la file d&#39;attente n&#39;a pas été créée correctement, tapez Ctrl+C pour arrêter l&#39;émetteur, puis procédez comme suit :

   1. Examinez le fichier txtlogd.conf et vérifiez que les paramètres QueueFile et QueueSize sont définis correctement.
   1. Vérifiez que le périphérique auquel la file d&#39;attente de disque est affectée est opérationnel et dispose de suffisamment d&#39;espace pour contenir un fichier de la taille spécifiée dans le paramètre QueueSize.
   1. Effectuez les corrections nécessaires et répétez cette procédure.

## ajouter le collecteur au serveur Web {#section-a7fb6425956f4f518ae3a7db091b33d2}

Pour les serveurs Apache, le collecteur est un objet partagé dynamique que vous chargez dans le processus de votre serveur Web.

Pour ajouter le collecteur à votre serveur Web, vous devez modifier le fichier httpd.conf comme décrit ci-dessous et redémarrer votre serveur Web.

Si Sensor capture des données pour plusieurs serveurs Web sur l’ordinateur serveur, vous devez effectuer la procédure suivante pour chaque serveur Web.

1. A l’aide d’un éditeur de texte, ouvrez le [!DNL httpd.conf] fichier pour le serveur Web dont événement Sensor capture les données.
1. ajoutez les lignes suivantes à la fin du fichier :

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >Ces lignes sont sensibles à la casse. Tapez-les exactement comme ils apparaissent ci-dessus.

1. Redémarrez le serveur Web. Le collecteur est chargé avec le serveur Web et commencera à collecter les données de événement et à les écrire dans la file d&#39;attente de disque.

## Test du capteur {#section-83d9f60b39a6474f9c76bee3e19b2575}

Début de l’émetteur et vérifiez qu’il peut se connecter au serveur Insight et lui transmettre les données du événement.

>[!NOTE]
>
>Pour vérifier que l’émetteur peut envoyer des données de événement au serveur Insight, assurez-vous que le serveur cible Insight est installé et en cours d’exécution avant de commencer le test suivant.

1. Si l’émetteur n’est pas en cours d’exécution, redémarrez-le à l’aide de la commande suivante :

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Ouvrez un navigateur (sur n’importe quel ordinateur) et demandez une page au serveur Web sur lequel Sensor s’exécute (veillez à sélectionner une page que Sensor surveille).
1. Une fois la requête émise, vérifiez dans la console de l’émetteur les messages indiquant qu’elle envoie des données de événement au serveur cible Insight.
1. Si Sensor ne transmet pas correctement les données, vérifiez que :

   * Cible Insight Server est en cours d’exécution.
   * Les [!DNL ServerAddress] paramètres et [!DNL ServerPort] sont définis correctement dans [!DNL txtlogd.conf].

   * Si vous avez spécifié [!DNL ServerAddress] à l’aide d’un nom de serveur, tentez plutôt d’utiliser son adresse IP numérique. La valeur du [!DNL CertName] paramètre correspond exactement au nom commun qui apparaît sur le certificat numérique du serveur cible Insight.

## ajouter l&#39;émetteur à votre script de démarrage du système {#section-4e1ffa6e043941ab91411d91d596477a}

Informations permettant de s’assurer que l’émetteur se charge automatiquement au redémarrage de l’ordinateur du serveur Web.

ajoutez la commande suivante (qui lance l&#39;émetteur) sur votre script de démarrage du système.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Cette commande début l&#39;émetteur en tant que démon. Les messages d&#39;exploitation et d&#39;erreur générés par l&#39;émetteur sont écrits sur syslog.

>[!NOTE]
>
>Certains utilisateurs Solaris peuvent rencontrer une erreur &quot;Impossible d&#39;acquérir mutex&quot;. Pour que Sensor fonctionne correctement sur ces systèmes, la ligne suivante doit être ajoutée ou modifiée dans le fichier /etc/system :
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>Le paramètre Solaris par défaut est 60. Selon les tests effectués avec Sensor, qui utilise trois sémaphores pour chaque instance, l’Adobe vous recommande d’utiliser 1024 comme paramètre. Ce nombre est suffisamment élevé pour que Sensor fonctionne avec toute autre application sur le serveur qui peut nécessiter des sémaphores, mais n’affecte pas les performances. Pour appuyer cette recommandation, veuillez noter que Adrian Cockcroft a déclaré ce qui suit dans son livre Sun Performance and Tuning (Prentice Hall, octobre 1994) : &quot;Les bases de données ont tendance à utiliser beaucoup de paramètres de mémoire partagée et de sémaphore. Elles n&#39;ont aucune incidence sur les performances ; tant qu&#39;ils sont assez gros, les programmes vont courir.&quot;

