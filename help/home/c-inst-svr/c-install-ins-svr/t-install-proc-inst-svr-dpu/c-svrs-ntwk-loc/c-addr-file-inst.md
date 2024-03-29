---
description: Le fichier d’adresse installé sur Insight Server contient quatre emplacements réseau prédéfinis.
title: Fichier d’adresse installé sur le serveur Insight
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
exl-id: 12e9bfa2-99ac-4584-b761-38401d1bc3d1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 2%

---

# Fichier d’adresse installé sur le serveur Insight{#the-address-file-installed-on-insight-server}

{{eol}}

Le fichier d’adresse installé sur Insight Server contient quatre emplacements réseau prédéfinis.

La procédure décrite dans la section suivante décrit la configuration de ce fichier.

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

* NetworkLocation 0 est un emplacement réseau vide et sans nom que vous modifiez pour associer le nom commun de votre [!DNL Insight Server] à son adresse IP. Si le serveur comporte plusieurs adresses IP, vous créez des NetworkLocations supplémentaires.
* NetworkLocation 1 correspond à la variable [!DNL Insight] emplacement réseau. Si vous ne définissez pas explicitement le paramètre NetworkLocation , [!DNL Insight] résout les noms courants via cet emplacement réseau.

* NetworkLocation 2 correspond à la variable [!DNL Insight Server] emplacement réseau. When [!DNL Insight Servers] fonctionnent dans une grappe. ils utilisent cet emplacement réseau pour résoudre les noms communs des communications inter-serveurs.

* NetworkLocation 3 correspond à la variable [!DNL Report] Emplacement réseau du serveur. Si vous ne définissez pas explicitement le paramètre NetworkLocation , [!DNL Report] résout les noms courants via cet emplacement réseau.

## Configuration du fichier d’adresse {#section-10caab9854a244e39b09071946f7bd27}

La procédure suivante décrit la configuration du fichier d’adresse pour définir un emplacement réseau (ou des emplacements réseau) pour votre [!DNL Insight Server].

1. Accédez au [!DNL Addresses] dans le répertoire où vous avez installé [!DNL Insight Server] (par exemple, [!DNL C:\Adobe\Server\Addresses)].

1. Recherchez la variable [!DNL server.address] et renommez ce fichier pour refléter le nom commun du serveur. Par exemple, si le nom commun était [!DNL server.mycompany.com], renommez le fichier . [!DNL server.mycompany.com.address].

1. Ouvrez le fichier renommé dans un éditeur de texte tel que Bloc-notes.
1. Modifier NetworkLocation 0 pour spécifier le nom commun et l’adresse IP de [!DNL Insight Server] comme illustré ci-dessous. Si votre serveur comporte plusieurs adresses IP, utilisez NetworkLocation 0 pour spécifier l’adresse IP du serveur sur le réseau local non routable (par exemple, son emplacement sur le réseau interne).

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
   <th colname="col2" class="entry"> Spécifiez les  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>Adresse IP</i> </td> 
   <td colname="col2"> <p>L’adresse IP numérique de la variable <span class="keyword"> Serveur Insight </span> machine. </p> <p>Exemple : 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nom commun </i> </td> 
   <td colname="col2"> <p>Nom commun attribué au certificat numérique pour <span class="keyword"> Serveur Insight </span>. </p> <p>Exemple : <span class="filepath"> server.mycompany.com </span></p> <p>Remarque : Veillez à saisir ce nom tel qu’il apparaît sur le certificat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nom de l’emplacement réseau </i> </td> 
   <td colname="col2"> <p>Nom que vous souhaitez attribuer à la collection de noms communs et d’adresses IP que représente cette NetworkLocation. Le nom doit être unique dans le fichier d’adresse. </p> <p>Exemple : Intranet de l’entreprise </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Si votre [!DNL Insight Server] comporte des adresses IP supplémentaires, créez un emplacement réseau supplémentaire pour chaque adresse. (Pour ce faire, vous pouvez facilement copier l’emplacement réseau que vous avez créé ci-dessus et mettre à jour l’adresse IP dans la copie.)

   Vous pouvez ajouter la nouvelle valeur NetworkLocation à la fin du fichier d’adresse ou l’insérer entre les définitions NetworkLocation existantes. (La position d’un NetworkLocation dans le fichier d’adresse n’est pas significative ; cependant, la variable [!DNL Insight], [!DNL Insight Server], et [!DNL Report] Les emplacements réseau du serveur sont généralement placés à la fin du fichier.)

   Après avoir ajouté les NetworkLocations nécessaires, procédez comme suit pour renuméroter les éléments du fichier :

   1. Mettez à jour le nombre d’éléments pour la structure Emplacements afin qu’il corresponde au nombre total de définitions NetworkLocation dans le fichier. Par exemple, si votre fichier contient quatre définitions NetworkLocation, la ligne Emplacements se présente comme suit :

      ```
      Locations = vector: 4 items
      ```

   1. Mettez à jour les numéros des éléments NetworkLocation afin que NetworkLocations soit numéroté consécutivement (à partir de 0).
   Exemple de fichier d’adresse qui définit une [!DNL Insight Server] avec deux adresses IP, reportez-vous à l’exemple de cette section.

1. Dans le [!DNL Insight] et [!DNL Report] Emplacement réseau du serveur, modifiez le paramètre parent comme illustré ci-dessous pour spécifier le nom de l’emplacement réseau qui [!DNL Insight] et [!DNL Report] utilisent comme emplacements réseau par défaut. (Pour un exemple de l’aspect du paramètre parent lors de sa configuration, reportez-vous à l’exemple de cette section.)

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

   Si votre [!DNL Insight Server] possède une seule adresse IP et, par conséquent, n’a qu’un seul NetworkLocation, pointez le paramètre Parent vers ce NetworkLocation. Si votre [!DNL Insight Server] comporte plusieurs adresses IP, pointez le paramètre Parent vers NetworkLocation qui définit l’adresse à laquelle votre [!DNL Insight] et [!DNL Report] les clients se connectent le plus souvent.

1. Dans le [!DNL Insight Server] emplacement réseau, modifiez le paramètre Parent comme illustré ci-dessous pour pointer vers NetworkLocation que le serveur utilise pour résoudre les noms communs d’autres [!DNL Insight Servers] lorsqu’il fonctionne dans une grappe. (Bien que cet emplacement réseau ne soit pas utilisé, sauf si une variable [!DNL Insight Server] fonctionne dans une grappe. Il est recommandé, même dans une configuration de serveur unique, de pointer le paramètre Parent vers un emplacement réseau qui identifie l’adresse IP interne du serveur.)

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

L’exemple suivant illustre un fichier d’adresse complété. Ce fichier définit cinq emplacements réseau.

* Les éléments NetworkLocation 0 et 1 définissent les emplacements réseau nommés &quot;MyCorporateIntranet&quot; et &quot;Internet&quot;. Ces emplacements réseau définissent deux adresses IP différentes pour un serveur nommé [!DNL VS01.myCompany.com].
* L’élément NetworkLocation 2 correspond à la valeur [!DNL Insight] emplacement réseau. Il s’agit de l’emplacement réseau par défaut utilisé par [!DNL Insight]. Dans cet exemple, la variable [!DNL Insight] L’emplacement réseau hérite de ses Définitions d’adresse à partir de l’emplacement réseau &quot;Internet&quot;.

* L’élément NetworkLocation 3 correspond à la valeur [!DNL Insight Server] emplacement réseau. Il s’agit de l’emplacement réseau par défaut. [!DNL Insight Server] utilise lorsqu’il communique avec d’autres serveurs d’une grappe. Dans cet exemple, la variable [!DNL Insight Server] L’emplacement réseau hérite de ses Définitions d’adresse de l’&quot;Intranet de l’entreprise&quot; NetworkLocation.

* L’élément NetworkLocation 4 correspond à la valeur [!DNL Report] Emplacement réseau du serveur. Il s’agit de l’emplacement réseau par défaut utilisé par [!DNL Report]. Dans cet exemple, la variable [!DNL Report] L’emplacement réseau du serveur hérite de ses Définitions d’adresse de NetworkLocation &quot;Internet&quot;.

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
