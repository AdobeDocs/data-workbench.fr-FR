---
description: D'un point de vue conceptuel, le fichier d'adresse sert le même objectif que le fichier ETC\HOSTS sur une machine en réseau.
solution: Insight
title: Emplacements réseau
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
translation-type: tm+mt
source-git-commit: f6ec885266de6b6d99615d73fad2a1c22897424b

---


# Emplacements réseau{#network-locations}

D&#39;un point de vue conceptuel, le fichier d&#39;adresse sert le même objectif que le fichier ETC\HOSTS sur une machine en réseau.

Cependant, contrairement au fichier HOSTS, qui décrit une collection unique de noms, le fichier d’adresses contient plusieurs collections de noms appelés emplacements réseau.

Un emplacement réseau est un ensemble nommé de définitions d’adresse. Chaque définition d’adresse de la collection associe un nom commun à une adresse IP.

Dans le fichier d’adresse, un emplacement réseau est défini dans une structure appelée NetworkLocation. Dans l’exemple suivant, NetworkLocation définit un emplacement réseau appelé &quot;MyCorporate Intranet&quot;. Il contient une définition d’adresse qui mappe le nom commun [!DNL VS01.myCompany.com] à l’adresse IP &quot;10.2.1.70&quot;.

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

Comme le montre l&#39;exemple ci-dessus, la structure NetworkLocation se compose de trois paramètres principaux :

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
   <td colname="col2"> Définit zéro ou plusieurs définitions d’adresse. Chaque paramètre AddressDefinition associe un nom commun à une adresse IP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> Attribue un nom à NetworkLocation. Le nom affecté à un NetworkLocation doit être unique dans le fichier d'adresse. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> <p>Spécifie le nom d'un autre NetworkLocation dont les membres sont inclus dans ce NetworkLocation. Ce paramètre permet à un NetworkLocation d’en étendre un autre. </p> <p>Vous pouvez définir le paramètre Parent sur "DNS" pour étendre un NetworkLocation au système DNS normal du client. </p> <p>Exemple : Parent = chaîne : DNS </p> <p>Lorsque DNS est le parent, les clients tentent de résoudre un nom commun à l’aide du système DNS de l’ordinateur client lorsqu’ils ne parviennent pas à résoudre le nom via NetworkLocation. </p> </td> 
  </tr> 
 </tbody> 
</table>
