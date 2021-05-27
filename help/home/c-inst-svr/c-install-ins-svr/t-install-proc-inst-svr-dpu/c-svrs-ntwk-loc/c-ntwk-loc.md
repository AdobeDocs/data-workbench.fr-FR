---
description: Conceptuellement, le fichier d’adresse a le même objectif que le fichier ETC&bsol;HOSTS sur une machine en réseau.
title: Emplacements du réseau
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
exl-id: 938217da-8935-4f2a-b5f8-9afc1dd489f3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# Emplacements du réseau{#network-locations}

Conceptuellement, le fichier d’adresse a le même objectif que le fichier ETC&amp;bsol;HOSTS sur une machine en réseau.

Cependant, contrairement au fichier HOSTS, qui décrit une seule collection de noms, le fichier d’adresse contient plusieurs collections de noms appelées emplacements réseau.

Un emplacement réseau est un ensemble nommé de définitions d’adresse. Chaque définition d’adresse dans la collection associe un nom commun à une adresse IP.

Dans le fichier d’adresse, un emplacement réseau est défini dans une structure appelée NetworkLocation. Dans l’exemple suivant, NetworkLocation définit un emplacement réseau appelé &quot;MyCorporate Intranet&quot;. Elle contient une définition d’adresse qui mappe le nom commun [!DNL VS01.myCompany.com] à l’adresse IP &quot;10.2.1.70&quot;.

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

Comme illustré dans l’exemple ci-dessus, la structure NetworkLocation se compose de trois paramètres principaux :

<table id="table_9142A0EFA15E4C37975E7ACE234F6FDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Adresses </td> 
   <td colname="col2"> Définit zéro ou plusieurs définitions d’adresse. Chaque valeur AddressDefintion associe un nom commun à une adresse IP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> Attribue un nom à NetworkLocation. Le nom attribué à un NetworkLocation doit être unique dans le fichier d’adresse. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> <p>Spécifie le nom d’un autre NetworkLocation dont les membres sont inclus dans ce NetworkLocation. Ce paramètre permet à un NetworkLocation d’en étendre un autre. </p> <p>Vous pouvez définir le paramètre Parent sur "DNS" pour étendre un NetworkLocation au système DNS normal du client. </p> <p>Exemple : Parent = chaîne : DNS </p> <p>Lorsque DNS est le parent, les clients tentent de résoudre un nom commun à l’aide du système DNS de l’ordinateur client lorsqu’ils ne peuvent pas résoudre le nom par le biais de NetworkLocation. </p> </td> 
  </tr> 
 </tbody> 
</table>
