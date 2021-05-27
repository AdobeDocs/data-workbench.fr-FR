---
description: Définissez les paramètres du fichier Insight.cfg pour spécifier vos paramètres de configuration de Data Workbench et de connexion réseau.
title: Paramètres de configuration
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
exl-id: c92fc79f-452d-4839-840a-a3ea9e8754c4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 2%

---

# Paramètres de configuration{#configuration-parameters}

Définissez les paramètres du fichier Insight.cfg pour spécifier vos paramètres de configuration de Data Workbench et de connexion réseau.

L&#39;exemple suivant ne contient que les paramètres inclus par défaut dans le fichier [!DNL Insight.cfg].

**Nouvelle disposition**

![](assets/config_tree_new_layout.png)

**Vue Disposition d’origine**

![](assets/cfg_Workstation_AddServer.png)

Certains des paramètres disponibles dans le nouveau fichier [!DNL Insight.cfg] peuvent ne pas être disponibles dans votre version du fichier [!DNL Insight.cfg]. Si l’un de ces paramètres est nécessaire, vous devez l’ajouter au fichier [!DNL Insight.cfg] en utilisant [!DNL Add Custom Key], en cliquant avec le bouton droit sur un paramètre, puis en spécifiant le nom et le type. Vous pouvez également ajouter des paramètres en ouvrant le fichier [!DNL .cfg] (situé dans le répertoire d’installation du Data Workbench) à l’aide d’un éditeur de texte.

Voici un exemple de tous les paramètres disponibles pour le fichier [!DNL Insight.cfg] que vous pouvez utiliser comme modèle pour ajouter des entrées de paramètre :

```
Licensing = serverInfo:
  Proxy Address = string: 
  Proxy Port = int: 8080
  Proxy User Name = string: 
  Proxy Password = string: 
Servers = vector: 1 items
  0 = serverInfo: 
    Address = string: VS02
    Name = string: Insight Server
    Port = int: 443
    Proxy Address = string: 
    Proxy Password = string: 
    Proxy Port = int: 8080
    Proxy User Name = string: 
    SSL Client Certificate = string: Named User.pem
    SSL Server Common Name = string: VS02
    Use Address File = bool: false
    Use SSL = bool: true
Color Set = int: 0
Default to Online = bool: false
Fonts = vector: 0 items
Gamma = float: 1.6
Maximum Sample Size (MB) = double: 0
Network Location = string: 
Unhide All = bool: false
Unlock = bool: false
Update Software = bool: true
User Folder = string: User\\
Toolbar Icons = bool: false
```

Le tableau suivant fournit des descriptions des paramètres de fichier [!DNL Insight.cfg] disponibles par ordre alphabétique.

<table id="table_4465713A08B649E280A3B4840E829518"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adresse </p> </td> 
   <td colname="col2"> <p>Nom d’hôte ou adresse IP numérique de l’ordinateur de votre serveur de Data Workbench. </p> <p>Exemple : <span class="filepath"> vsServer.mycompany.com ou 192.168.1.90</span> </p> <p>Si <span class="wintitle"> Address</span> n’est pas spécifié, <span class="keyword"> le client</span> utilise le nom commun spécifié dans le paramètre SSL Server Common Name lorsque Use Address File est défini sur false. </p> <p> <p>Remarque : Si le paramètre Utiliser le fichier d’adresse est défini sur true, le texte saisi dans le paramètre Adresse peut être supprimé après l’ouverture du premier profil sur <span class="keyword"> le client</span>. Ensuite, le paramètre du paramètre d’emplacement réseau détermine les adresses du fichier d’adresse de la grappe utilisées pour la connexion au serveur maître. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Jeu de couleurs </p> </td> 
   <td colname="col2"> <p>Spécifie la couleur d’arrière-plan de votre application cliente <span class="keyword"></span>. Les options sont les suivantes : </p> <p>0 = noir </p> <p>1 = blanc </p> <p>2 = monochrome </p> <p>La valeur par défaut est 0, noir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Niveau en ligne par défaut </p> </td> 
   <td colname="col2"> <p>Facultatif. Permet de faire fonctionner par défaut votre instance de Data Workbench comme une diffusion en continu, hors ligne ou en ligne à chaque ouverture. Les options disponibles sont Diffusion en continu, En ligne ou Hors ligne. La configuration par défaut de Data Workbench consiste à travailler hors ligne. </p> <p> <p>Remarque : Avant de décider de travailler en ligne par défaut, veillez à évaluer les avantages et les conséquences décrits dans <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Travail hors ligne et en ligne</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Polices </p> </td> 
   <td colname="col2"> <p>Facultatif. Vecteur répertoriant les polices que <span class="keyword"> le client</span> doit utiliser pour effectuer le rendu de caractères spéciaux Unicode UTF8. Le nombre de polices dans la liste est illimité. </p> <p>La première police doit toujours être Lucida Sans Console. Si ce paramètre n’est pas inclus dans le fichier <span class="filepath"> Insight.cfg</span> , Data Workbench utilise uniquement la console Lucida Sans pour afficher du texte. </p> <p> Data Workbench utilise la première police de la liste pour effectuer le rendu de tous les caractères jusqu’à ce qu’il rencontre un caractère dont il ne peut pas effectuer le rendu. Elle utilise la deuxième police de la liste pour effectuer le rendu de ce caractère. Si cette police n’effectue pas le rendu du caractère, Data Workbench utilise la troisième police de la liste pour effectuer le rendu de ce caractère, et ainsi de suite, jusqu’à ce qu’elle atteigne la fin de la liste des polices. Si la police correcte n’est pas répertoriée dans le vecteur, Data Workbench affiche la valeur hexadécimale du caractère. </p> <p> <p>Remarque :  Ne modifiez pas ce paramètre pendant l’exécution de Data Workbench. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> Paramètre Gamma pour l’affichage du Data Workbench. La valeur par défaut est 1.6. Adobe ne recommande pas de modifier cette valeur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Licences </p> </td> 
   <td colname="col2"> <p>Facultatif. Vous ne devez modifier les paramètres du vecteur de licences que si vous contactez le serveur de licences d’Adobe par l’intermédiaire d’un serveur proxy. </p> <p>Identifiant de section pour les paramètres qui permettent à votre <span class="keyword"> client</span> de contacter le serveur de licences d’Adobe par le biais d’un serveur proxy. Développez le noeud Licences et renseignez les paramètres suivants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse du proxy </p> </td> 
   <td colname="col2"> <p>Facultatif. Adresse du serveur proxy que <span class="keyword"> client</span> doit utiliser pour accéder au serveur de licences d’Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Port du proxy </p> </td> 
   <td colname="col2"> <p>Facultatif. Port du serveur proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom d’utilisateur du proxy </p> </td> 
   <td colname="col2"> <p>Facultatif. Nom d’utilisateur du serveur proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mot de passe du proxy </p> </td> 
   <td colname="col2"> <p>Facultatif. Mot de passe associé au nom d’utilisateur du proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Taille maximale de l’échantillon (Mo) </p> </td> 
   <td colname="col2"> <p>Spécifie la taille maximale autorisée dans le cache de données utilisé par <span class="keyword"> le client</span> s’exécutant sur un seul ordinateur. </p> <p>Bien que le paramètre Sample Bytes dans le fichier <span class="filepath"> Server.cfg</span> spécifie la taille du cache de données pour tous les <span class="keyword"> clients</span> se connectant à un serveur Data Workbench (250e6 octets par défaut), le paramètre Maximum Sample Size permet de limiter davantage la taille du cache de données pour un ordinateur particulier. Cela s’avère utile lorsque le client est installé sur un ordinateur avec un stockage ou une puissance de calcul limités. </p> <p> <p>Remarque : Ce paramètre limite la taille d’un échantillon de données local interrogé localement par le programme client. En revanche, le fichier <span class="filepath"> cache.db</span> contient des données pour chaque profil auquel le client se connecte, ainsi que les noms des éléments et leurs dimensions. Ces noms d’élément et dimensions dans les fichiers <span class="filepath"> cache.db</span> sont nécessaires pour exécuter des requêtes locales. Par conséquent, il n’existe aucun moyen de limiter sa taille autre que de réduire le nombre d’éléments dans le jeu de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom </p> </td> 
   <td colname="col2">Facultatif. Nom utilisé par <span class="keyword"> le client</span> pour identifier le <span class="keyword"> serveur</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Emplacement réseau </p> </td> 
   <td colname="col2"> <p>Facultatif. Emplacement réseau utilisé par <span class="keyword"> client</span> pour résoudre le nom commun du serveur de Data Workbench en adresse IP. Les emplacements réseau disponibles sont définis dans le fichier d’adresse du serveur. Pour plus d’informations, voir le <i>Guide d’installation et d’administration des produits serveur</i>. </p> <p>Si vous ne spécifiez pas d’emplacement réseau, <span class="keyword"> client</span> résout les noms communs à l’aide de l’emplacement réseau par défaut, "Insight". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Port </p> </td> 
   <td colname="col2"> <p>Port auquel <span class="keyword"> le client</span> envoie des requêtes. Ce numéro de port doit correspondre au port sur lequel le serveur du Data Workbench écoute les demandes. Il s’agit généralement de 443 pour les connexions sécurisées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse du proxy </p> </td> 
   <td colname="col2"> <p>Si un serveur proxy est nécessaire pour se connecter aux ordinateurs de votre serveur de Data Workbench, vous devez renseigner au moins ce paramètre et le paramètre de port proxy. Vous pouvez éventuellement renseigner les paramètres Nom d’utilisateur du proxy et Mot de passe de l’utilisateur du proxy. </p> <p>Adresse du serveur proxy que <span class="keyword"> le client</span> doit utiliser pour accéder au serveur du Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mot de passe du proxy </p> </td> 
   <td colname="col2"> <p>Facultatif. Mot de passe du serveur proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Port du proxy </p> </td> 
   <td colname="col2"> <p>Port du serveur proxy. La valeur par défaut est 8080. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom d’utilisateur du proxy </p> </td> 
   <td colname="col2"> <p>Facultatif. Nom d’utilisateur du serveur proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recherche </p> </td> 
   <td colname="col2"> <p>Dans <span class="filepath"> Insight.cfg</span> (ou tout fichier <span class="filepath"> .cfg</span>), vous pouvez rechercher par nom de clé, type de clé ou valeur pour localiser rapidement une entrée, afin de ne pas avoir à faire défiler des fichiers volumineux et étendus pour obtenir des informations imbriquées. Vous pouvez localiser les noms de dimension, les noms de serveur, etc. </p> <p>Saisissez une expression de recherche dans ce champ pour localiser les données. La couleur du champ varie en fonction du succès d’une correspondance. Les correspondances s’affichent en surbrillance et les non-correspondances sont grisées. S’il n’existe aucune correspondance, l’arrière-plan du champ de recherche devient rouge. Lorsque vous appuyez sur Entrée, l’arborescence de configuration s’étend à tous les endroits où il y a une correspondance et s’effondre là où il n’y a pas de correspondance. </p> <p>Vous pouvez également utiliser des expressions régulières dans le champ <span class="wintitle"> Rechercher</span>. Par exemple, vous pouvez utiliser : <span class="filepath"> *zip.*</span> pour toute entrée contenant le mot "zip". </p> <p>Pour effacer une recherche, appuyez sur <span class="uicontrol"> Échappement</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs </p> </td> 
   <td colname="col2"> <p>En-tête vectoriel pour les connexions <span class="keyword"> client</span> à <span class="keyword"> serveur</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Certificat client SSL </p> </td> 
   <td colname="col2"> <p>Facultatif, sauf si vous disposez de plusieurs certificats. Nom du fichier contenant le certificat numérique pour cette copie du Data Workbench. Il s’agit du fichier que vous avez téléchargé dans Téléchargement et installation du certificat numérique. </p> <p>Exemple : <span class="filepath"> Samantha Smith.pem</span> </p> <p>Si vous laissez ce paramètre vide, <span class="keyword"> le client</span> utilise n’importe quel certificat présent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom commun du serveur SSL </p> </td> 
   <td colname="col2"> <p>Nom commun du serveur de Data Workbench (tel qu’il est attribué sur son certificat numérique). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Icônes de la barre d’outils </p> </td> 
   <td colname="col2"> <p>False désactive les icônes de l’interface utilisateur du poste de travail et affiche le texte dans la barre d’outils. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utiliser le fichier d’adresse </p> </td> 
   <td colname="col2"> <p>Indique si les paramètres du fichier d’adresse remplacent le paramètre Adresse . Les options sont true ou false. Si la valeur est définie sur true, les paramètres du fichier d’adresse, le cas échéant, remplacent le paramètre Adresse . La valeur par défaut est true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utiliser SSL </p> </td> 
   <td colname="col2">Indique si SSL est utilisé pour la communication sécurisée entre le serveur du Data Workbench et <span class="keyword"> le client</span>. Les options sont true ou false. La valeur par défaut est true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Afficher tout </p> </td> 
   <td colname="col2"> <p>Facultatif. Permet d’afficher temporairement tous les filtres, dimensions et mesures masqués à l’aide de l’une des fonctionnalités suivantes : 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A">Paramètre [Exclusif] dans les fichiers <span class="filepath"> order.txt</span> </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306">Masquer l’option dans les fichiers <span class="filepath"> order.txt</span> </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8">Afficher le paramètre dans les fichiers <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span> et <span class="filepath"> .filter</span>. </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC">Paramètre masqué dans le fichier <span class="filepath"> Transformation.cfg</span>. </li> 
     </ul> </p> <p>Pour plus d’informations sur ces méthodes, voir <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> Masquer un élément de menu</a>. </p> <p>Les options sont true ou false. Le paramètre par défaut est false. Définissez ce paramètre sur true pour afficher temporairement les mesures, dimensions et filtres masqués. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Déverrouiller </p> </td> 
   <td colname="col2"> <p>Facultatif. Indique si vous êtes autorisé à déverrouiller les espaces de travail verrouillés. Les options sont true et false. True permet de déverrouiller un espace de travail verrouillé, contrairement à false. La valeur par défaut est false. Pour plus d’informations sur les espaces de travail verrouillés, voir <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> Déverrouillage d’un espace de travail</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mettre à jour le logiciel </p> </td> 
   <td colname="col2"> <p>Facultatif. Spécifie si le <span class="keyword"> logiciel client </span>doit être mis à jour par le serveur Data Workbench. Les options sont true ou false. La valeur par défaut est true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dossier utilisateur </p> </td> 
   <td colname="col2"> <p>Facultatif. Indique le nom et l’emplacement du dossier qui contient les copies locales des espaces de travail, des mesures, des dimensions ou des fichiers de configuration pour chaque profil. Le paramètre par défaut est User\\, qui spécifie le dossier User dans le répertoire d’installation du Data Workbench. </p> <p>La modification de ce paramètre est utile lorsque deux utilisateurs partagent le même ordinateur. Pour accueillir les deux utilisateurs, vous pouvez spécifier un dossier partagé auquel les deux utilisateurs ont accès. </p> </td> 
  </tr> 
 </tbody> 
</table>
