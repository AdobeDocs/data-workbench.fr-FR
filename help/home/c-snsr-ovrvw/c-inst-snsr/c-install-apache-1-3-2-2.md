---
description: Instructions d’installation et de configuration de Capteur pour Apache Server 1.3, Apache Server 2.0.42 ou version ultérieure, ou Apache Server 2.2 s’exécutant sous Microsoft Windows Server 2000 ou version ultérieure.
title: Apache Server 1.3, 2, 2.2 ou 2.4 sous Windows Server 2000 ou ultérieur
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
exl-id: d1bd0fc1-da5b-4183-8270-73c46195f724
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 1%

---

# Apache Server 1.3, 2, 2.2 ou 2.4 sous Windows Server 2000 ou ultérieur{#apache-server-or-on-windows-server-or-later}

{{eol}}

Instructions d’installation et de configuration de Capteur pour Apache Server 1.3, Apache Server 2.0.42 ou version ultérieure, ou Apache Server 2.2 s’exécutant sous Microsoft Windows Server 2000 ou version ultérieure.

Les fichiers de programme pour Capteur sont contenus dans un fichier d’installation que vous obtenez sur le site de téléchargement de l’Adobe. Si vous ne disposez pas déjà du fichier d’installation de Capteur pour votre serveur web en particulier, téléchargez-le (ou procurez-le auprès de votre représentant d’Adobe) avant de commencer les procédures suivantes.

* Apache Server 1.3
* Apache Server 2.0.42 ou version ultérieure
* Apache Server 2.2 s’exécutant sous Microsoft Windows Server 2000 ou version ultérieure

## Installation des fichiers de programme {#section-2f3e85083b4f4aa989a85997330e86ae}

Avant d’installer les fichiers de programme, vous devez déterminer où vous souhaitez conserver la file d’attente du disque, car c’est également là que vous devez installer les fichiers de programme. Procédure pour extraire et installer les fichiers de programme pour Capteur.

Pour installer et configurer Capteur, procédez comme suit :

1. Sur votre ordinateur Windows, créez un répertoire dans lequel installer les fichiers du programme Capteur. Gardez à l’esprit que votre file d’attente de disque réside également dans ce répertoire. Assurez-vous donc que le périphérique choisi dispose de suffisamment d’espace pour contenir une file d’attente de la taille dont vous avez besoin.

   ```
   C:\VisualSensor
   ```

1. Extrayez le contenu du fichier d&#39;installation dans le répertoire que vous venez de créer. Au cours de cette étape, Capteur installe les fichiers suivants :

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
   <td colname="col2"> Messages de la visionneuse d’événements. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mod_Visual_sciences.dll </td> 
   <td colname="col2"> Module collecteur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>Fichier de feuille de calcul Excel que les architectes peuvent utiliser pour configurer une expérience contrôlée. Capteur n’utilise pas ce fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificat utilisé pour valider le certificat numérique qu’Insight Server présente pendant le processus de connexion. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> Le programme d'émetteur </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Le fichier de configuration de Capteur </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le package d’installation contient un fichier de feuille de calcul appelé TestExperiment.xls. Cette feuille de calcul est un outil que les architectes utilisent pour configurer une expérience contrôlée. Sensor n’utilise pas ce fichier. Il n’est donc pas nécessaire d’installer le fichier sur l’ordinateur sur lequel Sensor est exécuté (bien que vous puissiez choisir de le faire). Vous pouvez plutôt copier le fichier vers un emplacement accessible par vos architectes ou simplement extraire le fichier du package d’installation, si nécessaire. Pour plus d’informations sur l’expérimentation contrôlée, consultez le guide des expériences contrôlées Insight .

## Modification du fichier de configuration du capteur {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

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

Pour les serveurs Apache, le collecteur est un objet partagé dynamique que vous chargez dans le processus de votre serveur web.

Pour ajouter le collecteur à votre serveur web, vous devez modifier la variable [!DNL httpd.conf] comme décrit ci-dessous et redémarrez votre serveur web.

>[!NOTE]
>
>Si Capteur capture des données pour plusieurs serveurs Web sur l’ordinateur serveur, vous devez effectuer la procédure suivante pour chaque serveur Web.

1. À l’aide d’un éditeur de texte, ouvrez le [!DNL httpd.conf]pour le serveur web dont le Capteur d’événements capture les événements.
1. Ajoutez les deux lignes suivantes à la fin du fichier :

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Ces lignes sont sensibles à la casse. Saisissez-les exactement comme ils apparaissent ci-dessus.

1. Redémarrez le processus du serveur web (il n’est pas nécessaire de redémarrer l’ensemble de l’ordinateur serveur, il suffit de redémarrer le processus du serveur web). Le collecteur est chargé avec le serveur web et commence à collecter les données d’événement et à les écrire dans la file d’attente du disque.
