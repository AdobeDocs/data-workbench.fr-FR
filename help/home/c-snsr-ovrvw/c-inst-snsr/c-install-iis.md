---
description: Instructions relatives à l’installation et à la configuration de Sensor for Internet Information Services (IIS) 5.x ou 6.x sous Microsoft Windows Server 2000 ou version ultérieure.
title: Microsoft IIS sur Windows Server 2000 ou version ultérieure
uuid: 26da0638-82c8-424f-9f00-aab3a940e5a9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Microsoft IIS sur Windows Server 2000 ou version ultérieure{#microsoft-iis-on-windows-server-or-later}

Instructions relatives à l’installation et à la configuration de Sensor for Internet Information Services (IIS) 5.x ou 6.x sous Microsoft Windows Server 2000 ou version ultérieure.

Lors de l’utilisation d’IIS 6.x, la journalisation doit être activée pour que Sensor fonctionne correctement. Si vous avez désactivé la journalisation pour réduire les E/S du disque, vous pouvez activer la journalisation sans écrire aucune donnée dans les journaux. Pour ce faire, activez la journalisation, puis effacez tous les champs de l&#39;onglet Avancé des Propriétés du format de fichier journal étendu W3C. Si vous avez besoin d’aide, contactez les services de conseil Adobe.

Les fichiers programme de Sensor sont compressés dans un fichier d’installation que vous obtenez du site de téléchargement d’Adobe. Si vous ne disposez pas déjà du fichier d’installation de Sensor pour votre serveur Web particulier, téléchargez-le (ou obtenez-le auprès de votre représentant Adobe) avant de commencer les procédures suivantes.

Pour installer et configurer Sensor, vous devez effectuer les étapes de haut niveau suivantes :

## 1. Installation des fichiers du programme {#section-9ef8c4e38c244b7d8b6d4bc6c0ad53fd}

Lors de l’exécution de Sensor sur Windows IIS, les fichiers programme et le fichier de file d’attente de disque doivent résider dans le même répertoire.

Par conséquent, avant d&#39;installer les fichiers du programme, vous devez déterminer où vous souhaitez conserver la file d&#39;attente du disque, car c&#39;est également là que vous devez installer les fichiers du programme.

Procédez comme suit pour extraire et installer les fichiers programme pour Sensor.

1. Sur votre ordinateur Windows, créez un répertoire dans lequel installer les fichiers du programme Sensor. Gardez à l’esprit que votre file d’attente de disque réside également dans ce répertoire. Assurez-vous donc que le périphérique choisi dispose d’un espace suffisant pour contenir une file d’attente de la taille dont vous avez besoin.

   Par exemple : C:\VisualSensor

1. Extrayez le contenu du fichier d&#39;installation dans le répertoire que vous venez de créer. Au cours de cette étape, Sensor installe les fichiers suivants :

<table id="table_C9E8803E51D046FD8FCCA38F8DAC04D1"> 
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
   <td colname="col1"> qlog.dll </td> 
   <td colname="col2"> Module collecteur (filtre ISAPI). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TestExperiment.xls </td> 
   <td colname="col2"> <p>Fichier de feuille de calcul Excel que les architectes peuvent utiliser pour configurer une expérience contrôlée. </p> <p>Sensor n’utilise pas ce fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificat utilisé pour valider le certificat numérique présenté par Insight Server pendant le processus de connexion. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> Le programme d'émetteur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Fichier de configuration de Sensor. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le package d’installation contient un fichier de feuille de calcul appelé TestExperiment.xls. Cette feuille de calcul est un outil que les architectes utilisent pour configurer une expérience contrôlée. Sensor n’utilise pas ce fichier, il n’est donc pas nécessaire d’installer le fichier sur l’ordinateur sur lequel Sensor est en cours d’exécution (bien que vous puissiez choisir de le faire). Vous souhaiterez peut-être copier le fichier vers un emplacement accessible par vos architectes ou simplement extraire le fichier du package d’installation, le cas échéant. Pour plus d&#39;informations sur l&#39;expérimentation contrôlée, consultez le Guide des expériences contrôlées Insight.

## 2. Modification du fichier de configuration {#section-206daf855e664f16af9a96a5cd3e62b1}

Le fichier txlogd.conf contient les paramètres de configuration de Sensor.

Vous devez modifier le fichier pour indiquer, entre autres, la taille de la file d’attente du disque, l’adresse du serveur Insight et l’ID qui sera joint aux données produites par ce capteur. Le fichier de configuration contient les paramètres obligatoires et facultatifs.

* **Les paramètres** requis sont des paramètres que vous devez spécifier lorsque vous installez Sensor. Sans ces paramètres, Sensor ne fonctionne pas correctement.
* **Les paramètres** facultatifs sont des paramètres qui, par défaut, utilisent des valeurs prédéfinies (que vous pouvez modifier) ou activent des fonctionnalités facultatives.

**Pour modifier le fichier de configuration de Sensor**

1. Ouvrez le `<SensorDirectory>/txlogd.conf` fichier dans un éditeur de texte et définissez les paramètres requis ainsi que les paramètres facultatifs de votre choix.

   Pour obtenir la description des paramètres txlogd.conf, voir Paramètres du fichier Sensor Txlogd.conf.

   Pour obtenir des exemples de fichiers de configuration terminés, reportez-vous à la section Fichiers de configuration Sensor.

1. Enregistrez et fermez le fichier.

## 3. Démarrage de l&#39;émetteur et création de la file d&#39;attente du disque {#section-a0af390ee1954109bcff5d9f09798683}

Après avoir configuré le fichier txlogd.conf, vous pouvez démarrer le programme d’émetteurs, l’enregistrer en tant que service Windows et créer la file d’attente des disques.

1. Dans le menu Démarrer de Windows, sélectionnez Accessoires > Invite de commandes.
1. Dans la fenêtre d’invite de commande, accédez au répertoire dans lequel vous avez installé Sensor et exécutez la commande suivante :

   ```
   txlog /regserver
   ```

   Cette commande démarre l’émetteur, crée la file d’attente du disque et enregistre Sensor en tant que service Windows.

1. Pour vérifier que l’émetteur s’exécute correctement, cliquez sur Démarrer > Panneau de configuration > Outils d’administration > Services.

   >[!NOTE]
   >
   >Cette séquence de commandes peut varier selon la version de Windows utilisée.

   1. Dans la liste des services, recherchez l’entrée de Sensor et vérifiez que son état est Démarré et que son type de démarrage est Automatique.
   1. Fermez le panneau de configuration Services.

1. Pour vérifier si l’émetteur a rencontré des erreurs au démarrage, cliquez sur Démarrer > Panneau de configuration > Outils d’administration > Observateur d’événements pour ouvrir l’Observateur d’événements.

   >[!NOTE]
   >
   >Cette séquence de commandes peut varier selon la version de Windows utilisée.

   1. Dans le volet gauche de la fenêtre Observateur d’événements, sélectionnez le journal des applications.
   1. Dans le volet de droite, recherchez les événements avec &quot;Adobe&quot; dans la colonne Source.
   1. Si vous trouvez une erreur provenant d’Adobe, cliquez deux fois sur l’erreur pour afficher la fenêtre Propriétés de l’événement. Cette fenêtre fournit des informations détaillées sur l’erreur.

1. Lorsque vous avez terminé d’examiner le journal des applications, fermez l’Observateur d’événements.
1. Vérifiez que l’émetteur a créé la file d’attente du disque (Diskq2000.log) dans le répertoire où vous avez installé les fichiers du programme Sensor et que c’est la taille que vous avez spécifiée dans le paramètre QueueSize du fichier txlogd.conf.

   Si la file d’attente n’a pas été créée correctement :

   1. Examinez le fichier txtlogd.conf et vérifiez que le paramètre QueueSize est défini correctement.
   1. Vérifiez que le périphérique sur lequel vous avez installé Sensor dispose d’un espace suffisant pour contenir un fichier de la taille spécifiée dans le paramètre QueueSize.
   1. A l’aide du panneau de contrôle Services de Windows, arrêtez l’émetteur.
   1. Supprimez le fichier de file d’attente.
   1. Réinscrivez Sensor en tant que service Windows : dans le menu Démarrer de Windows, sélectionnez Accessoires > Invite de commandes. Dans la fenêtre d’invite de commande, accédez au répertoire dans lequel vous avez installé Sensor et exécutez la commande suivante :

      ```
      txlog /regserver
      ```

L&#39;émetteur est conçu pour fonctionner en continu. Si vous redémarrez l’ordinateur, l’émetteur redémarre automatiquement. Si vous devez démarrer et arrêter l’émetteur manuellement, vous pouvez le faire à l’aide du panneau de configuration Services de Windows.

## Ajout du collecteur au serveur Web {#section-682dc480e5574791ac18da104daf7906}

Pour IIS, le collecteur est un filtre ISAPI que vous ajoutez à votre serveur Web dans IIS.

1. Ouvrez le Gestionnaire IIS à l’aide de Démarrer > Outils d’administration > Gestionnaire des services IIS (Internet Information Services).
1. Développez les noeuds Ordinateur local et Sites Web.
1. Cliquez avec le bouton droit sur le site Web auquel vous souhaitez ajouter le collecteur et sélectionnez Propriétés.
1. Sélectionnez l’onglet Filtres ISAPI et cliquez sur Ajouter.
1. Dans le champ Nom du filtre, saisissez le nom d’affichage du filtre. Le nom de filtre suggéré est &quot;Capteur&quot;.
1. Cliquez sur Parcourir, sélectionnez le fichier qlog.dll (situé dans le répertoire où vous avez installé Sensor), puis cliquez sur OK.
1. Cliquez sur OK pour ajouter le filtre.

   Une fois le filtre ajouté, le collecteur est immédiatement opérationnel et prêt à collecter des données. Une flèche verte vers le haut doit apparaître dans la colonne État de l&#39;onglet Filtres ISAPI du Gestionnaire IIS. Vous ne verrez peut-être pas la flèche verte tant que le trafic n’est pas réellement traversé par le filtre. Dans ce cas, vous devez envoyer une requête au serveur Web pour vérifier que le collecteur fonctionne correctement.

Si la flèche verte n’apparaît pas après le flux du trafic vers le collecteur, procédez comme suit :

1. Cliquez sur Démarrer > Outils d’administration > Observateur d’événements pour rechercher les erreurs dans l’Observateur d’événements.

   >[!NOTE]
   >
   >Cette séquence de commandes peut varier selon la version de Windows utilisée.

1. Dans le volet gauche de la fenêtre Observateur d’événements, sélectionnez le journal des applications.
1. Dans le volet de droite, recherchez les événements avec &quot;Adobe&quot; dans la colonne Source.
1. Si vous trouvez une erreur, cliquez deux fois sur l’erreur pour afficher la fenêtre Propriétés de l’événement.

## Capture de données supplémentaires {#section-dcd10073eb1947a5928e4f9b9fa99e3a}

Les pages Web sont souvent structurées à l&#39;aide du langage de programmation ASP (Active Server Pages).

ASP est une technologie Microsoft qui s&#39;exécute dans IIS. Lorsqu&#39;un navigateur demande un fichier ASP, IIS transmet la requête au moteur ASP. Le moteur ASP lit le fichier ASP, ligne par ligne, et exécute les scripts du fichier. Enfin, le fichier ASP est renvoyé au navigateur sous forme de code HTML brut. ASP fournit des objets RESPOND ou REQUEST qui, en plus d&#39;autres utilisations, permettent la réponse ou la requête des requêtes utilisateur ou des données envoyées à partir de formulaires HTML.

Dans certains cas, vous pouvez ne pas ajouter les valeurs entrées dans les formulaires à l’URL affichée dans la barre d’adresse du navigateur d’un utilisateur ou qui est consultable dans le code HTML lui-même. Le script ASP côté serveur simple vous permet d’ajouter des noms de champ de formulaire et leurs valeurs respectives au fichier journal sans les rendre disponibles dans le navigateur de l’utilisateur ni les incorporer dans le fichier HTML. Pour capturer les valeurs de formulaire réelles saisies dans des formulaires particuliers de votre site Web, vous devez ajouter quelques lignes de code pour ajouter les valeurs de formulaire à la requête de journal.

Dans la page de traitement d’un formulaire, incluez le code suivant pour ajouter les valeurs de formulaire saisies aux données de requête (en plus d’écrire les valeurs de formulaire envoyées dans une base de données externe ou à un autre emplacement) :

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

Ce processus ajoute les valeurs de formulaire telles que définies aux données de requête pour la page de traitement des formulaires. Dans les données du journal, les valeurs ajoutées sont disponibles sous forme de chaînes de requête dans la page Traitement du formulaire, comme illustré ci-dessous. Par exemple, v_1, v_2, v_3 et v_4 sont désormais des chaînes de requête contenant les données saisies dans les champs de formulaire appropriés. La syntaxe décrite dans l’exemple précédent peut être dupliquée pour tous les champs et valeurs de formulaire supplémentaires que vous souhaitez capturer :

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Si vous souhaitez que chaque champ et valeur de formulaire soit capturés et disponible pour l’analyse, vous pouvez utiliser la syntaxe suivante :

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues);
```

Cet exemple montre comment prendre tous les champs de formulaire présents dans le code HTML avec leurs valeurs respectives et les ajouter en tant que chaînes de requête à l’entrée du journal pour la page de traitement du formulaire. Veuillez noter que cela inclurait tous les champs masqués présents dans le formulaire.

Les données du journal seraient augmentées comme indiqué dans le tableau suivant :

| Données collectées | Description | Exemple |
|---|---|---|
| v_1 | Valeur associée à la chaîne de requête NAME | v_1=John Smith |
| v_2 | Valeur associée à la chaîne de requête CITY | v_2=Los Angeles |
| v_3 | Valeur associée à la chaîne de requête STATE | v_3=Californie |
| v_4 | Valeur associée à la chaîne de requête ZIP | v_4=90210 |
