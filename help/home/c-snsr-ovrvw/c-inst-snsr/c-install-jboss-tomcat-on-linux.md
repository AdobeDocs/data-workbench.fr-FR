---
description: Instructions détaillées sur l’installation et la configuration des implémentations de Capteur pour J2EE s’exécutant sur RedHat Linux 7.x ou version ultérieure, Sun Solaris SPARC 2.6 ou version ultérieure ou Sun Solaris x86 9 ou version ultérieure.
title: Serveurs JBoss, Tomcat et WebLogic sous RedHat Linux ou Sun Solaris
uuid: 7977fb9b-1737-4e1d-80c6-aabf968974dd
exl-id: 09c2f266-2ecc-42fc-98b6-b91f8883af0c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1823'
ht-degree: 1%

---

# Serveurs JBoss, Tomcat et WebLogic sous RedHat Linux ou Sun Solaris{#jboss-tomcat-and-weblogic-servers-on-redhat-linux-or-sun-solaris}

{{eol}}

Instructions détaillées sur l’installation et la configuration des implémentations de Capteur pour J2EE s’exécutant sur RedHat Linux 7.x ou version ultérieure, Sun Solaris SPARC 2.6 ou version ultérieure ou Sun Solaris x86 9 ou version ultérieure.

Les fichiers de programme pour Capteur sont contenus dans un fichier d’installation que vous obtenez sur le site de téléchargement de l’Adobe. Si vous ne disposez pas déjà du fichier d’installation de Capteur pour votre serveur web en particulier, téléchargez-le (ou procurez-le auprès de votre représentant d’Adobe) avant de commencer les procédures suivantes.

Les mises en oeuvre J2EE prises en charge sont les suivantes :

* JBoss Server 3.2.x ou version ultérieure
* Apache Jakarta Tomcat Server 4.1 ou version ultérieure
* WebLogic Server 6.x ou version ultérieure

Pour installer et configurer Capteur, procédez comme suit :

## Installation des fichiers de programme {#section-2f3e85083b4f4aa989a85997330e86ae}

Procédure d’extraction et d’installation des fichiers de programme pour Capteur.

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
1. Ajoutez ce qui suit : `<filter>` et `<filter-mapping>` au fichier descripteur. Si vous n’avez pas installé txlogd.conf dans le répertoire /etc, vous devez saisir le chemin d’accès correct à ce fichier dans la variable `<param-value>` element:

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>/etc/txlogd.conf</param-value> 
     <description></description> 
     </init-param> 
   </filter> 
   
   <filter-mapping> 
     <filter-name>VSCollectorFilter</filter-name> 
     <url-pattern>/*</url-pattern> 
   </filter-mapping> 
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

Cette commande lance l&#39;émetteur comme démon. Les messages d&#39;exploitation et d&#39;erreur générés par l&#39;émetteur sont écrits sur [!DNL syslog].

Le paramètre par défaut de Solaris est 60. Selon les tests effectués avec Capteur, qui utilise trois semaphores pour chaque instance, Adobe vous recommande d’utiliser 1024 comme paramètre. Ce nombre est suffisamment élevé pour que Capteur fonctionne avec toute autre application sur le serveur qui peut nécessiter un point-virgule, mais n’affecte pas les performances. Pour appuyer cette recommandation, veuillez noter que Adrian Cockcroft a déclaré dans son livre Sun Performance and Tuning (Prentice Hall, octobre 1994) ce qui suit : &quot;Les bases de données ont tendance à utiliser beaucoup de paramètres de mémoire partagée et de sémaphore. Elles n’affectent pas les performances ; tant qu&#39;ils seront assez gros, les programmes fonctionneront.&quot;

## Capture de données supplémentaires {#section-9483b663cbd0432daaca50c1089c7fca}

Les capteurs de toutes les plateformes peuvent collecter toutes les données disponibles dans les en-têtes de requête et de réponse HTTP.

Les capteurs de la plateforme J2EE fournissent un mécanisme de collecte de données qui n’est pas disponible sur d’autres plateformes. Le collecteur de la plateforme J2EE (collecteur J2EE) se trouve sur la couche de l’application, ce qui lui permet de collecter des données sensibles qui sont disponibles uniquement pour l’application et ne doivent pas être exposées par le balisage de page ou dans les en-têtes.

>[!NOTE]
>
>Bien que les balises de page et la modification de l’en-tête puissent masquer les données, celles-ci restent accessibles pour ceux qui examinent le code source d’une page ou qui consultent les en-têtes à l’aide des outils de plug-in de navigateur.

Par exemple, le collecteur J2EE peut être utilisé pour capturer les données de coût par clic (CPC) pour les liens affichés sur une page, les informations sensibles sur les partenaires sur une page et de nombreux autres points de données. L’environnement J2EE vous permet de modifier facilement votre WEBAPP pour capturer ces données personnalisées à l’aide de notre classe de collecteur.

Lorsqu’un capteur de la plateforme J2EE reçoit une requête, il appelle une classe de collecteur qui importe la fonction appendToLog . La fonction appendToLog ajoute à la requête initiale les paramètres de chaîne de requête spécifiés dans la fonction appendToLog . Cela entraîne l’URI de la requête initiale contenant des paires nom-valeur de chaîne de requête supplémentaires qui correspondent aux noms et aux valeurs des données capturées. Par exemple, CPC=20 serait annexé à la demande initiale lorsque la valeur d’un emplacement de publicité ou d’un lien de clic publicitaire spécifique est de 20 cents. Insight Server traite ces valeurs dans le jeu de données à des fins d’analyse. Cette méthodologie de collecte présente un autre avantage : elle permet la collecte de données supplémentaires sans créer d’entrées de journal supplémentaires, comme elle peut être créée à l’aide des méthodologies de balisage de page.

Pour plus d’informations sur le traitement, consultez le Guide de configuration des jeux de données .

**Pour capturer des données supplémentaires à partir d’une page**

1. Ajoutez le code suivant en haut de la page .jsp à partir de laquelle vous souhaitez capturer des données :

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. Utilisez la méthode appendToLog() de l’objet collecteur pour ajouter les paires nom-valeur souhaitées à la chaîne de requête de la page .jsp demandée. L’exemple suivant ajoute &quot;A=1&quot; et &quot;B=2&quot; à la chaîne de requête de la page .jsp demandée pour la page /index.jsp :

   ```
   <html> 
   <body> 
     <h1>Hello World</h1> 
     <% 
       VSCollector collector = new VSCollector(request, response); 
       collector.appendToLog("A", "1"); 
       collector.appendToLog("B", "2"); 
     %> 
   </body> 
   </html>
   ```

   L’URI de requête obtenu est /index.jsp?A=1&amp;B=2.

1. Répétez cette procédure pour chaque page .jsp à partir de laquelle vous souhaitez capturer des données supplémentaires.
