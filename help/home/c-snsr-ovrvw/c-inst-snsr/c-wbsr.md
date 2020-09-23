---
description: Instructions détaillées pour l’installation et la configuration de Sensor for WebSphere 5.x exécuté sur AIX 5.1 ou version ultérieure.
solution: Analytics
title: WebSphere sous AIX
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1645'
ht-degree: 0%

---


# WebSphere sous AIX{#websphere-on-aix}

Instructions détaillées pour l’installation et la configuration de Sensor for WebSphere 5.x exécuté sur AIX 5.1 ou version ultérieure.

Les fichiers de programme pour [!DNL Sensor] sont compressés dans un fichier d’installation que vous obtenez du site de téléchargement de l’Adobe. Si vous ne disposez pas déjà du fichier [!DNL Sensor] d’installation pour votre serveur Web particulier, téléchargez-le (ou procurez-le auprès de votre représentant d’Adobe) avant de commencer les procédures suivantes.

>[!NOTE]
>
>Les serveurs WebSphere [!DNL Sensor] ne prennent pas en charge l’expérimentation contrôlée. Pour plus d&#39;informations sur l&#39;expérimentation contrôlée, consultez le Guide des expériences contrôlées *Data Workbench.*

## Installation des fichiers de Programme {#section-86f69127278c41bc90b97b68bb40bc6e}

Procédure d’extraction et d’installation des fichiers de programme pour Sensorto sur le serveur.

1. Connectez-vous en tant qu’utilisateur root ou en tant qu’utilisateur disposant de l’autorisation root.
1. Décompressez et décompressez le fichier d’installation à l’aide de la commande suivante :

   ```
   gunzip installationFilename.tar.gz 
   tar -xf installationFilename.tar
   ```

1. Copiez les fichiers de programme non compressés dans les répertoires identifiés dans le tableau suivant :

<table id="table_0E3B403071EF44AFBF0DD673EFEBBFE5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Cible Directory </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> Module de chargement du collecteur </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> Bibliothèques du module de chargement des collecteurs </td> 
   <td colname="col3"> Répertoire WebSphere /lib </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> Programme de l'émetteur </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
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

Par défaut, les fichiers de programme du fichier tar disposent des autorisations suivantes. Selon la configuration de votre système, ces paramètres peuvent être modifiés (non masqués) lors de l’extraction des fichiers.

Pour réinitialiser les autorisations aux paramètres par défaut recommandés, utilisez les commandes chmod ci-dessous.

>[!NOTE]
>
>Vérifiez que les répertoires dans lesquels vous avez installé les fichiers permettent au moins ce niveau d&#39;accès.

| Fichier | Autorisations par défaut | chmod, commande |
|---|---|---|
| libvisual_sciences.so | rwx —x —x | chmod 711 |
| J2EECollector.jar | rw- rw- r— | chmod 664 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

Si vous souhaitez utiliser des autorisations autres que les valeurs par défaut recommandées, consultez les informations fournies dans Autorisations de fichier UNIX de Sensor pour vous assurer que vous comprenez comment ces fichiers sont utilisés.

## Edit the Sensor Configuration file {#section-283c8a92fa8841c1b6034e5f834ef4e7}

Le fichier txlogd.conf contient les paramètres de configuration de Sensor.

Vous devez modifier le fichier pour indiquer, entre autres, la taille de la file d’attente de disque, l’adresse du serveur Insight et l’identifiant qui sera associé aux données produites par ce capteur.

Le fichier de configuration contient les paramètres requis et les paramètres facultatifs.

* Les paramètres requis sont des paramètres que vous devez spécifier lors de l’installation de Sensor. Sans ces paramètres, Sensor ne s’exécute pas correctement.
* Les paramètres facultatifs sont des paramètres qui, par défaut, correspondent à des valeurs prédéfinies (que vous pouvez modifier) ou qui activent des fonctionnalités facultatives.

**Pour modifier le fichier de configuration**

1. Ouvrez le fichier /etc/txlogd.conf dans un éditeur de texte et définissez les paramètres requis ainsi que les paramètres facultatifs de votre choix.
1. Enregistrez et fermez le fichier.

## Début de l&#39;émetteur et création de la file d&#39;attente de disque {#section-63285a2328604f20a2cb31b3d5cb80e6}

Procédure de création de la file d&#39;attente de disque, après avoir configuré le fichier txlogd.conf.

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

## ajouter le collecteur à l’Application web {#section-d17297b1193f4e3cb150fb41f754ef12}

Pour les serveurs WebSphere, le collecteur agit comme un filtre dans le conteneur de servlet.

Pour ajouter le collecteur à l’application Web, ajoutez le filtre au descripteur de déploiement web.xml de l’application Web, puis redémarrez l’application Web.

1. A l’aide d’un éditeur de texte, ouvrez le fichier web.xml pour le serveur Web dont événement Sensor capture les données.
1. ajoutez les éléments et éléments suivants `<filter>``<filter-mapping>` dans le fichier descripteur. Si vous n’avez pas installé txlogd.conf dans le répertoire /etc, vous devez entrer le chemin d’accès correct à ce fichier dans l’ `<param-value>` élément.

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
   >Ces lignes sont sensibles à la casse. Tapez-les exactement comme ils apparaissent ci-dessus.

1. Redémarrez l’application Web. Le collecteur est chargé avec l&#39;application et commencera à collecter les données de événement et à les écrire dans la file d&#39;attente de disque.

## Déclarer l&#39;emplacement du collecteur et des fichiers d&#39;objets partagés {#section-e641f08999d34a648aaee2111b69ca25}

Procédure de modification du script de démarrage de Websphere pour déclarer l&#39;emplacement des fichiers J2EECollector.jar et libvisual_sciences.so.

1. Ouvrez le fichier setupCmdLine.sh dans le répertoire Websphere /bin.
1. Après la ligne qui définit la variable $WAS_CLASSPATH, ajoutez la ligne suivante :

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. Après le bloc Case qui définit la variable $WAS_LIBPATH, ajoutez la ligne suivante :

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Save the [!DNL setupCmdLine.sh] file.

## Test du capteur {#section-07f2da5c4caa46bf9dd1cb4ae4b61af5}

Procédure de début de l’émetteur et de vérification de sa capacité à se connecter au serveur Insight et à lui transmettre les données du événement.

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
   * Les paramètres ServerAddress et ServerPort sont définis correctement dans txtlogd.conf. Si vous avez spécifié ServerAddress à l’aide d’un nom de serveur, essayez d’utiliser son adresse IP numérique à la place.
   * La valeur du paramètre CertName correspond exactement au nom commun qui apparaît sur le certificat numérique du serveur cible Insight.

## ajouter l&#39;émetteur à votre script de démarrage du système {#section-23bb905100d04f018af93873dd4d5f68}

Informations permettant de s’assurer que l’émetteur se charge automatiquement au redémarrage de l’ordinateur du serveur Web.

ajoutez la commande suivante (qui lance l&#39;émetteur) sur votre script de démarrage du système.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Cette commande début l&#39;émetteur en tant que démon. Les messages d&#39;exploitation et d&#39;erreur générés par l&#39;émetteur sont écrits sur syslog.

## Capture de données supplémentaires {#section-d5ccf8ee50914a87938e0c17480757e6}

Les capteurs de toutes les plateformes peuvent collecter toutes les données disponibles dans les en-têtes de requête et de réponse HTTP.

Les capteurs de la plate-forme J2EE fournissent un mécanisme de collecte de données qui n’est pas disponible sur d’autres plates-formes. Le collecteur de la plate-forme J2EE (collecteur J2EE) se trouve sur la couche d’application, ce qui lui permet de collecter des données sensibles qui ne sont disponibles que pour l’application et ne doivent pas être exposées par balisage de page ou dans les en-têtes.

>[!NOTE]
>
>Bien que les balises de page et la modification de l’en-tête puissent masquer les données, celles-ci restent accessibles à ceux qui examinent le code source d’une page ou regardent les en-têtes à l’aide des outils de module complémentaire du navigateur.

Par exemple, le collecteur J2EE peut être utilisé pour capturer les données de coût par clic (CPC) pour les liens affichés sur une page, les informations de partenaire sensibles sur une page et de nombreux autres points de données. L&#39;environnement J2EE vous permet de modifier facilement votre WEBAPP pour capturer ces données personnalisées à l&#39;aide de notre classe de collecteurs.

Lorsqu’un capteur pour la plate-forme J2EE reçoit une demande, il appelle une classe de collecteur qui importe la fonction appendToLog. La fonction appendToLog ajoute à la requête initiale les paramètres de chaîne de requête spécifiés dans la fonction appendToLog. Ceci génère l’URI de la requête initiale contenant des paires nom-valeur de chaîne de requête supplémentaires qui correspondent aux noms et aux valeurs des données capturées. Par exemple, CPC=20 est ajouté à la demande initiale lorsque la valeur d’un emplacement d’annonce ou d’un lien de clic publicitaire particulier est de 20 cents. Insight Server traite ces valeurs dans le jeu de données pour analyse. Cette méthodologie de collecte présente un autre avantage : elle permet la collecte de données supplémentaires sans créer d’entrées de journal supplémentaires, comme cela peut être le cas avec les méthodologies de balisage de page.

Pour plus d&#39;informations sur le traitement, consultez le Guide *de configuration des jeux de* données.

1. ajoutez le code suivant en haut de la page .jsp à partir de laquelle vous souhaitez capturer des données :

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

   L&#39;URI de demande qui en résulte est /index.jsp?A=1&amp;B=2.

1. Répétez cette procédure pour chaque page .jsp à partir de laquelle vous souhaitez capturer des données supplémentaires.

