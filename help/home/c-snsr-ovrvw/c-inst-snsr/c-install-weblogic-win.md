---
description: Instructions détaillées sur l’installation et la configuration de Capteur pour WebLogic Server 6.x ou version ultérieure s’exécutant sous Microsoft Windows Server 2000 ou version ultérieure.
title: Serveur WebLogic sous Windows Server 2000 ou ultérieur
uuid: 80dbf544-bd09-4af8-bb05-4032eb49dd5d
exl-id: cf5b5284-dd61-4c55-8319-483bfe60930c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 1%

---

# Serveur WebLogic sous Windows Server 2000 ou ultérieur{#weblogic-server-on-windows-server-or-later}

{{eol}}

Instructions détaillées sur l’installation et la configuration de Capteur pour WebLogic Server 6.x ou version ultérieure s’exécutant sous Microsoft Windows Server 2000 ou version ultérieure.

Les fichiers de programme pour Capteur sont contenus dans un fichier d’installation que vous obtenez sur le site de téléchargement de l’Adobe. Si vous ne disposez pas déjà du fichier d’installation de Capteur pour votre serveur web en particulier, téléchargez-le (ou procurez-le auprès de votre représentant d’Adobe) avant de commencer les procédures suivantes.

Pour installer et configurer Capteur, procédez comme suit :

## Installation des fichiers de programme {#section-2f3e85083b4f4aa989a85997330e86ae}

Procédure d’extraction et d’installation des fichiers de programme pour Capteur.

1. Sur WebLogic Server, créez un répertoire dans lequel installer les fichiers du programme Capteur. Gardez à l’esprit que votre file d’attente de disque se trouve dans ce répertoire. Assurez-vous donc que le périphérique choisi dispose de suffisamment d’espace pour contenir une file d’attente de la taille dont vous avez besoin.

   ```
   C:\VisualSensor
   ```

1. Extrayez le contenu du fichier d&#39;installation dans le répertoire que vous venez de créer. Au cours de cette étape, Capteur installe les fichiers suivants :

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
   <td colname="col1"> Visual_sciences.dll </td> 
   <td colname="col2"> Module de chargement du collecteur. </td> 
   <td colname="col3"> Dans n’importe quel répertoire. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> Bibliothèques du module de chargement de collecteur </td> 
   <td colname="col3"> WEB-INF/lib </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd.exe </p> </td> 
   <td colname="col2"> Le programme de l'émetteur. </td> 
   <td colname="col3"> Dans n’importe quel répertoire </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Le fichier de configuration de Capteur. </td> 
   <td colname="col3"> Dans n’importe quel répertoire </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificat utilisé pour valider le certificat numérique qu’Insight Server présente pendant le processus de connexion </td> 
   <td colname="col3"> Dans n’importe quel répertoire </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le package d’installation contient un fichier de feuille de calcul appelé [!DNL TestExperiment.xls]. Cette feuille de calcul est un outil que les architectes utilisent pour configurer une expérience contrôlée. Sensor n’utilise pas ce fichier. Il n’est donc pas nécessaire d’installer le fichier sur l’ordinateur sur lequel Sensor est exécuté (bien que vous puissiez choisir de le faire). Vous pouvez plutôt copier le fichier vers un emplacement accessible par vos architectes ou simplement extraire le fichier du package d’installation, si nécessaire. Pour plus d’informations sur l’expérimentation contrôlée, consultez le guide des expériences contrôlées Insight .

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

1. Dans le menu Démarrer de Windows, sélectionnez Accessoires > Invite de commande.
1. Dans la fenêtre de l’invite de commande, accédez au répertoire dans lequel vous avez installé Capteur et exécutez la commande suivante :

   ```
   txlog /regserver
   ```

   Cette commande démarre l’émetteur, crée la file d’attente du disque et enregistre Sensor en tant que service Windows.

1. Pour vérifier que l&#39;émetteur s&#39;exécute correctement, cliquez sur Démarrer > Panneau de Contrôle > Outils d&#39;administration > Services.

   >[!NOTE]
   >
   >Cette séquence de commandes peut varier en fonction de la version de Windows utilisée.

   1. Dans la liste des services, recherchez l’entrée de Capteur et vérifiez que son état est Démarré et que son type de démarrage est Automatique.
   1. Fermez le panneau de configuration Services .

1. Pour vérifier si l&#39;émetteur a rencontré des erreurs au démarrage, cliquez sur Démarrer > Panneau de Contrôle > Outils d&#39;administration > Visionneuse d&#39;événements pour ouvrir la visionneuse d&#39;événements.

   1. Dans le volet gauche de la fenêtre Visionneuse d’événements , sélectionnez le Journal des applications .
   1. Dans le volet de droite, recherchez les événements avec &quot;Adobe&quot; dans la colonne Source .
   1. Si vous trouvez une erreur dans &quot;Adobe&quot;, double-cliquez sur l’erreur pour afficher la fenêtre Event Properties (Propriétés de l’événement). Cette fenêtre fournit des informations détaillées sur l’erreur.

1. Lorsque vous avez terminé d’examiner le journal des applications, fermez la visionneuse d’événements.
1. Vérifiez que l&#39;émetteur a créé la file d&#39;attente du disque (Diskq2000.log) dans le répertoire où vous avez installé les fichiers du programme Capteur et que c&#39;est la taille que vous avez spécifiée dans le paramètre QueueSize du fichier txlogd.conf.

   Si la file d’attente n’a pas été créée correctement :

   1. Examinez le fichier txtlogd.conf et vérifiez que le paramètre QueueSize est correctement défini.
   1. Vérifiez que le périphérique sur lequel vous avez installé Capteur dispose de suffisamment d’espace disponible pour contenir un fichier de la taille spécifiée dans le paramètre QueueSize .
   1. À l’aide du panneau de configuration Services sous Windows, arrêtez l’émetteur.
   1. Supprimez le fichier de file d’attente.
   1. Réenregistrer Capteur en tant que service Windows : dans le menu Démarrer de Windows, sélectionnez Accessoires > Invite de commande. Dans la fenêtre de l’invite de commande, accédez au répertoire dans lequel vous avez installé Capteur et exécutez la commande suivante :

      ```
      txlog /regserver
      ```

L&#39;émetteur est conçu pour fonctionner en continu. Si vous redémarrez la machine, l&#39;émetteur redémarre automatiquement. Si vous devez démarrer et arrêter l&#39;émetteur manuellement, vous pouvez le faire à l&#39;aide du panneau de configuration Services de Windows.

## Ajout du collecteur au serveur web {#section-c5b83ae4ebce430aa764f951e849b333}

Pour les serveurs JBoss, le collecteur fonctionne comme un filtre dans le conteneur de servlets.

Pour ajouter le collecteur à votre serveur web, vous devez modifier la variable [!DNL web.xml] comme décrit ci-dessous et redémarrez votre application web.

1. À l’aide d’un éditeur de texte, ouvrez le [!DNL web.xml] pour le serveur web dont le Capteur d’événements capture les événements.
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

1. Redémarrez le processus du serveur web (il n’est pas nécessaire de redémarrer l’ensemble de l’ordinateur serveur, il suffit de redémarrer le processus du serveur web). Le collecteur est chargé avec le serveur web et commence à collecter les données d’événement et à les écrire dans la file d’attente du disque.

## Modification du script de démarrage {#section-0dae181ef8884f10a57f6cfda8500969}

Instructions pour la modification du script de démarrage.

Dans le script utilisé pour démarrer WebLogic (par exemple, C:\bea\user_projects\mydomain\startServer.cmd), modifiez la ligne &quot;set JAVA_OPTIONS=&quot; pour définir la définition java.library.path sur le répertoire contenant le fichier Visual_sciences.dll .

```
set JAVA_OPTIONS=-Djava.library.path=C:\Sensor 
    directory
```

## Capture de données supplémentaires {#section-9483b663cbd0432daaca50c1089c7fca}

Vous pouvez capturer des données de mesure supplémentaires à partir d’applications web J2EE à l’aide de la fonctionnalité appendToLog() .

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
