---
description: Instructions sur l’installation et la configuration de Sensor for Internet Information Services (IIS) 5.x ou 6.x s’exécutant sous Microsoft Windows Server 2000 ou version ultérieure.
title: Microsoft IIS sous Windows Server 2000 ou ultérieur
uuid: 26da0638-82c8-424f-9f00-aab3a940e5a9
exl-id: e4b5ac44-b0ac-43be-9b9c-180a64354081
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1718'
ht-degree: 1%

---

# Microsoft IIS sous Windows Server 2000 ou ultérieur{#microsoft-iis-on-windows-server-or-later}

Instructions sur l’installation et la configuration de Sensor for Internet Information Services (IIS) 5.x ou 6.x s’exécutant sous Microsoft Windows Server 2000 ou version ultérieure.

Lorsque vous utilisez IIS 6.x, la journalisation doit être activée pour que Capteur fonctionne correctement. Si vous avez désactivé la journalisation afin de réduire les E/S du disque, vous pouvez activer la journalisation sans écrire de données dans les journaux. Pour ce faire, activez la journalisation, puis effacez tous les champs de l’onglet Avancé des Propriétés du format de fichier journal étendu W3C. Si vous avez besoin d’aide, contactez les services de conseil d’Adobe.

Les fichiers de programme pour Capteur sont contenus dans un fichier d’installation que vous obtenez sur le site de téléchargement de l’Adobe. Si vous ne disposez pas déjà du fichier d’installation de Capteur pour votre serveur web en particulier, téléchargez-le (ou procurez-le auprès de votre représentant d’Adobe) avant de commencer les procédures suivantes.

Pour installer et configurer Capteur, vous devez effectuer les étapes de haut niveau suivantes :

## 1. Installation des fichiers de programme {#section-9ef8c4e38c244b7d8b6d4bc6c0ad53fd}

Lors de l’exécution de Capteur sous Windows IIS, les fichiers de programme et le fichier de file d’attente du disque doivent se trouver dans le même répertoire.

Par conséquent, avant d’installer les fichiers de programme, vous devez déterminer où vous souhaitez conserver la file d’attente du disque, car c’est également là que vous devez installer les fichiers de programme.

Procédez comme suit pour extraire et installer les fichiers de programme pour Capteur.

1. Sur votre ordinateur Windows, créez un répertoire dans lequel installer les fichiers du programme Capteur. Gardez à l’esprit que votre file d’attente de disque réside également dans ce répertoire. Assurez-vous donc que le périphérique choisi dispose de suffisamment d’espace pour contenir une file d’attente de la taille dont vous avez besoin.

   Par exemple : C:\VisualSensor

1. Extrayez le contenu du fichier d&#39;installation dans le répertoire que vous venez de créer. Au cours de cette étape, Capteur installe les fichiers suivants :

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
   <td colname="col2"> Messages de la visionneuse d’événements. </td>
  </tr>
  <tr>
   <td colname="col1"> qlog.dll </td>
   <td colname="col2"> Le module collecteur (un filtre ISAPI). </td>
  </tr>
  <tr>
   <td colname="col1"> TestExperiment.xls </td>
   <td colname="col2"> <p>Fichier de feuille de calcul Excel que les architectes peuvent utiliser pour configurer une expérience contrôlée. </p> <p>Capteur n’utilise pas ce fichier. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> trust_ca_cert.pem </td>
   <td colname="col2"> Certificat utilisé pour valider le certificat numérique qu’Insight Server présente pendant le processus de connexion. </td>
  </tr>
  <tr>
   <td colname="col1"> TXLog.exe </td>
   <td colname="col2"> Le programme de l'émetteur. </td>
  </tr>
  <tr>
   <td colname="col1"> txlogd.conf </td>
   <td colname="col2"> Le fichier de configuration de Capteur. </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>Le package d’installation contient un fichier de feuille de calcul appelé TestExperiment.xls. Cette feuille de calcul est un outil que les architectes utilisent pour configurer une expérience contrôlée. Sensor n’utilise pas ce fichier. Il n’est donc pas nécessaire d’installer le fichier sur l’ordinateur sur lequel Sensor est exécuté (bien que vous puissiez choisir de le faire). Vous pouvez plutôt copier le fichier vers un emplacement accessible par vos architectes ou simplement extraire le fichier du package d’installation, si nécessaire. Pour plus d’informations sur l’expérimentation contrôlée, consultez le guide des expériences contrôlées Insight .

## 2. Modification du fichier de configuration {#section-206daf855e664f16af9a96a5cd3e62b1}

Le fichier txlogd.conf contient les paramètres de configuration de Capteur.

Vous devez modifier le fichier pour indiquer, entre autres, la taille de la file d’attente du disque, l’adresse du serveur Insight et l’identifiant qui sera joint aux données générées par ce capteur. Le fichier de configuration contient les paramètres requis et les paramètres facultatifs.

* **Les** paramètres requis sont des paramètres que vous devez spécifier lorsque vous installez Capteur. Sans ces paramètres, Capteur ne s’exécute pas correctement.
* **Les** paramètres facultatifs sont des paramètres qui activent par défaut des valeurs prédéfinies (que vous pouvez modifier) ou des fonctionnalités facultatives.

**Modification du fichier de configuration du capteur**

1. Ouvrez le fichier `<SensorDirectory>/txlogd.conf` dans un éditeur de texte et définissez les paramètres requis ainsi que les paramètres facultatifs souhaités.

   Pour obtenir des descriptions des paramètres txlogd.conf, voir Paramètres de fichier Txlogd.conf de Capteur.

   Pour obtenir des exemples de fichiers de configuration terminés, voir Exemple de fichiers de configuration de Capteur.

1. Enregistrez le fichier, puis fermez-le.

## 3. Démarrez l’émetteur et créez la file d’attente du disque {#section-a0af390ee1954109bcff5d9f09798683}

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

   >[!NOTE]
   >
   >Cette séquence de commandes peut varier en fonction de la version de Windows utilisée.

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

## Ajout du collecteur au serveur web {#section-682dc480e5574791ac18da104daf7906}

Pour IIS, le collecteur est un filtre ISAPI que vous ajoutez à votre serveur web dans IIS.

1. Ouvrez le Gestionnaire des services Internet à l’aide de Démarrer > Outils d’administration > Gestionnaire des services d’informations Internet (IIS).
1. Développez les noeuds Ordinateur local et Sites web .
1. Cliquez avec le bouton droit sur le site web auquel vous souhaitez ajouter le collecteur et sélectionnez Propriétés.
1. Sélectionnez l’onglet Filtres ISAPI et cliquez sur Ajouter.
1. Dans le champ Nom du filtre , saisissez un nom d’affichage pour le filtre. Le nom de filtre suggéré est &quot;Capteur&quot;.
1. Cliquez sur Parcourir, sélectionnez le fichier qlog.dll (situé dans le répertoire où vous avez installé Capteur), puis cliquez sur OK.
1. Cliquez sur OK pour ajouter le filtre.

   Une fois le filtre ajouté, le collecteur est immédiatement opérationnel et prêt à collecter des données. Une flèche verte ascendante doit apparaître dans la colonne État de l’onglet Filtres ISAPI du Gestionnaire IIS. Il se peut que vous ne voyiez pas la flèche verte tant que le trafic ne passe pas réellement dans le filtre. Dans ce cas, vous devez envoyer une requête au serveur web pour confirmer que le collecteur fonctionne correctement.

Si la flèche verte n’apparaît pas après le flux de trafic vers le collecteur, effectuez les étapes suivantes :

1. Cliquez sur Démarrer > Outils d’administration > Visionneuse d’événements pour rechercher les erreurs dans la visionneuse d’événements.

   >[!NOTE]
   >
   >Cette séquence de commandes peut varier en fonction de la version de Windows utilisée.

1. Dans le volet de gauche de la fenêtre Event Viewer, sélectionnez le journal de l’application.
1. Dans le volet de droite, recherchez les événements avec &quot;Adobe&quot; dans la colonne Source .
1. Si une erreur s’affiche, double-cliquez sur l’erreur pour afficher la fenêtre Event Properties.

## Capture de données supplémentaires {#section-dcd10073eb1947a5928e4f9b9fa99e3a}

Les pages web sont souvent structurées à l’aide du langage de programmation ASP (Principal Server Pages).

ASP est une technologie Microsoft qui s’exécute dans IIS. Lorsqu’un navigateur demande un fichier ASP, IIS transmet la demande au moteur ASP. Le moteur ASP lit le fichier ASP ligne par ligne et exécute les scripts du fichier. Enfin, le fichier ASP est renvoyé au navigateur en tant que HTML brut. ASP fournit des objets RESPOND ou REQUEST qui, en plus d’autres utilisations, permettent la réponse ou la requête des requêtes utilisateur ou des données envoyées à partir de formulaires de HTML.

Dans certains cas, vous pouvez ne pas ajouter les valeurs saisies dans les formulaires à l’URL affichée dans la barre d’adresse du navigateur d’un utilisateur ou visible dans le code de HTML lui-même. Un script ASP simple côté serveur vous permet d’ajouter des noms de champ de formulaire et leurs valeurs respectives au fichier journal sans les rendre disponibles dans le navigateur de l’utilisateur ni les incorporer dans le fichier de HTML. Pour capturer les valeurs de formulaire réelles saisies dans des formulaires spécifiques de votre site web, quelques lignes de code doivent être ajoutées pour ajouter les valeurs de formulaire à la requête de journal.

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

Ce processus ajoute les valeurs de formulaire telles que définies aux données de requête de la page de traitement du formulaire. Dans les données du journal, les valeurs ajoutées seraient disponibles sous forme de chaînes de requête dans la page de traitement du formulaire, comme illustré ci-dessous. Par exemple, v_1, v_2, v_3 et v_4 seront désormais des chaînes de requête contenant les données saisies dans les champs de formulaire appropriés. La syntaxe décrite dans l’exemple précédent peut être dupliquée pour les champs et valeurs de formulaire supplémentaires que vous souhaitez capturer :

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Si vous souhaitez que chaque champ et valeur de formulaire soit capturés et disponible pour analyse, vous pouvez utiliser la syntaxe suivante :

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

Cet exemple prend tous les champs de formulaire présents dans le HTML avec leurs valeurs respectives et les ajoute en tant que chaînes de requête à l’entrée de journal de la page de traitement du formulaire. Veuillez noter que cela inclut tous les champs masqués présents dans le formulaire.

Les données du journal seraient augmentées comme décrit dans le tableau suivant :

| Données collectées | Description | Exemple |
|---|---|---|
| v_1 | Valeur associée à la chaîne de requête NAME | v_1=John Smith |
| v_2 | Valeur associée à la chaîne de requête CITY | v_2=Los Angeles |
| v_3 | Valeur associée à la chaîne de requête STATE | v_3=Californie |
| v_4 | Valeur associée à la chaîne de requête ZIP | v_4=90210 |
