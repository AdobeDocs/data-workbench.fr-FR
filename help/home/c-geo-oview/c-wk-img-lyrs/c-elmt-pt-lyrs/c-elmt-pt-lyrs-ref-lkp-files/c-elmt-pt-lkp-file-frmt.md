---
description: Informations sur les colonnes de calque de point d’élément.
solution: Analytics
title: Format du fichier de recherche de point d’élément
topic: Data workbench
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Format du fichier de recherche de point d’élément{#element-point-lookup-file-format}

Informations sur les colonnes de calque de point d’élément.

Le fichier de recherche de calque de point d’élément doit contenir au moins trois colonnes :

* **[!DNL Key]colonne :**Cette colonne doit contenir des données de clé communes, ce qui permet au serveur de l’outil de données de connecter les données du fichier de recherche à celles du jeu de données. La[!DNL Key]colonne doit être la première colonne du fichier de recherche. Chaque ligne de cette colonne identifie un élément de la dimension.

* **[!DNL Longitude]colonne :**Cette colonne doit contenir la longitude de chaque point de données de la[!DNL Key]colonne.

* **[!DNL Latitude]colonne :**Cette colonne doit contenir la latitude de chaque point de données de la[!DNL Key]colonne.

* **[!DNL Name]colonne :**(Facultatif). Si vous souhaitez spécifier un nom à afficher sur la carte pour chaque point de données, vous pouvez inclure une[!DNL Name]colonne dans le fichier de recherche.

Chaque ligne du fichier de [!DNL Zip Points.txt] recherche contient un code postal dans la première colonne, suivi de la longitude, de la latitude et du nom de la ville associée.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

