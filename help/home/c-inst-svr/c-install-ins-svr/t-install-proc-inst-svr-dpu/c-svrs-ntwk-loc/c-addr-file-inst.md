---
description: Le fichier d’adresse installé sur Insight Server contient quatre emplacements réseau prédéfinis.
title: Fichier d’adresse installé sur le serveur Insight
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
exl-id: 12e9bfa2-99ac-4584-b761-38401d1bc3d1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 2%

---

# Fichier d’adresse installé sur le serveur Insight{#the-address-file-installed-on-insight-server}

Le fichier d’adresse installé sur Insight Server contient quatre emplacements réseau prédéfinis.

La procédure décrite dans la section suivante décrit comment configurer ce fichier.

```
Locations = vector: 4 items  
  0 = NetworkLocation:  
    Addresses = vector: 1 items 
      0 = AddressDefinition:  
        Address = string:  
        Name = string:  
    Name = string:  
    Parent = string:  
  1 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight 
    Parent = string:  
  2 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight Server 
    Parent = string: 
  3 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Report Server 
    Parent = string:
```

* NetworkLocation 0 est un emplacement réseau vide sans nom que vous modifiez pour associer le nom commun de votre [!DNL Insight Server] à son adresse IP. Si le serveur comporte plusieurs adresses IP, vous créez des NetworkLocations supplémentaires.
* NetworkLocation 1 est l&#39;emplacement réseau [!DNL Insight]. Si vous ne définissez pas explicitement le paramètre NetworkLocation, [!DNL Insight] résout les noms courants via cet emplacement réseau.

* NetworkLocation 2 est l&#39;emplacement réseau [!DNL Insight Server]. Lorsque [!DNL Insight Servers] opère dans un cluster, il utilise cet emplacement réseau pour résoudre les noms courants pour la communication entre serveurs.

* NetworkLocation 3 est l&#39;emplacement réseau du serveur [!DNL Report]. Si vous ne définissez pas explicitement le paramètre NetworkLocation, [!DNL Report] résout les noms courants via cet emplacement réseau.

## Pour configurer le fichier d&#39;adresse {#section-10caab9854a244e39b09071946f7bd27}

La procédure suivante décrit comment configurer le fichier d&#39;adresse pour définir un emplacement réseau (ou des emplacements réseau) pour votre [!DNL Insight Server].

1. Accédez au dossier [!DNL Addresses] dans le répertoire où vous avez installé [!DNL Insight Server] (par exemple, [!DNL C:\Adobe\Server\Addresses)].

1. Localisez le fichier [!DNL server.address] et renommez ce fichier pour refléter le nom commun du serveur. Par exemple, si le nom commun est [!DNL server.mycompany.com], vous renommez le fichier [!DNL server.mycompany.com.address].

1. Ouvrez le fichier renommé dans un éditeur de texte tel que le Bloc-notes.
1. Modifiez NetworkLocation 0 pour spécifier le nom commun et l&#39;adresse IP de [!DNL Insight Server] comme indiqué ci-dessous. Si votre serveur comporte plusieurs adresses IP, utilisez NetworkLocation 0 pour spécifier l’adresse IP du serveur sur le réseau local non routable (par exemple, son emplacement sur le réseau interne).

   ```
   Locations = vector: 3 items 
   0 = NetworkLocation: 
     Addresses = vector: 1 items 
       0 = AddressDefinition: 
         Address = string: IPAddress 
         Name = string: CommonName 
     Name = string: NetworkLocationName 
     Parent = string: 
   ```

<table id="table_02C2A1630CCD40C4A51B314C3CB683F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour cette valeur... </th> 
   <th colname="col2" class="entry"> Spécifiez les </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>Adresse IP</i> </td> 
   <td colname="col2"> <p>Adresse IP numérique de l’ordinateur <span class="keyword"> Insight Server </span>. </p> <p>Exemple : 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nom commun  </i> </td> 
   <td colname="col2"> <p>Nom commun attribué au certificat numérique pour <span class="keyword"> Insight Server </span>. </p> <p>Exemple : <span class="filepath"> server.mycompany.com </span></p> <p>Remarque : Veillez à saisir ce nom exactement tel qu’il apparaît sur le certificat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nom de l'emplacement réseau  </i> </td> 
   <td colname="col2"> <p>Nom que vous souhaitez attribuer à la collection de noms communs et d'adresses IP que représente cette NetworkLocation. Le nom doit être unique dans le fichier d'adresse. </p> <p>Exemple : Intranet de l'entreprise </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Si votre [!DNL Insight Server] comporte des adresses IP supplémentaires, créez un NetworkLocation supplémentaire pour chaque adresse. (Pour ce faire, il est facile de faire une copie du NetworkLocation que vous avez créé ci-dessus et de mettre à jour l&#39;adresse IP dans la copie.)

   Vous pouvez ajouter le nouvel objet NetworkLocation à la fin du fichier d&#39;adresse ou l&#39;insérer entre les définitions NetworkLocation existantes. (La position d&#39;un NetworkLocation dans le fichier d&#39;adresse n&#39;est pas significative ; toutefois, les [!DNL Insight], [!DNL Insight Server] et [!DNL Report] Server NetworkLocations sont généralement placés à la fin du fichier.)

   Après avoir ajouté les NetworkLocations nécessaires, procédez comme suit pour renuméroter les éléments du fichier :

   1. Mettez à jour le nombre d&#39;articles pour la structure Emplacements afin qu&#39;il corresponde au nombre total de définitions NetworkLocation dans le fichier. Par exemple, si votre fichier contient quatre définitions NetworkLocation, la ligne Locations se présente comme suit :

      ```
      Locations = vector: 4 items
      ```

   1. Mettez à jour les numéros d&#39;élément NetworkLocation de sorte que NetworkLocations soit numéroté consécutivement (à partir de 0).
   Pour un exemple de fichier d&#39;adresse qui définit un [!DNL Insight Server] avec deux adresses IP, reportez-vous à l&#39;exemple de cette section.

1. Dans les emplacements réseau de serveur [!DNL Insight] et [!DNL Report], modifiez le paramètre Parent comme illustré ci-dessous pour spécifier le nom de NetworkLocation que [!DNL Insight] et [!DNL Report] utilisent comme emplacements réseau par défaut. (Pour un exemple de l’aspect du paramètre Parent lorsqu’il est configuré, reportez-vous à l’exemple de cette section.)

   ```
   1 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight 
     Parent = string: ClientDefaultNetworkLocation 
   
   3 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Report Server 
     Parent = string: ClientDefaultNetworkLocation
   ```

   Si votre [!DNL Insight Server] a une seule adresse IP et, par conséquent, n&#39;a qu&#39;un seul NetworkLocation, pointez le paramètre Parent vers ce NetworkLocation. Si votre [!DNL Insight Server] comporte plusieurs adresses IP, pointez le paramètre Parent sur NetworkLocation qui définit l&#39;adresse à laquelle vos clients [!DNL Insight] et [!DNL Report] se connectent le plus fréquemment.

1. Dans l&#39;emplacement réseau [!DNL Insight Server], modifiez le paramètre Parent comme illustré ci-dessous pour pointer vers NetworkLocation que le serveur utilise pour résoudre les noms communs d&#39;autres [!DNL Insight Servers] lorsqu&#39;il opère dans un cluster. (Bien que cet emplacement réseau ne soit pas utilisé à moins qu&#39;un [!DNL Insight Server] ne fonctionne dans un cluster, il est recommandé, même dans une configuration de serveur unique, de pointer le paramètre Parent vers un emplacement réseau qui identifie l&#39;adresse IP interne du serveur.)

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

L&#39;exemple suivant montre un fichier d&#39;adresse terminé. Ce fichier définit cinq emplacements réseau.

* Les éléments NetworkLocation 0 et 1 définissent les emplacements réseau nommés &quot;MyCorporateIntranet&quot; et &quot;Internet&quot;. Ces emplacements réseau définissent deux adresses IP différentes pour un serveur nommé [!DNL VS01.myCompany.com].
* L&#39;élément NetworkLocation 2 correspond à l&#39;emplacement réseau [!DNL Insight]. Il s&#39;agit de l&#39;emplacement réseau par défaut utilisé par [!DNL Insight]. Dans cet exemple, l&#39;emplacement réseau [!DNL Insight] hérite de ses AddressDefinitions de NetworkLocation &quot;Internet&quot;.

* L&#39;élément NetworkLocation 3 correspond à l&#39;emplacement réseau [!DNL Insight Server]. Il s&#39;agit de l&#39;emplacement réseau par défaut utilisé par [!DNL Insight Server] lorsqu&#39;il communique avec d&#39;autres serveurs d&#39;une grappe. Dans cet exemple, l&#39;emplacement réseau [!DNL Insight Server] hérite de la valeur AddressDefinitions de &quot;MyCorporate Intranet&quot; NetworkLocation.

* L&#39;élément NetworkLocation 4 correspond à l&#39;emplacement réseau du serveur [!DNL Report]. Il s&#39;agit de l&#39;emplacement réseau par défaut utilisé par [!DNL Report]. Dans cet exemple, l&#39;emplacement réseau du serveur [!DNL Report] hérite de ses AddressDefinitions de NetworkLocation &quot;Internet&quot;.

   ```
   Locations = vector: 5 items 
     0 = NetworkLocation:  
       Addresses = vector: 1 items 
         0 = AddressDefinition:  
           Address = string: 10.2.1.70 
           Name = string: VS01.myCompany.com 
       Name = string: MyCorporateIntranet 
       Parent = string:  
   
     1 = NetworkLocation:  
       Addresses = vector: 1 items 
         0 = AddressDefinition:  
           Address = string: 65.196.125.167 
           Name = string: VS01.myCompany.com 
       Name = string: Internet 
       Parent = string: 
   
     2 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight 
       Parent = string: Internet 
   
     3 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight Server 
       Parent = string: MyCorporateIntranet 
   
     4 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Report Server 
       Parent = string: Internet
   ```
