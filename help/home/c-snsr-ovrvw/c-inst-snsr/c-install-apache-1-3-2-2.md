---
description: Instructions d’installation et de configuration de Sensor pour Apache Server 1.3, Apache Server 2.0.42 ou version ultérieure, ou Apache Server 2.2 s’exécutant sous Microsoft Windows Server 2000 ou version ultérieure.
title: Apache Server 1.3, 2, 2.2 ou 2.4 sous Windows Server 2000 ou version ultérieure
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Apache Server 1.3, 2, 2.2 ou 2.4 sous Windows Server 2000 ou version ultérieure{#apache-server-or-on-windows-server-or-later}

Instructions d’installation et de configuration de Sensor pour Apache Server 1.3, Apache Server 2.0.42 ou version ultérieure, ou Apache Server 2.2 s’exécutant sous Microsoft Windows Server 2000 ou version ultérieure.

Les fichiers programme de Sensor sont compressés dans un fichier d’installation que vous obtenez du site de téléchargement d’Adobe. Si vous ne disposez pas déjà du fichier d’installation de Sensor pour votre serveur Web particulier, téléchargez-le (ou obtenez-le auprès de votre représentant Adobe) avant de commencer les procédures suivantes.

* Apache Server 1.3
* Apache Server 2.0.42 ou version ultérieure
* Apache Server 2.2 s’exécutant sous Microsoft Windows Server 2000 ou version ultérieure

## Installation des fichiers du programme {#section-2f3e85083b4f4aa989a85997330e86ae}

Avant d&#39;installer les fichiers du programme, vous devez déterminer où vous souhaitez conserver la file d&#39;attente de disque, car c&#39;est aussi là que vous devez installer les fichiers du programme.Procédure pour extraire et installer les fichiers du programme pour Sensor.

Pour installer et configurer Sensor, procédez comme suit :

1. Sur votre ordinateur Windows, créez un répertoire dans lequel installer les fichiers du programme Sensor. Gardez à l’esprit que votre file d’attente de disque réside également dans ce répertoire. Assurez-vous donc que le périphérique choisi dispose d’un espace suffisant pour contenir une file d’attente de la taille dont vous avez besoin.

   ```
   C:\VisualSensor
   ```

1. Extrayez le contenu du fichier d&#39;installation dans le répertoire que vous venez de créer. Au cours de cette étape, Sensor installe les fichiers suivants :

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> Messages de l’Observateur d’événements. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mod_Visual_sciences.dll </td> 
   <td colname="col2"> Module collecteur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>Fichier de feuille de calcul Excel que les architectes peuvent utiliser pour configurer une expérience contrôlée. Sensor n’utilise pas ce fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificat utilisé pour valider le certificat numérique présenté par Insight Server pendant le processus de connexion. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> Le programme transmetteur </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Fichier de configuration de Sensor </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le package d’installation contient un fichier de feuille de calcul appelé TestExperiment.xls. Cette feuille de calcul est un outil que les architectes utilisent pour configurer une expérience contrôlée. Sensor n’utilise pas ce fichier, il n’est donc pas nécessaire d’installer le fichier sur l’ordinateur sur lequel Sensor est en cours d’exécution (bien que vous puissiez choisir de le faire). Vous souhaiterez peut-être copier le fichier vers un emplacement accessible par vos architectes ou simplement extraire le fichier du package d’installation, le cas échéant. Pour plus d&#39;informations sur l&#39;expérimentation contrôlée, consultez le Guide des expériences contrôlées Insight.

## Modification du fichier de configuration du capteur {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Le [!DNL txlogd.conf] fichier contient les paramètres de configuration de Sensor.

Vous devez modifier ce fichier pour indiquer, entre autres, la taille et l’emplacement du fichier de file d’attente de disque, l’adresse du serveur Insight et l’ID qui sera joint aux données d’événement produites par ce capteur.

Le fichier de configuration contient les paramètres obligatoires et facultatifs.

* **Les paramètres** requis sont des paramètres que vous devez spécifier lorsque vous installez Sensor. Sans ces paramètres, Sensor ne fonctionne pas correctement.
* **Les paramètres** facultatifs sont des paramètres qui, par défaut, utilisent des valeurs prédéfinies (que vous pouvez modifier) ou activent des fonctionnalités facultatives.

**Pour modifier le fichier de configuration de Sensor**

* Ouvrez le [!DNL /etc/txlogd.conf] fichier dans un éditeur de texte et définissez les paramètres requis ainsi que les paramètres facultatifs de votre choix.
* Enregistrez et fermez le fichier.

**Pour modifier le fichier de configuration de Sensor**

1. Ouvrez le [!DNL /etc/txlogd.conf] fichier dans un éditeur de texte et définissez les paramètres requis ainsi que les paramètres facultatifs de votre choix.
1. Enregistrez et fermez le fichier.

## Démarrage de l&#39;émetteur et création de la file d&#39;attente du disque {#section-55630de65f264274aefd771da2002852}

Après avoir configuré le fichier txlogd.conf, vous pouvez démarrer le programme d’émetteurs, l’enregistrer en tant que service Windows et créer la file d’attente des disques.

1. Si le répertoire dans lequel se trouve la file d&#39;attente de disque n&#39;existe pas déjà, créez-le. Assurez-vous que le répertoire fournit à la fois le module collecteur et le programme émetteur l&#39;accès en lecture/écriture au fichier.

   Pour plus d’informations sur les autorisations requises par les fichiers de file d’attente de disque, voir Autorisations de fichier Sensor UNIX.
1. Sur l’ordinateur sur lequel Sensor est installé, exécutez la commande suivante pour démarrer l’émetteur :

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * L’option &quot;i&quot; de cette commande démarre l’émetteur en &quot;mode interactif&quot;. Ce mode affiche les messages d’émetteur à l’écran et vous permet également d’interagir avec l’émetteur à l’aide des commandes du clavier.
   * L’option &quot;c&quot; indique à l’émetteur de créer la file d’attente du disque.
   * L’option &quot;f&quot; spécifie l’emplacement du fichier de configuration.
   Pour plus d’informations sur les options que vous pouvez utiliser au démarrage de l’émetteur, voir Options de ligne de commande de l’émetteur de capteur.

1. Vérifiez que l’émetteur a créé la file d’attente du disque à l’emplacement spécifié dans le paramètre QueueFile et à la taille spécifiée dans le paramètre QueueSize.
1. Si la file d’attente n’a pas été créée correctement, tapez Ctrl+C pour arrêter l’émetteur, puis procédez comme suit :

   1. Examinez le fichier txtlogd.conf et vérifiez que les paramètres QueueFile et QueueSize sont définis correctement.
   1. Vérifiez que le périphérique auquel la file d&#39;attente de disque est affectée est opérationnel et dispose de suffisamment d&#39;espace disponible pour stocker un fichier de la taille spécifiée dans le paramètre QueueSize.
   1. Effectuez les corrections nécessaires et répétez cette procédure.

## Ajout du collecteur au serveur Web {#section-c5b83ae4ebce430aa764f951e849b333}

Pour les serveurs Apache, le collecteur est un objet partagé dynamique que vous chargez dans le processus de votre serveur Web.

Pour ajouter le collecteur à votre serveur Web, vous devez modifier le [!DNL httpd.conf] fichier comme décrit ci-dessous et redémarrer votre serveur Web.

>[!NOTE]
>
>Si Sensor capture des données pour plusieurs serveurs Web sur l’ordinateur serveur, vous devez effectuer la procédure suivante pour chaque serveur Web.

1. A l’aide d’un éditeur de texte, ouvrez le [!DNL httpd.conf]fichier pour le serveur Web dont Sensor capture les événements.
1. Ajoutez les deux lignes suivantes à la fin du fichier :

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Ces lignes sont sensibles à la casse. Tapez-les exactement comme ils apparaissent ci-dessus.

1. Redémarrez le processus du serveur Web (vous n&#39;avez pas à redémarrer l&#39;ordinateur du serveur entier, il vous suffit de redémarrer le processus du serveur Web). Le collecteur est chargé avec le serveur Web et commence à collecter les données d’événement et à les écrire dans la file d’attente du disque.

