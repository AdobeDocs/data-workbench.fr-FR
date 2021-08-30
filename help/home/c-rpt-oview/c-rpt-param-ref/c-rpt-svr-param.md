---
description: Informations sur les paramètres Report Server.cfg.
title: Paramètres Report Server.cfg
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 2%

---

# Paramètres Report Server.cfg{#report-server-cfg-parameters}

Informations sur les paramètres Report Server.cfg.

L’exemple [!DNL Report Server.cfg] illustré dans [Configuration de la connexion à Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) contient uniquement les paramètres inclus dans le fichier [!DNL Report Server.cfg] par défaut.

Si vous contactez le serveur de licences d’Adobe via un serveur proxy, vous devez ajouter le vecteur de licences et ses paramètres à la balise [!DNL Report Server.cfg]. Voici un exemple de ce vecteur et de ses paramètres que vous pouvez utiliser comme modèle pour votre vecteur de licence :

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

Le tableau suivant fournit des descriptions des paramètres de fichier [!DNL Report Server.cfg] :

<table id="table_9DA4A3124A9D444CBB4CBFF6FA279A42"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Extension Excel </td> 
   <td colname="col2"> <p>Les extensions Excel prises en charge sont les suivantes : </p> <p>Extension Excel = chaîne : <span class="filepath"> .xlsx </span> </p> <p>Extension Excel = chaîne : <span class="filepath"> .xls </span> (valeur par défaut) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Polices </td> 
   <td colname="col2"> <p>Facultatif. Vectorisation répertoriant les polices que <span class="keyword"> Report Server </span> doit utiliser pour effectuer le rendu des caractères spéciaux Unicode UTF8. Le nombre de polices dans la liste est illimité. </p> <p>La première police doit toujours être Lucida Sans Console. Si ce paramètre n’est pas inclus dans le fichier <span class="filepath"> Report Server.cfg </span> , <span class="keyword"> Report Server </span> utilise uniquement la console Lucida Sans pour afficher le texte. </p> <p> <span class="keyword"> Le serveur de rapports  </span> utilise la première police de la liste pour effectuer le rendu de tous les caractères jusqu’à ce qu’il rencontre un caractère dont il ne peut pas effectuer le rendu. Il utilise ensuite la deuxième police de la liste pour effectuer le rendu de ce caractère. Si cette police n’effectue pas le rendu du caractère, <span class="keyword"> Report Server </span> utilise la troisième police de la liste pour effectuer le rendu de ce caractère, et ainsi de suite, jusqu’à ce qu’elle atteigne la fin de la liste des polices. Si la police correcte n’est pas répertoriée dans le vecteur, <span class="keyword"> Report Server </span> affiche la valeur hexadécimale du caractère. </p> <p> <p>Remarque :  N’apportez pas de modifications à ce paramètre pendant l’exécution de <span class="keyword"> Report Server </span>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Paramètre Gamma  </span> pour la sortie du  <span class="filepath"> fichier  </span> .png. La valeur par défaut est 1.6. </p> <p> <p>Remarque :  Adobe ne recommande pas de modifier cette valeur. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licences </td> 
   <td colname="col2"> <p>Facultatif. Vous ne devez modifier les paramètres de ce vecteur que si vous contactez le serveur de licences d’Adobe via un serveur proxy. </p> <p>Identifiant de section pour les paramètres que vous définissez pour contacter le serveur de licences d’Adobe via un serveur proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse du proxy </td> 
   <td colname="col2"> Adresse d’un serveur proxy que <span class="keyword"> Report Server </span> doit utiliser pour accéder au serveur de licences d’Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mot de passe du proxy </td> 
   <td colname="col2"> Facultatif. Mot de passe associé au <span class="wintitle"> nom d’utilisateur du proxy </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port du proxy </td> 
   <td colname="col2"> Port du serveur proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom d’utilisateur du proxy </td> 
   <td colname="col2"> Facultatif. Nom d’utilisateur utilisé pour accéder au serveur proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Emplacement réseau </td> 
   <td colname="col2"> Emplacement réseau utilisé par <span class="keyword"> Report Server </span> pour convertir le nom commun du serveur en adresse IP. Les emplacements réseau sont définis dans le fichier d’adresse situé dans le répertoire Adresses de l’ordinateur du serveur Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveurs </td> 
   <td colname="col2"> <p>Identifiant de section pour les paramètres que vous définissez pour configurer les machines de serveur Data Workbench <span class="keyword"> Report Server </span> devant se connecter pour générer des rapports. Cela inclut un nombre indiquant le nombre d’éléments répertoriés dans ce vecteur. </p> <p>Pour chaque serveur, ajoutez une entrée serverInfo et renseignez les paramètres si nécessaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse </td> 
   <td colname="col2"> Adresse IP de l’ordinateur serveur Data Workbench auquel <span class="keyword"> Report Server </span> doit se connecter pour générer des rapports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> Nom utilisé en interne par <span class="keyword"> Report Server </span> pour identifier le serveur Data Workbench. Il s’agit simplement d’un libellé interne, vous pouvez donc utiliser n’importe quel nom. Pour des raisons de cohérence, nous vous suggérons d’utiliser le nom commun répertorié dans le certificat numérique du serveur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Port par lequel <span class="keyword"> Report Server </span> communique avec le serveur Data Workbench. Pour les connexions sécurisées, cette valeur est généralement 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse du proxy </td> 
   <td colname="col2"> Adresse d’un serveur proxy que <span class="keyword"> Report Server </span> doit utiliser pour accéder au serveur Data Workbench. Ce paramètre n’est nécessaire que lorsqu’un serveur proxy est requis pour se connecter aux machines de votre serveur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mot de passe du proxy </td> 
   <td colname="col2"> Mot de passe du serveur proxy. Ce paramètre n’est nécessaire que lorsqu’un serveur proxy est requis pour se connecter aux machines de votre serveur Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port du proxy </td> 
   <td colname="col2"> Port du serveur proxy. La valeur par défaut est 8080. Ce paramètre n’est nécessaire que lorsqu’un serveur proxy est requis pour se connecter aux machines de votre serveur Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom d’utilisateur du proxy </td> 
   <td colname="col2"> Nom d’utilisateur du serveur proxy. Ce paramètre n’est nécessaire que lorsqu’un serveur proxy est requis pour se connecter aux machines de votre serveur Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificat client SSL </td> 
   <td colname="col2"> Nom du fichier de certificat SSL pour la machine <span class="keyword"> Report Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom commun du serveur SSL </td> 
   <td colname="col2"> <span class="wintitle"> Nom commun au serveur  </span> répertorié dans le certificat numérique du serveur Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utiliser SSL </td> 
   <td colname="col2"> Indique si SSL est utilisé pour la communication sécurisée entre le serveur Data Workbench et le <span class="keyword"> serveur de rapports </span>. Les options sont true ou false. La valeur par défaut est true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite de mémoire des résultats (Ko) </td> 
   <td colname="col2"> <p>La quantité de mémoire (en Ko) que vous souhaitez rendre disponible pour les rapports et les alertes. La valeur par défaut est 50000. </p> <p>Lors de l’exécution des rapports, <span class="keyword"> Report Server </span> vérifie d’abord cette valeur, puis vérifie la valeur dans le paramètre Taille maximale des tranches . Par exemple, si vous définissez ce paramètre sur 50 000 et que la taille maximale des tranches est de 50, <span class="keyword"> le serveur de rapports </span> exécute seulement 50 espaces de travail à la fois, même si de l’espace est disponible pour exécuter d’autres espaces de travail. </p> <p> <p>Remarque :  Cette limite ne doit jamais dépasser la valeur définie dans le paramètre Limite de mémoire de requête du serveur Data Workbench et, idéalement, doit être définie un peu plus basse que la <span class="wintitle"> Limite de mémoire de requête </span> afin de fournir une certaine marge de manoeuvre aux autres utilisateurs qui peuvent exécuter des rapports en même temps. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Taille maximale des tranches </td> 
   <td colname="col2"> Nombre maximal d’espaces de travail de rapport que <span class="keyword"> Serveur de rapports </span> peut exécuter simultanément. La valeur par défaut est 50. Pour plus d’informations sur l’utilisation de ce paramètre par <span class="keyword"> Report Server </span>, voir la <span class="wintitle"> Limite de mémoire des résultats (KB) </span> description du paramètre. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mettre à jour le logiciel </td> 
   <td colname="col2"> <p>Indique s’il faut autoriser la mise à jour du </span> logiciel <span class="keyword"> du serveur de rapports par le serveur Data Workbench. Les options sont true ou false. La valeur par défaut est true. </span></p> <p>Voici un exemple de ce paramètre que vous pouvez utiliser comme modèle : </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utilisation du rendu matériel OpenGL </td> 
   <td colname="col2"> <p>Contrôle si <span class="keyword"> le serveur de rapports </span> utilise le rendu matériel (comme la carte graphique de la machine) pour produire la sortie du rapport. Les options sont true ou false. La valeur par défaut est true. </p> <p>Ce paramètre doit être défini sur false uniquement lorsque vous rencontrez des problèmes avec votre carte graphique. Lorsqu’il est défini sur false, <span class="keyword"> Report Server </span> ne tente pas d’utiliser le rendu matériel et utilise le rendu logiciel par défaut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Création de rapports </td> 
   <td colname="col2"> Identifiant de section pour les paramètres que vous définissez pour configurer la création de rapports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalle de message d’achèvement </td> 
   <td colname="col2"> <p>Fréquence (en secondes) à laquelle <span class="keyword"> Report Server </span> imprime les messages d’état d’achèvement lorsque les requêtes sont exécutées pendant la génération du rapport ou de l’alerte. La valeur par défaut est de 120 secondes. </p> <p>Exemple : Les requêtes Workspace sont terminées à 62,145672 %. </p> <p>Les messages d’achèvement sont écrits dans le fichier <span class="filepath"> reportserver.log </span> et sont synchronisés avec le serveur. Ce paramètre contrôle les fichiers <span class="filepath"> status.txt </span> qui sont envoyés en avant et en arrière pour chaque jeu de rapports, de sorte que le pourcentage terminé puisse être affiché avec des miniatures. Les messages sont envoyés chaque fois qu’un jeu de rapports se termine ou que l’intervalle est atteint, selon ce qui se produit en premier. Si vous définissez cette valeur sur une valeur supérieure, le taux d’affichage du rapport généré dans l’interface client par les miniatures n’a aucun effet sur le nombre de messages intermédiaires affichés. Si vous spécifiez une valeur faible, le système peut passer beaucoup de temps à synchroniser les données, car les données sont synchronisées du <span class="keyword"> serveur de rapports </span> vers le profil, entre tous les DPU et tous les clients connectés à chaque fois qu’un message <span class="filepath"> status.txt </span> change. </p> <p>Le système envoie toujours un fichier <span class="filepath"> status.txt </span> à la fin d’un jeu de rapports, quelle que soit la définition de ce paramètre de configuration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profils </td> 
   <td colname="col2"> <p>Nombre indiquant le nombre d’éléments répertoriés dans ce vecteur. Pour chaque profil pour lequel des rapports doivent être créés, ajoutez une entrée <span class="wintitle"> ReportProfile </span> dans le vecteur Profils et renseignez les paramètres Serveur et Profil . </p> <p> <span class="wintitle"> Serveur  </span> : nom que le serveur de  <span class="keyword"> rapports  </span> utilise en interne pour identifier le serveur Data Workbench. Ce nom doit être le nom commun au serveur répertorié dans le certificat SSL du serveur Data Workbench. </p> <p> <span class="wintitle"> Profil  </span> : nom du profil pour lequel des rapports doivent être créés. Ce nom doit correspondre au profil nommé sur l’ordinateur du serveur Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur SMTP pour les erreurs </td> 
   <td colname="col2"> <p>Adresse du serveur SMTP à partir duquel vous souhaitez envoyer des erreurs <span class="wintitle"> Report Server </span> par courrier électronique. </p> <p>Exemple : <span class="filepath"> mail.mycompany.com </span> </p> <p>Un serveur SMTP est requis pour utiliser les fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur SMTP pour le mot de passe des erreurs </td> 
   <td colname="col2"> <p>Mot de passe de connexion au serveur SMTP. Ce paramètre est facultatif, sauf si vous devez vous connecter pour envoyer des courriers électroniques. </p> <p>Un serveur SMTP est requis pour utiliser les fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur SMTP pour les erreurs d’envoi à partir de </td> 
   <td colname="col2"> Adresse électronique à partir de laquelle vous souhaitez envoyer des erreurs <span class="wintitle"> au serveur de rapports </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur SMTP pour les erreurs envoyées à </td> 
   <td colname="col2"> <p>Adresse(s) de courriel à laquelle les alertes sont envoyées. </p> <p>Exemple : <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>Un serveur SMTP est requis pour utiliser les fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server for Erreurs Username </td> 
   <td colname="col2"> <p>Nom d’utilisateur pour la connexion au serveur SMTP. Ce paramètre est facultatif, sauf si vous devez vous connecter pour envoyer des courriers électroniques. </p> <p>Un serveur SMTP est requis pour utiliser les fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalle d’état </td> 
   <td colname="col2"> <p>Fréquence (en secondes) à laquelle <span class="wintitle"> Report Server </span> génère et envoie des informations d’état au serveur Data Workbench pour qu’il les affiche dans <span class="wintitle"> État détaillé </span>. </p> <p>La valeur par défaut est de 120 secondes. Il n’est pas recommandé de définir cette valeur sur une petite valeur, par exemple deux minutes, car l’exécution d’une file d’attente de rapports peut prendre des heures. Dans ce cas, vous pouvez définir entre 600 et 1 200 secondes. </p> <p>Pour plus d’informations sur <span class="wintitle"> État détaillé </span>, consultez le chapitre Interfaces administratives du <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Guide de l’utilisateur d’Insight </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalle de mise à jour </td> 
   <td colname="col2"> <p>Fréquence (en minutes) à laquelle <span class="keyword"> Report Server </span> surveille tous les profils répertoriés dans le vecteur Profils pour détecter de nouveaux rapports et alertes. La valeur par défaut est de 10 minutes. </p> <p>L’heure spécifiée est répartie entre tous les profils répertoriés. Par exemple, si votre intervalle est défini sur 10 minutes et que vous surveillez deux profils, chaque profil est surveillé pendant 5 minutes. Si un profil est surveillé lorsqu’un rapport ou une alerte nouveau ou modifié est enregistré dans le profil, le rapport ou l’alerte est immédiatement disponible pour génération. </p> <p>Si <span class="wintitle"> Intervalle de mise à jour </span> est configuré pour surveiller plusieurs profils, il est important que ce paramètre soit suffisamment élevé pour charger tous les profils dans le temps configuré. Dans les systèmes dont les dimensions sont nombreuses, par exemple, lorsqu’il peut s’écouler plusieurs minutes avant de récupérer la connexion de données initiale avec tous les noms d’éléments, ce paramètre doit être suffisamment long pour que cette synchronisation complète se produise. Sinon, le système génère une erreur de synchronisation de profil. </p> </td> 
  </tr> 
 </tbody> 
</table>
