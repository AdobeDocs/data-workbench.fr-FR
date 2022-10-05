---
description: Instructions détaillées sur l’installation et la configuration de Capteur pour un serveur Apache 1.3.x sous RedHat Linux 7.x ou version ultérieure, SUSE Linux 9.x ou version ultérieure, Sun Solaris SPARC 2.6 ou version ultérieure, Sun Solaris x86 9 ou version ultérieure, FreeBSD 4 ou version ultérieure, ou Mac OS X PowerPC.
title: Apache Server 1.3.x sous Linux, Sun Solaris, FreeBSD ou Mac OS X
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
exl-id: 087494fb-c8f0-457c-b3db-d9147a739998
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---

# Apache Server 1.3.x sous Linux, Sun Solaris, FreeBSD ou Mac OS X{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

{{eol}}

Instructions détaillées sur l’installation et la configuration de Capteur pour un serveur Apache 1.3.x sous RedHat Linux 7.x ou version ultérieure, SUSE Linux 9.x ou version ultérieure, Sun Solaris SPARC 2.6 ou version ultérieure, Sun Solaris x86 9 ou version ultérieure, FreeBSD 4 ou version ultérieure, ou Mac OS X PowerPC.

Les fichiers de programme pour Capteur sont contenus dans un fichier d’installation que vous obtenez sur le site de téléchargement de l’Adobe. Si vous ne disposez pas déjà du fichier d’installation de Capteur pour votre serveur web en particulier, téléchargez-le (ou procurez-le auprès de votre représentant d’Adobe) avant de commencer les procédures suivantes.

Pour installer et configurer Capteur, vous devez effectuer les étapes de haut niveau suivantes :

## Installation des fichiers de programme {#section-aae323e252394212bf4096d65fdd280c}

Instructions pour extraire et installer les fichiers de programme pour Capteur sur l’ordinateur serveur.

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
   <td colname="col2"> Le programme d'émetteur </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Le fichier de configuration de Capteur </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificat utilisé pour valider le certificat numérique qu’Insight Server présente pendant le processus de connexion </td> 
   <td colname="col3"> /usr/local/visuel_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le package d’installation contient un fichier de feuille de calcul appelé TestExperiment.xls. Cette feuille de calcul est un outil que les architectes utilisent pour configurer une expérience contrôlée. Sensor n’utilise pas ce fichier. Il n’est donc pas nécessaire d’installer le fichier sur l’ordinateur sur lequel Sensor est exécuté (bien que vous puissiez choisir de le faire). Vous pouvez plutôt copier le fichier vers un emplacement accessible par vos architectes ou simplement extraire le fichier du package d’installation, si nécessaire. Pour plus d’informations sur l’expérimentation contrôlée, consultez le guide des expériences contrôlées Insight .

**Autorisations sur les fichiers de programme**

Des autorisations incorrectes sur les fichiers de programme entraînent la plupart des problèmes lors de l’installation de Capteur.

Veillez à définir les autorisations exactement comme indiqué dans cette section.

Par défaut, les fichiers de programme du fichier tar disposent des autorisations suivantes. Selon la configuration de votre système, ces paramètres peuvent être modifiés (non masqués) lors de l’extraction des fichiers. Pour réinitialiser les autorisations aux paramètres par défaut recommandés, utilisez les commandes chmod ci-dessous. Vérifiez que les répertoires dans lesquels vous avez installé les fichiers permettent au moins ce niveau d’accès.

| Fichier | Autorisations par défaut | chmod, commande |
|---|---|---|
| mod_Visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-rw- r— | chmod 664 |
| trust_ca_cert.pem | rw-rw- r— | chmod 664 |

## Modification du fichier de configuration du capteur {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

Le [!DNL txlogd.conf] contient les paramètres de configuration de Capteur.

Vous devez modifier le fichier pour indiquer, entre autres, la taille de la file d’attente du disque, l’adresse du serveur Insight et l’identifiant qui sera joint aux données générées par ce capteur.

Le fichier de configuration contient les paramètres requis et les paramètres facultatifs.

* Les paramètres requis sont des paramètres que vous devez spécifier lors de l’installation de Capteur. Sans ces paramètres, Capteur ne s’exécute pas correctement.
* Les paramètres facultatifs sont des paramètres qui activent par défaut des valeurs prédéfinies (que vous pouvez modifier) ou des fonctionnalités facultatives.

Modification du fichier de configuration du capteur

1. Ouvrez le fichier /etc/txlogd.conf dans un éditeur de texte et définissez les paramètres requis ainsi que les paramètres facultatifs souhaités.
1. Enregistrez le fichier, puis fermez-le.

## Démarrez l’émetteur et créez la file d’attente du disque {#section-a453d912ec3d47aa8e40ccacf527119d}

Instructions de création de la file d’attente de disque après la configuration du fichier txlogd.conf.

1. Si le répertoire dans lequel se trouve la file d’attente de disque n’existe pas déjà, créez-le. Assurez-vous que le répertoire fournit au module collecteur et au programme d’émetteur un accès en lecture/écriture au fichier.
1. Sur l’ordinateur sur lequel Sensor est installé, exécutez la commande suivante pour démarrer l’émetteur :

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * L&#39;option &quot;i&quot; de cette commande démarre l&#39;émetteur en mode interactif. Ce mode affiche les messages de l&#39;émetteur à l&#39;écran et permet également d&#39;interagir avec l&#39;émetteur à l&#39;aide des commandes du clavier.
   * L&#39;option &quot;c&quot; demande à l&#39;émetteur de créer la file d&#39;attente du disque.
   * L’option &quot;f&quot; spécifie l’emplacement du fichier de configuration.

1. Vérifiez que l’émetteur a créé la file d’attente du disque à l’emplacement spécifié dans le paramètre QueueFile et à la taille spécifiée dans le paramètre QueueSize .
1. Si la file d&#39;attente n&#39;a pas été créée correctement, tapez Ctrl+C pour arrêter l&#39;émetteur, puis procédez comme suit :

   1. Examinez le fichier txtlogd.conf et vérifiez que les paramètres QueueFile et QueueSize sont correctement définis.
   1. Vérifiez que le périphérique auquel la file d’attente de disque est affectée est opérationnel et dispose de suffisamment d’espace disponible pour contenir un fichier de la taille spécifiée dans le paramètre QueueSize .
   1. Effectuez les corrections nécessaires et répétez cette procédure.

## Ajout du collecteur au serveur web {#section-a7fb6425956f4f518ae3a7db091b33d2}

Pour les serveurs Apache, le collecteur est un objet partagé dynamique que vous chargez dans le processus de votre serveur web.

Pour ajouter le collecteur à votre serveur web, vous devez modifier le fichier httpd.conf comme décrit ci-dessous, puis redémarrer votre serveur web.

Si Capteur capture des données pour plusieurs serveurs Web sur l’ordinateur serveur, vous devez effectuer la procédure suivante pour chaque serveur Web.

1. À l’aide d’un éditeur de texte, ouvrez le [!DNL httpd.conf] pour le serveur web dont le Capteur d’événements capture les événements.
1. Ajoutez les lignes suivantes à la fin du fichier :

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >Ces lignes sont sensibles à la casse. Saisissez-les exactement comme ils apparaissent ci-dessus.

1. Redémarrez le serveur web. Le collecteur est chargé avec le serveur web et commence à collecter les données d’événement et à les écrire dans la file d’attente du disque.

## Test du capteur {#section-83d9f60b39a6474f9c76bee3e19b2575}

Démarrez l’émetteur et vérifiez qu’il peut se connecter au serveur Insight et lui transmettre des données d’événement.

>[!NOTE]
>
>Pour vérifier que l’émetteur peut envoyer des données d’événement au serveur Insight, assurez-vous que le serveur Insight cible est installé et en cours d’exécution avant de lancer le test suivant.

1. Si l&#39;émetteur n&#39;est pas déjà en cours d&#39;exécution, redémarrez-le à l&#39;aide de la commande suivante :

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Ouvrez un navigateur (sur n’importe quel ordinateur) et demandez une page au serveur Web sur lequel le Capteur est en cours d’exécution (veillez à sélectionner une page que le Capteur surveille).
1. Après avoir émis la requête, vérifiez dans la console de l’émetteur les messages indiquant qu’il envoie des données d’événement au serveur Insight cible.
1. Si Sensor ne transmet pas correctement les données, vérifiez que :

   * Le serveur Insight cible est en cours d’exécution.
   * Le [!DNL ServerAddress] et [!DNL ServerPort] Les paramètres sont correctement définis dans [!DNL txtlogd.conf].

   * Si vous avez spécifié [!DNL ServerAddress] en utilisant un nom de serveur, essayez d’utiliser plutôt son adresse IP numérique. La valeur de la variable [!DNL CertName] correspond exactement au nom commun qui apparaît sur le certificat numérique de target Insight Server.

## Ajout de l’émetteur au script de démarrage du système {#section-4e1ffa6e043941ab91411d91d596477a}

Informations permettant de s’assurer que l’émetteur se charge automatiquement au redémarrage de la machine du serveur web.

Ajoutez la commande suivante (qui lance l&#39;émetteur) au script de démarrage du système.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Cette commande lance l&#39;émetteur comme démon. Les messages d&#39;exploitation et d&#39;erreur générés par l&#39;émetteur sont écrits dans syslog.

>[!NOTE]
>
>Certains utilisateurs de Solaris peuvent rencontrer une erreur &quot;impossible d’acquérir un mutex&quot;. Pour que Capteur fonctionne correctement sur ces systèmes, la ligne suivante doit être ajoutée à ou modifiée dans le fichier /etc/system :
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>Le paramètre par défaut de Solaris est 60. Selon les tests effectués avec Capteur, qui utilise trois semaphores pour chaque instance, Adobe vous recommande d’utiliser 1024 comme paramètre. Ce nombre est suffisamment élevé pour que Capteur fonctionne avec toute autre application sur le serveur qui peut nécessiter un point-virgule, mais n’affecte pas les performances. Pour appuyer cette recommandation, veuillez noter que Adrian Cockcroft a déclaré dans son livre Sun Performance and Tuning (Prentice Hall, octobre 1994) ce qui suit : &quot;Les bases de données ont tendance à utiliser beaucoup de paramètres de mémoire partagée et de sémaphore. Elles n’affectent pas les performances ; tant qu&#39;ils seront assez gros, les programmes fonctionneront.&quot;
