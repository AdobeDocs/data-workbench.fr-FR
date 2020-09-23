---
description: Si les clients peuvent accéder à un serveur Insight via plusieurs réseaux (par exemple, via l’intranet de l’entreprise et Internet), le fichier d’adresse doit définir un emplacement réseau distinct pour chacune des adresses IP du serveur.
solution: Analytics
title: Plusieurs adresses IP pour un serveur Insight
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---


# Plusieurs adresses IP pour un serveur Insight{#multiple-ip-addresses-for-an-insight-server}

Si les clients peuvent accéder à un serveur Insight via plusieurs réseaux (par exemple, via l’intranet de l’entreprise et Internet), le fichier d’adresse doit définir un emplacement réseau distinct pour chacune des adresses IP du serveur.

Par exemple, si le serveur [!DNL VS01.myCompany.com] a une adresse IP de 10.2.1.70 sur un réseau interne et une adresse IP de 65.196.125.167 sur Internet, le fichier d&#39;adresse doit inclure un emplacement réseau pour chacune des adresses, comme illustré dans l&#39;exemple ci-dessous :

```
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
```

Lorsque les utilisateurs se connectent à un [!DNL Insight Server]serveur, ils utilisent le paramètre NetworkLocation (dans l’interface utilisateur cliente) pour spécifier l’emplacement réseau par lequel ils souhaitent que le nom commun du serveur soit résolu. Par exemple, à partir d&#39;un fichier d&#39;adresse avec les deux NetworkLocations illustrées ci-dessus, un utilisateur définirait le paramètre NetworkLocation sur &quot;MyCorporate Intranet&quot; pour se connecter à [!DNL Insight Server] travers le réseau interne et à &quot;Internet&quot; pour se connecter au serveur via Internet.
