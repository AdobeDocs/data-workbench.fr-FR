---
description: Si les clients peuvent accéder à un serveur Insight via plusieurs réseaux (par exemple, via l’intranet d’entreprise et par Internet), le fichier d’adresses doit définir un emplacement réseau distinct pour chacune des adresses IP du serveur.
title: Plusieurs adresses IP pour un serveur Insight
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
exl-id: 71654a60-af82-45f2-826b-29ecc7127b0b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---

# Plusieurs adresses IP pour un serveur Insight{#multiple-ip-addresses-for-an-insight-server}

Si les clients peuvent accéder à un serveur Insight via plusieurs réseaux (par exemple, via l’intranet d’entreprise et par Internet), le fichier d’adresses doit définir un emplacement réseau distinct pour chacune des adresses IP du serveur.

Par exemple, si le serveur [!DNL VS01.myCompany.com] a une adresse IP de 10.2.1.70 sur un réseau interne et une adresse IP de 65.196.125.167 sur Internet, le fichier d’adresses inclut un emplacement réseau pour chacune des adresses comme illustré dans l’exemple ci-dessous :

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

Lorsque les utilisateurs se connectent à un [!DNL Insight Server], ils utilisent le paramètre NetworkLocation (dans l’interface utilisateur cliente) pour spécifier l’emplacement réseau par lequel ils souhaitent résoudre le nom commun du serveur. Par exemple, dans un fichier d’adresse avec les deux NetworkLocations ci-dessus, un utilisateur définit le paramètre NetworkLocation sur &quot;MyCorporate Intranet&quot; pour se connecter à [!DNL Insight Server] via le réseau interne et à &quot;Internet&quot; pour se connecter au serveur via Internet.
