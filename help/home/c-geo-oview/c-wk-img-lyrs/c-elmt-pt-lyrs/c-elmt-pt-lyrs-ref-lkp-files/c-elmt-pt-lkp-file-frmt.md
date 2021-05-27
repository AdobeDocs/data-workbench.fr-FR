---
description: Informations sur les colonnes de calque de point d’élément.
title: Format de fichier Lookup de point d’élément
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
exl-id: da81da9e-0567-4f3a-bc0d-ab6c5e4a23b7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 6%

---

# Format de fichier Lookup de point d’élément{#element-point-lookup-file-format}

Informations sur les colonnes de calque de point d’élément.

Le fichier de recherche de calque de point d’élément doit contenir au moins les trois colonnes suivantes :

* **[!DNL Key]colonne :** cette colonne doit contenir des données de clé communes, ce qui permet au serveur Data Workbench de connecter les données du fichier de recherche à celles du jeu de données. La colonne [!DNL Key] doit être la première colonne du fichier de recherche. Chaque ligne de cette colonne identifie un élément de la dimension.

* **[!DNL Longitude]column :** cette colonne doit contenir la longitude pour chaque point de données de la  [!DNL Key] colonne.

* **[!DNL Latitude]column :** cette colonne doit contenir la latitude pour chaque point de données de la  [!DNL Key] colonne.

* **[!DNL Name]colonne :**  (facultatif). Si vous souhaitez spécifier un nom à afficher sur la carte pour chaque point de données, vous pouvez inclure une colonne [!DNL Name] dans le fichier de recherche.

Chaque ligne du fichier de recherche [!DNL Zip Points.txt] contient un code postal dans la première colonne, suivi de la longitude, de la latitude et du nom de la ville associée.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```
