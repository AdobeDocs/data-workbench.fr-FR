---
description: Informations sur les paramètres Report Server.cfg.
solution: Analytics
title: Paramètres Report Server.cfg
topic: Data workbench
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# Paramètres Report Server.cfg{#report-server-cfg-parameters}

Informations sur les paramètres Report Server.cfg.

L’exemple [!DNL Report Server.cfg] illustré dans [Configuration de la connexion au serveur](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) Insight contient uniquement les paramètres inclus dans le [!DNL Report Server.cfg] fichier par défaut.

Si vous contactez le serveur Adobe License Server par l’intermédiaire d’un serveur proxy, vous devez ajouter le vecteur de gestion de la licence et ses paramètres au serveur [!DNL Report Server.cfg]. Voici un exemple de ce vecteur et de ses paramètres que vous pouvez utiliser comme modèle pour votre vecteur de licence :

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

Le tableau suivant décrit les paramètres du [!DNL Report Server.cfg] fichier :

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
   <td colname="col2"> <p>Facultatif. Vectorisation répertoriant les polices que <span class="keyword"> le serveur de rapports </span> doit utiliser pour générer des caractères spéciaux Unicode UTF8. Le nombre de polices dans la liste est illimité. </p> <p>La première police doit toujours être Lucida Sans Console. Si ce paramètre n’est pas inclus dans le fichier <span class="filepath"> Report Server.cfg </span> , <span class="keyword"> </span> Report Server utilise uniquement la console Lucida Sans pour afficher du texte. </p> <p> <span class="keyword"> Le serveur de rapports </span> utilise la première police de la liste pour effectuer le rendu de tous les caractères jusqu’à ce qu’il rencontre un caractère qu’il ne peut pas rendre. Il utilise ensuite la deuxième police de la liste pour rendre ce caractère. Si cette police n’effectue pas le rendu du caractère, <span class="keyword"> le serveur de rapports </span> utilise la troisième police de la liste pour le rendre, etc., jusqu’à ce qu’elle atteigne la fin de la liste des polices. Si la police correcte n’est pas répertoriée dans le vecteur, <span class="keyword"> le serveur de rapports </span> affiche la valeur hexadécimale du caractère. </p> <p> <p>Remarque :  N’apportez aucune modification à ce paramètre pendant l’exécution du serveur de <span class="keyword"> rapports </span> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Paramètre Gamma </span> pour la sortie du fichier <span class="filepath"> .png </span> . La valeur par défaut est 1.6. </p> <p> <p>Remarque :  Adobe recommande de ne pas modifier cette valeur. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licence </td> 
   <td colname="col2"> <p>Facultatif. Vous devez modifier les paramètres de ce vecteur uniquement si vous contactez le serveur de licences d’Adobe par l’intermédiaire d’un serveur proxy. </p> <p>Identifiant de section pour les paramètres que vous configurez pour contacter le serveur de licences d’Adobe via un serveur proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse du proxy </td> 
   <td colname="col2"> adresse d’un serveur proxy que <span class="keyword"> le serveur de rapports </span> doit utiliser pour accéder au serveur de licences d’Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mot de passe du proxy </td> 
   <td colname="col2"> Facultatif. mot de passe associé au nom d’utilisateur du <span class="wintitle"> proxy </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port du proxy </td> 
   <td colname="col2"> port du serveur proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom d’utilisateur du proxy </td> 
   <td colname="col2"> Facultatif. nom d’utilisateur utilisé pour accéder au serveur proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Emplacement réseau </td> 
   <td colname="col2"> Emplacement réseau utilisé par <span class="keyword"> Report Server </span> pour résoudre le nom commun du serveur en adresse IP. Les emplacements réseau sont définis dans le fichier d’adresse situé dans le répertoire Adresses de l’ordinateur serveur de l’outil de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveurs </td> 
   <td colname="col2"> <p>Identifiant de section pour les paramètres que vous définissez pour configurer les ordinateurs serveur de l’outil de données que <span class="keyword"> le serveur de rapports doit </span> se connecter pour générer des rapports. Cela inclut un nombre indiquant le nombre d’éléments répertoriés dans ce vecteur. </p> <p>Pour chaque serveur, ajoutez une entrée serverInfo et complétez les paramètres si nécessaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse </td> 
   <td colname="col2"> Adresse IP de l’ordinateur serveur de l’outil de données auquel <span class="keyword"> le serveur de rapports </span> doit se connecter pour générer des rapports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> Nom utilisé en interne par <span class="keyword"> Report Server </span> pour identifier le serveur de l’outil de données. Il s'agit simplement d'une étiquette interne, vous pouvez donc utiliser n'importe quel nom que vous voulez. Pour des raisons de cohérence, nous vous suggérons d’utiliser le nom commun tel qu’il figure dans le certificat numérique du serveur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Port par lequel <span class="keyword"> le serveur de rapports </span> communique avec le serveur de l’outil de données. Pour les connexions sécurisées, cette valeur est généralement 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse du proxy </td> 
   <td colname="col2"> adresse d’un serveur proxy que <span class="keyword"> le serveur de rapports </span> doit utiliser pour accéder au serveur de l’outil de données. Ce paramètre n’est nécessaire que lorsqu’un serveur proxy est nécessaire pour se connecter à vos machines serveur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mot de passe du proxy </td> 
   <td colname="col2"> mot de passe du serveur proxy. Ce paramètre n’est nécessaire que lorsqu’un serveur proxy est nécessaire pour se connecter aux ordinateurs de votre serveur de outils de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port du proxy </td> 
   <td colname="col2"> port du serveur proxy. La valeur par défaut est 8080. Ce paramètre n’est nécessaire que lorsqu’un serveur proxy est nécessaire pour se connecter aux ordinateurs de votre serveur de outils de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom d’utilisateur du proxy </td> 
   <td colname="col2"> Nom d’utilisateur du serveur proxy. Ce paramètre n’est nécessaire que lorsqu’un serveur proxy est nécessaire pour se connecter aux ordinateurs de votre serveur de outils de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificat client SSL </td> 
   <td colname="col2"> Nom du fichier de certificat SSL pour l’ <span class="keyword"> ordinateur du serveur de rapports </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom commun du serveur SSL </td> 
   <td colname="col2"> <span class="wintitle"> Nom commun du serveur </span> répertorié dans le certificat numérique du serveur de l’outil de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utiliser SSL </td> 
   <td colname="col2"> Indique si SSL est utilisé pour la communication sécurisée entre le serveur de l’outil de données et <span class="keyword"> le serveur de rapports </span>. Les options sont true ou false. La valeur par défaut est true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite de mémoire des résultats (Ko) </td> 
   <td colname="col2"> <p>Quantité de mémoire (en Ko) que vous souhaitez rendre disponible pour les rapports et les alertes. La valeur par défaut est 50000. </p> <p>Lors de l’exécution des rapports, <span class="keyword"> le serveur de rapports </span> vérifie d’abord cette valeur, puis vérifie la valeur dans le paramètre Taille de tranche maximale. Si, par exemple, vous définissez ce paramètre sur 50 000 et la taille de tranche maximale sur 50, <span class="keyword"> le serveur de rapports </span> exécute uniquement 50 espaces de travail à la fois, même si l’espace est disponible pour exécuter d’autres espaces de travail. </p> <p> <p>Remarque :  Cette limite ne doit jamais dépasser la valeur définie dans le paramètre Limite de mémoire de requête du serveur de l’outil de données et, dans l’idéal, doit être un peu inférieure à la limite de mémoire de <span class="wintitle"> requête </span> afin de fournir une certaine marge de manoeuvre aux autres utilisateurs qui exécutent des rapports en même temps. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Taille maximale de la tranche </td> 
   <td colname="col2"> Nombre maximal d’espaces de travail de rapport que <span class="keyword"> le serveur de rapports </span> peut exécuter simultanément. La valeur par défaut est 50. Pour plus d’informations sur la manière dont <span class="keyword"> Report Server </span> utilise ce paramètre, voir la description du <span class="wintitle"> paramètre Limite de mémoire des </span> résultats (Ko). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mettre à jour le logiciel </td> 
   <td colname="col2"> <p>Indique si le <span class="keyword"> logiciel de ce serveur de </span> rapports doit être mis à jour par le serveur de l’outil de données. Les options sont true ou false. La valeur par défaut est true. </p> <p>Voici un exemple de ce paramètre que vous pouvez utiliser comme modèle : </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utiliser le rendu matériel OpenGL </td> 
   <td colname="col2"> <p>Contrôle si <span class="keyword"> le serveur de rapports </span> utilise le rendu matériel (comme la carte graphique de l’ordinateur) pour générer la sortie du rapport. Les options sont true ou false. La valeur par défaut est true. </p> <p>Ce paramètre ne doit être défini sur false que lorsque vous rencontrez des problèmes avec votre carte graphique. Lorsqu’il est défini sur false, <span class="keyword"> le serveur de rapports </span> ne tente pas d’utiliser le rendu matériel et utilise le rendu logiciel par défaut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Création de rapports </td> 
   <td colname="col2"> Identifiant de section pour les paramètres que vous définissez pour configurer la création de rapports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalle de message d’achèvement </td> 
   <td colname="col2"> <p>Fréquence (en secondes) à laquelle le serveur de <span class="keyword"> rapports </span> imprime les messages d’état d’achèvement lors de l’exécution des requêtes pendant la génération du rapport ou de l’alerte. La valeur par défaut est de 120 secondes. </p> <p>Exemple : Les requêtes Workspace sont terminées à 62,145672 %. </p> <p>Les messages d’achèvement sont écrits dans le fichier <span class="filepath"> reportserver.log </span> et sont synchronisés sur le serveur. Ce paramètre contrôle les fichiers <span class="filepath"> .txt </span> status qui sont envoyés en avant et en arrière pour chaque jeu de rapports, de sorte que le pourcentage terminé puisse être affiché avec des miniatures. Les messages sont envoyés chaque fois qu’un jeu de rapports se termine ou lorsque l’intervalle est atteint, le premier événement survenant. Si vous définissez cette valeur sur une valeur plus élevée, le rapport généré dans l’interface client par les miniatures n’est pas affiché dans le rapport, mais le nombre de messages intermédiaires affichés est affecté. Si vous spécifiez une valeur faible, le système risque de passer beaucoup de temps à synchroniser les données, car les données sont synchronisées du serveur de <span class="keyword"> rapports </span> vers le profil, sur tous les DPU et sur tous les clients connectés chaque fois qu’un message <span class="filepath"> status.txt </span> change. </p> <p>Le système envoie toujours un fichier <span class="filepath"> status.txt </span> à la fin d’un jeu de rapports, quel que soit le paramètre de cette configuration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profils </td> 
   <td colname="col2"> <p>Nombre indiquant le nombre d’éléments répertoriés dans ce vecteur. Pour chaque profil pour lequel des rapports doivent être créés, ajoutez une entrée <span class="wintitle"> Profil de rapport </span> dans le vecteur Profils et complétez les paramètres Serveur et Profil. </p> <p> <span class="wintitle"> Serveur </span> - Nom utilisé par <span class="keyword"> le serveur de rapports </span> en interne pour identifier le serveur de l’outil de données. Ce nom doit être le nom commun du serveur figurant dans le certificat SSL du serveur de l’outil de données. </p> <p> <span class="wintitle"> Profil </span> : nom du profil pour lequel des rapports doivent être créés. Ce nom doit correspondre au profil nommé sur l’ordinateur serveur de l’outil de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur SMTP pour les erreurs </td> 
   <td colname="col2"> <p>adresse du serveur SMTP à partir duquel vous souhaitez envoyer les <span class="wintitle"> erreurs du serveur de </span> rapports par courrier électronique. </p> <p>Exemple : <span class="filepath"> mail.mycompany.com </span> </p> <p>Un serveur SMTP est requis pour l’utilisation des fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur SMTP pour le mot de passe des erreurs </td> 
   <td colname="col2"> <p>mot de passe de connexion au serveur SMTP. Ce paramètre est facultatif, sauf si vous devez vous connecter pour envoyer du courrier. </p> <p>Un serveur SMTP est requis pour l’utilisation des fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur SMTP pour les erreurs d’envoi depuis </td> 
   <td colname="col2"> Adresse électronique à partir de laquelle vous souhaitez envoyer les <span class="wintitle"> erreurs du serveur de </span> rapports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur SMTP pour les erreurs envoyées à </td> 
   <td colname="col2"> <p>adresse(s) électronique(s) à laquelle les alertes sont envoyées. </p> <p>Exemple : <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>Un serveur SMTP est requis pour l’utilisation des fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur SMTP pour les erreurs Nom d’utilisateur </td> 
   <td colname="col2"> <p>Nom d’utilisateur pour la connexion au serveur SMTP. Ce paramètre est facultatif, sauf si vous devez vous connecter pour envoyer du courrier. </p> <p>Un serveur SMTP est requis pour l’utilisation des fonctionnalités décrites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalle de statut </td> 
   <td colname="col2"> <p>Fréquence (en secondes) à laquelle le serveur de <span class="wintitle"> rapports </span> génère et envoie des informations d’état au serveur de l’outil de données pour qu’elles s’affichent dans <span class="wintitle"> l’état détaillé </span>. </p> <p>La valeur par défaut est de 120 secondes. Il n’est pas recommandé de définir cette valeur sur une petite valeur, par exemple deux minutes, car l’exécution d’une file d’attente de rapports peut prendre des heures. Dans ce cas, vous pouvez envisager un paramètre de 600 à 1 200 secondes. </p> <p>Pour plus d’informations sur <span class="wintitle"> le statut détaillé </span>, consultez le chapitre Interfaces d’administration du <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Guide de l’utilisateur d’Insight </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalle de mise à jour </td> 
   <td colname="col2"> <p>Fréquence (en minutes) à laquelle le serveur de <span class="keyword"> rapports </span> analyse tous les profils répertoriés dans le vecteur Profils pour détecter de nouveaux rapports et alertes. La valeur par défaut est de 10 minutes. </p> <p>La durée spécifiée est divisée entre tous les profils répertoriés. Par exemple, si votre intervalle est défini sur 10 minutes et que vous surveillez deux profils, chaque profil est surveillé pendant 5 minutes. Si un profil est surveillé lorsqu’un rapport ou une alerte nouveau ou modifié est enregistré dans le profil, le rapport ou l’alerte est immédiatement disponible pour la génération. </p> <p>Si l’intervalle de <span class="wintitle"> mise à jour </span> est configuré pour surveiller plusieurs profils, il est important que ce paramètre soit suffisamment élevé pour charger tous les profils dans le délai configuré. Dans les systèmes avec de nombreuses dimensions configurées, par exemple, où la récupération de la connexion aux données initiales avec tous les noms d’élément peut prendre plusieurs minutes, ce paramètre doit être suffisamment long pour que cette synchronisation complète se produise. Sinon, le système génère une erreur de synchronisation de profil. </p> </td> 
  </tr> 
 </tbody> 
</table>

