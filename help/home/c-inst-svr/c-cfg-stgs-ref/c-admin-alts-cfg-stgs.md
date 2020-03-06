---
description: Instructions de configuration des alertes administratives pour Insight Server, Repeater ou Transform.
solution: Insight
title: Paramètres de configuration des alertes d’administration
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Paramètres de configuration des alertes d’administration{#administrative-alerts-configuration-settings}

Instructions de configuration des alertes administratives pour Insight Server, Repeater ou Transform.

Renseignez les paramètres dans le fichier suivant :

[!DNL Product Name installation directory\Components\Administrative Alerts.cfg]

<table id="table_5A2298906D5F4215B8FAC42CACBC0002"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Catégorie </td> 
   <td colname="col2"> Nom de la catégorie. Une catégorie Valeur par défaut est requise. Voir Catégories d’erreurs dans ce tableau. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Catégories d’erreur </td> 
   <td colname="col2"> Vous permet de classer les erreurs conjointement avec le fichier de catégorisation des erreurs. Chaque catégorie d’erreur peut avoir son propre jeu de destinataires et son propre délai de ralentissement. Par exemple, vous pouvez créer une catégorie Critique avec un délai de ralentissement de 0, de sorte que chaque erreur critique soit immédiatement envoyée par courriel aux destinataires spécifiés dans la liste Destinataires. Les erreurs qui ne correspondent pas à une sous-chaîne dans le fichier de catégorisation des erreurs sont affectées à la catégorie Par défaut. Pour ajouter une nouvelle catégorie, cliquez avec le bouton droit sur un nombre et cliquez sur <span class="uicontrol"> Ajouter nouveau </span> &gt; <span class="uicontrol"> Catégorie d’erreur </span>. Vous pouvez également les copier ou les supprimer à l’aide de l’action de clic droit. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier de classification des erreurs </td> 
   <td colname="col2"> <p>nom du fichier à utiliser pour classer chaque alerte. Vous créez ce fichier à l’aide du Bloc-notes. Ce fichier doit comporter trois colonnes sur chaque ligne, séparées par des onglets. La première colonne est une chaîne à faire correspondre dans les erreurs. Un signe ^ correspond au début et un $ à la fin de la chaîne ; tous les autres caractères correspondent littéralement. La deuxième colonne est une catégorie pour les erreurs qui correspondent, qui se trouve dans Catégories d’erreurs. Le troisième est un autre message, qui est ajouté en regard du message d’erreur réel dans les courriers électroniques envoyés. Si aucun fichier n’est spécifié, toutes les erreurs sont classées par défaut. </p> <p>Pour consulter un exemple de ce fichier, voir le fichier <span class="filepath"> Error Categories.txt </span> dans le répertoire Lookups. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> De </td> 
   <td colname="col2"> <p>Adresse qui apparaît dans le paramètre "from" du message électronique. </p> <p>Exemple : <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Espace disque minimum (Mo) </td> 
   <td colname="col2"> Le serveur génère une alerte par courrier électronique lorsque le stockage sur disque disponible dans un répertoire utilisé par le serveur tombe sous cette valeur. La valeur par défaut est 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Délai d'expiration de l'alerte du capteur (min) </td> 
   <td colname="col2"> <p>Le serveur génère une alerte par courrier électronique lorsqu’il n’a reçu aucune donnée d’un <span class="wintitle"> capteur configuré et précédemment connecté </span> dans cette fenêtre temporelle. La valeur par défaut est 15. </p> <p> <p>Remarque :  Le délai d’expiration des alertes <span class="wintitle"> Sensor </span> ne fonctionne que si une connexion existante à un <span class="wintitle"> capteur </span> est interrompue. Si le service du serveur est arrêté et redémarré et que les <span class="wintitle"> capteurs </span> ne se connectent pas, le serveur ne génère pas d’alertes par courrier électronique. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse du serveur </td> 
   <td colname="col2"> <p>Adresse du serveur SMTP pour le courrier électronique sortant. </p> <p>Exemple : <span class="filepath"> mail.mycompany.com </span></p> <p>Un serveur SMTP est requis pour l’utilisation des fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mot de passe du serveur </td> 
   <td colname="col2"> <p>mot de passe de connexion au serveur SMTP. Ce paramètre est facultatif, sauf si vous devez vous connecter pour envoyer du courrier. </p> <p>Un serveur SMTP est requis pour l’utilisation des fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utilisateur du serveur </td> 
   <td colname="col2"> <p>ID utilisateur/nom de connexion au serveur SMTP. Ce paramètre est facultatif, sauf si vous devez vous connecter pour envoyer du courrier. </p> <p>Un serveur SMTP est requis pour l’utilisation des fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Délai de ralentissement (secondes) </td> 
   <td colname="col2"> nombre minimum de secondes qui doit s’écouler entre deux erreurs dans cette catégorie pour qu’un courrier électronique soit envoyé. La valeur 0 envoie immédiatement le courrier électronique. </td> 
  </tr> 
 </tbody> 
</table>

