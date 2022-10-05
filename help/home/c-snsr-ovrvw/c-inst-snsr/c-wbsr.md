---
description: Instructions détaillées sur l’installation et la configuration de Capteur pour WebSphere 5.x s’exécutant sous AIX 5.1 ou version ultérieure.
title: WebSphere sous AIX
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
exl-id: e560d265-dc84-4ff2-ac86-7a2ac5261451
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1645'
ht-degree: 0%

---

# WebSphere sous AIX{#websphere-on-aix}

{{eol}}

Instructions détaillées sur l’installation et la configuration de Capteur pour WebSphere 5.x s’exécutant sous AIX 5.1 ou version ultérieure.

Les fichiers de programme pour [!DNL Sensor] sont regroupés dans un fichier d’installation que vous obtenez sur le site de téléchargement Adobe. Si vous ne disposez pas déjà de la variable [!DNL Sensor] fichier d’installation pour votre serveur web spécifique, téléchargez-le (ou obtenez-le auprès de votre représentant d’Adobe) avant de commencer les procédures suivantes.

>[!NOTE]
>
>Le [!DNL Sensor] pour les serveurs WebSphere ne prend pas en charge l’expérimentation contrôlée. Pour plus d’informations sur l’expérimentation contrôlée, voir *Guide des expériences contrôlées par le Data Workbench.*

## Installation des fichiers de programme {#section-86f69127278c41bc90b97b68bb40bc6e}

Procédure d’extraction et d’installation des fichiers de programme pour Sensorto sur l’ordinateur serveur.

1. Connectez-vous en tant qu’utilisateur root ou en tant qu’utilisateur disposant de l’autorisation root.
1. Décompressez et décompressez le fichier d’installation à l’aide de la commande suivante :

   ```
   gunzip installationFilename.tar.gz 
   tar -xf installationFilename.tar
   ```

1. Copiez les fichiers de programme décompressés dans les répertoires identifiés dans le tableau suivant :

<table id="table_0E3B403071EF44AFBF0DD673EFEBBFE5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Répertoire cible </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisuel_sciences.so </td> 
   <td colname="col2"> Module de chargement du collecteur </td> 
   <td colname="col3"> /usr/local/visuel_sciences </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> Bibliothèques du module de chargement de collecteur </td> 
   <td colname="col3"> Répertoire WebSphere /lib </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
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

Par défaut, les fichiers de programme du fichier tar disposent des autorisations suivantes. Selon la configuration de votre système, ces paramètres peuvent être modifiés (non masqués) lors de l’extraction des fichiers.

Pour réinitialiser les autorisations aux paramètres par défaut recommandés, utilisez les commandes chmod ci-dessous.

>[!NOTE]
>
>Vérifiez que les répertoires dans lesquels vous avez installé les fichiers permettent au moins ce niveau d’accès.

| Fichier | Autorisations par défaut | chmod, commande |
|---|---|---|
| libvisuel_sciences.so | rwx —x —x | chmod 711 |
| J2EECollector.jar | rw-rw- r— | chmod 664 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-rw- r— | chmod 664 |
| trust_ca_cert.pem | rw-rw- r— | chmod 664 |

Si vous souhaitez utiliser des autorisations autres que les valeurs par défaut recommandées, consultez les informations dans Autorisations des fichiers UNIX dans Capteur, afin de vous assurer que vous comprenez comment ces fichiers sont utilisés.

## Modification du fichier de configuration du capteur {#section-283c8a92fa8841c1b6034e5f834ef4e7}

Le fichier txlogd.conf contient les paramètres de configuration de Capteur.

Vous devez modifier le fichier pour indiquer, entre autres, la taille de la file d’attente du disque, l’adresse du serveur Insight et l’identifiant qui sera joint aux données générées par ce capteur.

Le fichier de configuration contient les paramètres requis et les paramètres facultatifs.

* Les paramètres requis sont des paramètres que vous devez spécifier lors de l’installation de Capteur. Sans ces paramètres, Capteur ne s’exécute pas correctement.
* Les paramètres facultatifs sont des paramètres qui activent par défaut des valeurs prédéfinies (que vous pouvez modifier) ou des fonctionnalités facultatives.

**Pour modifier le fichier de configuration**

1. Ouvrez le fichier /etc/txlogd.conf dans un éditeur de texte et définissez les paramètres requis ainsi que les paramètres facultatifs souhaités.
1. Enregistrez le fichier, puis fermez-le.

## Démarrez l’émetteur et créez la file d’attente du disque {#section-63285a2328604f20a2cb31b3d5cb80e6}

Procédure de création de la file d’attente du disque, après avoir configuré le fichier txlogd.conf.

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

## Ajout du collecteur à l’application web {#section-d17297b1193f4e3cb150fb41f754ef12}

Pour les serveurs WebSphere, le collecteur fonctionne comme un filtre dans le conteneur de servlets.

Pour ajouter le collecteur à l’application web, ajoutez le filtre au descripteur de déploiement web.xml de l’application web, puis redémarrez l’application web.

1. À l’aide d’un éditeur de texte, ouvrez le fichier web.xml du serveur web dont le Capteur d’événements capture les événements.
1. Ajoutez ce qui suit : `<filter>` et `<filter-mapping>` au fichier descripteur. Si vous n’avez pas installé txlogd.conf dans le répertoire /etc, vous devez saisir le chemin d’accès correct à ce fichier dans la variable `<param-value>` élément .

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>C:/VisualSensor/txlogd.conf</param-value> 
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

1. Redémarrez l’application web. Le collecteur est chargé avec l’application et commence à collecter les données d’événement et à les écrire dans la file d’attente du disque.

## Déclarez l’emplacement du collecteur et des fichiers d’objets partagés {#section-e641f08999d34a648aaee2111b69ca25}

Procédure de modification du script de démarrage de Websphere pour déclarer l’emplacement des fichiers J2EECollector.jar et libVisual_sciences.so.

1. Ouvrez le fichier setupCmdLine.sh dans le répertoire /bin de WebSphere.
1. Après la ligne qui définit la variable $WAS_CLASSPATH , ajoutez la ligne suivante :

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. Après le bloc de casse qui définit la variable $WAS_LIBPATH , ajoutez la ligne suivante :

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Enregistrez le [!DNL setupCmdLine.sh] fichier .

## Test du capteur {#section-07f2da5c4caa46bf9dd1cb4ae4b61af5}

Procédure de démarrage de l’émetteur et de vérification de sa capacité à se connecter au serveur Insight et à lui transmettre des données d’événement.

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
   * Les paramètres ServerAddress et ServerPort sont correctement définis dans txtlogd.conf. Si vous avez spécifié ServerAddress à l’aide d’un nom de serveur, essayez plutôt d’utiliser son adresse IP numérique.
   * La valeur du paramètre CertName correspond exactement au nom commun qui apparaît sur le certificat numérique du serveur Insight cible.

## Ajout de l’émetteur au script de démarrage du système {#section-23bb905100d04f018af93873dd4d5f68}

Informations permettant de s’assurer que l’émetteur se charge automatiquement au redémarrage de la machine du serveur web.

Ajoutez la commande suivante (qui lance l&#39;émetteur) au script de démarrage du système.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Cette commande lance l&#39;émetteur comme démon. Les messages d&#39;exploitation et d&#39;erreur générés par l&#39;émetteur sont écrits dans syslog.

## Capture de données supplémentaires {#section-d5ccf8ee50914a87938e0c17480757e6}

Les capteurs de toutes les plateformes peuvent collecter toutes les données disponibles dans les en-têtes de requête et de réponse HTTP.

Les capteurs de la plateforme J2EE fournissent un mécanisme de collecte de données qui n’est pas disponible sur d’autres plateformes. Le collecteur de la plateforme J2EE (collecteur J2EE) se trouve sur la couche de l’application, ce qui lui permet de collecter des données sensibles qui sont disponibles uniquement pour l’application et ne doivent pas être exposées par le balisage de page ou dans les en-têtes.

>[!NOTE]
>
>Bien que les balises de page et la modification de l’en-tête puissent masquer les données, celles-ci restent accessibles pour ceux qui examinent le code source d’une page ou qui consultent les en-têtes à l’aide des outils de plug-in de navigateur.

Par exemple, le collecteur J2EE peut être utilisé pour capturer les données de coût par clic (CPC) pour les liens affichés sur une page, les informations sensibles sur les partenaires sur une page et de nombreux autres points de données. L’environnement J2EE vous permet de modifier facilement votre WEBAPP pour capturer ces données personnalisées à l’aide de notre classe de collecteur.

Lorsqu’un capteur de la plateforme J2EE reçoit une requête, il appelle une classe de collecteur qui importe la fonction appendToLog . La fonction appendToLog ajoute à la requête initiale les paramètres de chaîne de requête spécifiés dans la fonction appendToLog . Cela entraîne l’URI de la requête initiale contenant des paires nom-valeur de chaîne de requête supplémentaires qui correspondent aux noms et aux valeurs des données capturées. Par exemple, CPC=20 serait annexé à la demande initiale lorsque la valeur d’un emplacement de publicité ou d’un lien de clic publicitaire spécifique est de 20 cents. Insight Server traite ces valeurs dans le jeu de données à des fins d’analyse. Cette méthodologie de collecte présente un autre avantage : elle permet la collecte de données supplémentaires sans créer d’entrées de journal supplémentaires, comme elle peut être créée à l’aide des méthodologies de balisage de page.

Pour plus d’informations sur le traitement, voir *Guide de configuration des jeux de données*.

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
