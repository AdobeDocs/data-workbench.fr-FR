---
description: Instructions de configuration des alertes administratives pour Insight Server, Répéteur ou Transform.
title: Paramètres de configuration des alertes administratives
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
exl-id: c75e442e-33e6-4fc8-8368-29482f09e1cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# Paramètres de configuration des alertes administratives{#administrative-alerts-configuration-settings}

Instructions de configuration des alertes administratives pour Insight Server, Répéteur ou Transform.

Renseignez les paramètres du fichier suivant :

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
   <td colname="col1"> Catégories d’erreurs </td> 
   <td colname="col2"> Permet de classer les erreurs en fonction du fichier de catégorisation des erreurs. Chaque catégorie d’erreur peut avoir son propre ensemble de destinataires et son propre délai de ralentissement. Par exemple, vous pouvez créer une catégorie Critique avec un délai de ralentissement de 0, de sorte que chaque erreur critique soit immédiatement envoyée par courrier électronique aux destinataires spécifiés dans la liste Destinataires. Les erreurs qui ne correspondent pas à une sous-chaîne dans le fichier de catégorisation des erreurs sont attribuées à la catégorie Par défaut. Pour ajouter une nouvelle catégorie, cliquez avec le bouton droit sur un nombre et cliquez sur <span class="uicontrol"> Ajouter </span> &gt; <span class="uicontrol"> Catégorie d’erreur </span>. Vous pouvez également les copier ou les supprimer à l’aide de l’action de clic droit. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier de classification d’erreur </td> 
   <td colname="col2"> <p>Nom du fichier que vous souhaitez utiliser pour classer chaque alerte. Vous créez ce fichier à l’aide du Bloc-notes. Ce fichier doit comporter trois colonnes par ligne, séparées par des onglets. La première colonne est une chaîne à associer en erreur. Un signe ^ correspond au début et un $ correspond à la fin de la chaîne ; tous les autres caractères correspondent littéralement. La deuxième colonne est une catégorie pour les erreurs qui correspondent, qui se trouve dans les catégories d’erreurs. Le troisième est un autre message, qui est ajouté en préfixe au message d’erreur réel dans les emails envoyés. Si aucun fichier n’est spécifié, toutes les erreurs sont classées comme valeur par défaut. </p> <p>Pour voir un exemple de ce fichier, consultez le fichier <span class="filepath"> Error Categories.txt </span> dans le répertoire Lookups. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> De </td> 
   <td colname="col2"> <p>Adresse qui apparaît dans le paramètre "from" du message électronique. </p> <p>Exemple : <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Espace disque minimal (Mo) </td> 
   <td colname="col2"> Le serveur génère une alerte par email lorsque l’espace de stockage sur disque disponible dans un répertoire utilisé par le serveur tombe sous cette valeur. La valeur par défaut est 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Délai d’expiration de l’alerte du capteur (min) </td> 
   <td colname="col2"> <p>Le serveur génère une alerte par email lorsqu’il n’a reçu aucune donnée d’un <span class="wintitle"> Capteur </span> configuré et précédemment connecté dans cette fenêtre temporelle. La valeur par défaut est 15. </p> <p> <p>Remarque :  <span class="wintitle"> Capteur </span> Délai d’attente d’alerte ne fonctionne que si une connexion existante à un <span class="wintitle"> Capteur </span> est supprimée. Si le service du serveur est arrêté et redémarré et que les capteurs <span class="wintitle"> </span> ne se connectent pas, le serveur ne génère pas d’alertes par email. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse du serveur </td> 
   <td colname="col2"> <p>Adresse du serveur SMTP pour les emails sortants. </p> <p>Exemple : <span class="filepath"> mail.mycompany.com </span></p> <p>Un serveur SMTP est requis pour utiliser les fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mot de passe du serveur </td> 
   <td colname="col2"> <p>Mot de passe de connexion au serveur SMTP. Ce paramètre est facultatif, sauf si vous devez vous connecter pour envoyer des courriers électroniques. </p> <p>Un serveur SMTP est requis pour utiliser les fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utilisateur du serveur </td> 
   <td colname="col2"> <p>ID/nom d’utilisateur pour la connexion au serveur SMTP. Ce paramètre est facultatif, sauf si vous devez vous connecter pour envoyer des courriers électroniques. </p> <p>Un serveur SMTP est requis pour utiliser les fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Délai de ralentissement (secondes) </td> 
   <td colname="col2"> Nombre minimum de secondes qui doivent s'écouler entre deux erreurs dans cette catégorie pour qu'un email soit envoyé. La valeur 0 envoie immédiatement l’email. </td> 
  </tr> 
 </tbody> 
</table>
