---
description: Définissez les paramètres du fichier Insight.cfg pour spécifier la connexion réseau et les paramètres de configuration du Data Workbench.
title: Paramètres de configuration
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
exl-id: c92fc79f-452d-4839-840a-a3ea9e8754c4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 2%

---

# Paramètres de configuration{#configuration-parameters}

Définissez les paramètres du fichier Insight.cfg pour spécifier la connexion réseau et les paramètres de configuration du Data Workbench.

L&#39;exemple suivant ne contient que les paramètres inclus par défaut dans le fichier [!DNL Insight.cfg].

**Nouvelle vue de mise en page**

![](assets/config_tree_new_layout.png)

**Vue de mise en page d’origine**

![](assets/cfg_Workstation_AddServer.png)

Certains des paramètres disponibles dans le nouveau fichier [!DNL Insight.cfg] peuvent ne pas être disponibles dans votre version du fichier [!DNL Insight.cfg]. Si l&#39;un de ces paramètres est nécessaire, vous devez l&#39;ajouter au fichier [!DNL Insight.cfg] en utilisant [!DNL Add Custom Key], en cliquant avec le bouton droit sur un paramètre, puis en spécifiant le nom et le type. Vous pouvez également ajouter des paramètres en ouvrant le fichier [!DNL .cfg] (situé dans le répertoire d’installation du Data Workbench) à l’aide d’un éditeur de texte.

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

Le tableau suivant décrit les paramètres de fichier [!DNL Insight.cfg] disponibles par ordre alphabétique.

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
   <td colname="col2"> <p>Nom d’hôte ou adresse IP numérique de l’ordinateur du serveur Data Workbench. </p> <p>Exemple : <span class="filepath"> vsServer.mycompany.com ou 192.168.1.90</span> </p> <p>Si <span class="wintitle"> Address</span> n'est pas spécifié, <span class="keyword"> le client</span> utilise le nom commun spécifié dans le paramètre Nom commun du serveur SSL lorsque l'option Utiliser le fichier d'adresse est définie sur false. </p> <p> <p>Remarque : Si le paramètre Utiliser le fichier d'adresse est défini sur true, le texte saisi dans le paramètre Address peut être supprimé après l'ouverture du premier profil sur <span class="keyword"> le client</span>. Ensuite, le paramètre Paramètre d’emplacement réseau détermine quelles adresses du fichier d’adresse de la grappe sont utilisées pour la connexion au serveur maître. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Jeu de couleurs </p> </td> 
   <td colname="col2"> <p>Spécifie la couleur d'arrière-plan de l'application cliente <span class="keyword"> </span>. Les options sont les suivantes : </p> <p>0 = noir </p> <p>1 = blanc </p> <p>2 = monochrome </p> <p>La valeur par défaut est 0, noir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Niveau en ligne par défaut </p> </td> 
   <td colname="col2"> <p>Facultatif. Permet de faire fonctionner votre instance de Data Workbench par défaut en tant que diffusion en continu, hors ligne ou en ligne à chaque ouverture. Les options disponibles sont Diffusion en flux continu, En ligne ou Hors ligne. La configuration par défaut du Data Workbench consiste à travailler hors connexion. </p> <p> <p>Remarque : Avant de décider de travailler en ligne par défaut, veillez à évaluer les avantages et les conséquences décrits dans <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Travailler hors ligne et en ligne</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Polices </p> </td> 
   <td colname="col2"> <p>Facultatif. Le vecteur répertoriant les polices que <span class="keyword"> le client</span> doit utiliser pour générer des caractères spéciaux Unicode UTF8. Le nombre de polices dans la liste est illimité. </p> <p>La première police doit toujours être Lucida Sans Console. Si ce paramètre n’est pas inclus dans le fichier <span class="filepath"> Insight.cfg</span>, le Data Workbench utilise uniquement la console Lucida Sans pour afficher du texte. </p> <p> Le Data Workbench utilise la première police de la liste pour effectuer le rendu de tous les caractères jusqu’à ce qu’il rencontre un caractère dont il ne peut pas effectuer le rendu. Il utilise la deuxième police de la liste pour effectuer le rendu de ce caractère. Si cette police n’effectue pas le rendu du caractère, le Data Workbench utilise la troisième police de la liste pour le rendre, etc., jusqu’à ce qu’elle atteigne la fin de la liste de police. Si la police correcte n’est pas répertoriée dans le vecteur, le Data Workbench affiche la valeur hexadécimale du caractère. </p> <p> <p>Remarque :  Ne modifiez pas ce paramètre lorsque le Data Workbench est en cours d’exécution. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> Paramètre Gamma pour l’affichage du Data Workbench. La valeur par défaut est 1.6. Adobe ne recommande pas de modifier cette valeur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Licence </p> </td> 
   <td colname="col2"> <p>Facultatif. Vous devez modifier les paramètres du vecteur de licence uniquement si vous contactez le serveur de licences d’Adobe par l’intermédiaire d’un serveur proxy. </p> <p>Identificateur de section pour les paramètres qui permettent à votre <span class="keyword"> client</span> de contacter le serveur de licence d'Adobe par l'intermédiaire d'un serveur proxy. Développez le noeud Licensing et définissez les paramètres suivants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse du proxy </p> </td> 
   <td colname="col2"> <p>Facultatif. adresse du serveur proxy que <span class="keyword"> client</span> doit utiliser pour accéder au serveur de licences d'Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Port proxy </p> </td> 
   <td colname="col2"> <p>Facultatif. Port du serveur proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom d’utilisateur du proxy </p> </td> 
   <td colname="col2"> <p>Facultatif. Nom d’utilisateur du serveur proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mot de passe du proxy </p> </td> 
   <td colname="col2"> <p>Facultatif. Mot de passe associé au nom d'utilisateur du proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Taille maximale de l’échantillon (Mo) </p> </td> 
   <td colname="col2"> <p>Spécifie la taille maximale autorisée dans le cache de données utilisé par <span class="keyword"> le client</span> s'exécutant sur un seul ordinateur. </p> <p>Bien que le paramètre Sample Bytes du fichier <span class="filepath"> Server.cfg</span> spécifie la taille du cache de données pour tous les clients <span class="keyword"> </span> se connectant à un serveur Data Workbench (250e6 octets par défaut), le paramètre Maximum Sample Size permet de limiter davantage la taille du cache de données pour un ordinateur particulier. Cela s'avère utile lorsque le client est installé sur un ordinateur avec un enregistrement ou une puissance de calcul limités. </p> <p> <p>Remarque : Ce paramètre limite la taille d’un échantillon de données local interrogé localement par le programme client. En revanche, le fichier <span class="filepath"> cache.db</span> contient des données pour chaque profil auquel le client se connecte, ainsi que les noms et dimensions des éléments. Ces noms d’élément et dimensions dans les fichiers <span class="filepath"> cache.db</span> sont requis pour exécuter des requêtes locales. Par conséquent, il n’existe aucun moyen de limiter sa taille autre que la réduction du nombre d’éléments dans l’ensemble de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom </p> </td> 
   <td colname="col2">Facultatif. Nom utilisé par <span class="keyword"> le client</span> pour identifier le serveur <span class="keyword"> </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Emplacement réseau </p> </td> 
   <td colname="col2"> <p>Facultatif. Emplacement réseau utilisé par <span class="keyword"> client</span> pour résoudre le nom commun du serveur Data Workbench en une adresse IP. Les emplacements réseau disponibles sont définis dans le fichier d'adresse du serveur. Pour plus d'informations, consultez le <i>Guide d'installation et d'administration des produits serveur</i>. </p> <p>Si vous ne spécifiez pas d’emplacement réseau, <span class="keyword"> client</span> résout les noms courants à l’aide de l’emplacement réseau par défaut, "Insight". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Port </p> </td> 
   <td colname="col2"> <p>port auquel <span class="keyword"> le client</span> envoie des requêtes. Ce numéro de port doit correspondre au port sur lequel le serveur Data Workbench écoute les requêtes. Il s'agit généralement de 443 pour les connexions sécurisées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse du proxy </p> </td> 
   <td colname="col2"> <p>Si un serveur proxy est nécessaire pour se connecter aux ordinateurs de votre serveur Data Workbench, vous devez au moins renseigner ce paramètre et le paramètre de port proxy. Vous pouvez éventuellement compléter les paramètres Nom d'utilisateur du proxy et Mot de passe de l'utilisateur du proxy. </p> <p>adresse du serveur proxy que <span class="keyword"> le client</span> doit utiliser pour accéder au serveur Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mot de passe du proxy </p> </td> 
   <td colname="col2"> <p>Facultatif. Mot de passe du serveur proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Port proxy </p> </td> 
   <td colname="col2"> <p>Port du serveur proxy. La valeur par défaut est 8080. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom d’utilisateur du proxy </p> </td> 
   <td colname="col2"> <p>Facultatif. Nom d’utilisateur du serveur proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recherche </p> </td> 
   <td colname="col2"> <p>Dans le <span class="filepath"> fichier Insight.cfg</span> (ou tout fichier <span class="filepath"> .cfg</span>), vous pouvez effectuer des recherches par nom de clé, type de clé ou valeur pour localiser rapidement une entrée, afin de ne pas avoir à faire défiler des fichiers volumineux et étendus pour obtenir des informations imbriquées. Vous pouvez localiser les noms de dimension, les noms de serveur, etc. </p> <p>Entrez une expression de recherche dans ce champ pour localiser les données. La couleur du champ change en fonction de la réussite d’une correspondance. Les correspondances sont mises en surbrillance et les non-correspondances sont grisées. S’il n’y a aucune correspondance, l’arrière-plan du champ de recherche devient rouge. Lorsque vous appuyez sur Entrée, l’arborescence de configuration s’étend à tous les endroits où il y a une correspondance et s’effondre là où il n’y a pas de correspondance. </p> <p>Vous pouvez également utiliser des expressions régulières dans le champ <span class="wintitle"> Rechercher</span>. Par exemple, vous pouvez utiliser re : <span class="filepath"> *zip.*</span> pour toute entrée contenant le mot "zip". </p> <p>Pour effacer une recherche, appuyez sur <span class="uicontrol"> Echap</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs </p> </td> 
   <td colname="col2"> <p>En-tête vectoriel pour les connexions <span class="keyword"> client</span> à <span class="keyword"> serveur</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Certificat client SSL </p> </td> 
   <td colname="col2"> <p>Facultatif, sauf si vous disposez de plusieurs certificats. Nom du fichier contenant le certificat numérique pour cette copie de Data Workbench. Il s’agit du fichier que vous avez téléchargé lors du téléchargement et de l’installation du certificat numérique. </p> <p>Exemple : <span class="filepath"> Samantha Smith.pem</span> </p> <p>Si vous laissez ce paramètre vide, <span class="keyword"> le client</span> utilise le certificat existant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom commun du serveur SSL </p> </td> 
   <td colname="col2"> <p>Nom commun du serveur de Data Workbench (tel qu’il est affecté sur son certificat numérique). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Icônes de la barre d’outils </p> </td> 
   <td colname="col2"> <p>False désactive les icônes de l'interface utilisateur du poste de travail et affiche le texte dans la barre d'outils. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utiliser le fichier d'adresse </p> </td> 
   <td colname="col2"> <p>Indique si des paramètres du fichier d’adresse remplacent le paramètre Address. Les options sont true ou false. Si ce paramètre est défini sur true, les paramètres du fichier d’adresse, s’ils sont présents, remplacent le paramètre Address. La valeur par défaut est true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utiliser SSL </p> </td> 
   <td colname="col2">Indique si SSL est utilisé pour la communication sécurisée entre le serveur Data Workbench et <span class="keyword"> le client</span>. Les options sont true ou false. La valeur par défaut est true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Afficher tout </p> </td> 
   <td colname="col2"> <p>Facultatif. Permet d’afficher temporairement toutes les mesures, dimensions et filtres qui ont été masqués à l’aide de l’une des fonctionnalités suivantes : 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A">[Exclusif] dans les fichiers <span class="filepath"> order.txt</span> </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306">Masquer l’option dans les fichiers <span class="filepath"> order.txt</span> </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8">Afficher le paramètre dans les fichiers <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span> et <span class="filepath"> .filter</span>. </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC">Paramètre masqué dans le fichier <span class="filepath"> Transformation.cfg</span>. </li> 
     </ul> </p> <p>Pour plus d'informations sur ces méthodes, voir <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> Masquer un élément de menu</a>. </p> <p>Les options sont true ou false. Le paramètre par défaut est false. Remplacez ce paramètre par true pour afficher temporairement les mesures, dimensions et filtres masqués. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Déverrouiller </p> </td> 
   <td colname="col2"> <p>Facultatif. Indique si vous êtes autorisé à déverrouiller les espaces de travail verrouillés. Les options sont true et false. True vous permet de déverrouiller tout espace de travail verrouillé, contrairement à false. La valeur par défaut est false. Pour plus d’informations sur les espaces de travail verrouillés, voir <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> Déverrouillage d’un espace de travail</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mettre à jour le logiciel </p> </td> 
   <td colname="col2"> <p>Facultatif. Indique si le <span class="keyword"> logiciel client </span>doit être mis à jour par le serveur Data Workbench. Les options sont true ou false. La valeur par défaut est true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dossier utilisateur </p> </td> 
   <td colname="col2"> <p>Facultatif. Indique le nom et l’emplacement du dossier qui contient les copies locales de tous les espaces de travail, mesures, dimensions ou fichiers de configuration pour chaque profil. Le paramètre par défaut est Utilisateur\\, qui spécifie le dossier Utilisateur dans le répertoire d'installation du Data Workbench. </p> <p>La modification de ce paramètre est utile lorsque deux utilisateurs partagent le même ordinateur. Pour accueillir les deux utilisateurs, vous pouvez spécifier un dossier partagé auquel les deux utilisateurs ont accès. </p> </td> 
  </tr> 
 </tbody> 
</table>
