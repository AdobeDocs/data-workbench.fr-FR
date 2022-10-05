---
description: Lors de la création d’une couche vectorielle qui référence un fichier de valeurs séparées par des tabulations (.tsv), les données vectorielles sont obtenues en récupérant les instructions de dessin ainsi que les données de longitude et de latitude du fichier .tsv.
title: Calques vectoriels faisant référence à des fichiers de valeurs séparés par des onglets
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
exl-id: be16ba73-4a98-472b-98f1-1b32e671b763
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 6%

---

# Calques vectoriels faisant référence à des fichiers de valeurs séparés par des onglets{#vector-layers-referencing-tab-separated-values-files}

{{eol}}

Lors de la création d’une couche vectorielle qui référence un fichier de valeurs séparées par des tabulations (.tsv), les données vectorielles sont obtenues en récupérant les instructions de dessin ainsi que les données de longitude et de latitude du fichier .tsv.

Pour définir un calque vectoriel faisant référence à un [!DNL .tsv] , vous devez disposer des éléments suivants :

* **A [!DNL .tsv] fichier** qui contient les données utilisées pour dessiner les vecteurs sur le globe, y compris les données de longitude et de latitude. Pour plus d’informations sur le format requis de la variable [!DNL .tsv] fichier, voir [Format de fichier TSV vectoriel](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e).

* **Un fichier de calque** qui spécifie l’emplacement de la variable [!DNL .tsv] fichier . Pour plus d’informations sur le format requis du fichier de calque, voir [Format de fichier de calque vectoriel](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf).

## Format de fichier TSV vectoriel {#section-a29012c9ff4444ac8a6d41c68482828e}

Le [!DNL .tsv] doit contenir les trois colonnes séparées par des onglets suivantes :

* **[!DNL Begin]:** Cette colonne doit indiquer s’il faut commencer une nouvelle ligne. Les valeurs de cette colonne peuvent être 0 (ne commencez pas de nouvelle ligne) ou 1 (commencez une nouvelle ligne).
* **[!DNL Longitude]:** Cette colonne doit contenir des valeurs de longitude.
* **[!DNL Latitude]:** Cette colonne doit contenir des valeurs de latitude.

>[!NOTE]
>
>Toutes les colonnes supplémentaires sont ignorées.

Voici un exemple : [!DNL .tsv] fichier contenant des données pour une couche vectorielle :

![](assets/tsv_vectorlayer.png)

## Format de fichier de calque vectoriel {#section-c430923f341f4c93852e9f24b61e82bf}

Chaque fichier de calque vectoriel faisant référence [!DNL .tsv] Les fichiers doivent être formatés à l’aide du modèle suivant :

```
Layer = VectorLayer:
  TSV Files = vector: n items
    0 = string: Maps\\File Name.tsv
    1 = string: Maps\\File Name.tsv
    . . .
    n-1 = string: Maps\\File Name.tsv
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

<table id="table_152F73536AB9403AB43854B81D6A9A15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Fichiers TSV </td> 
   <td colname="col2"> <p>Chemin(s) d’accès au <span class="filepath"> .tsv</span> fichier(s) contenant les données vectorielles. </p> <p>Exemple : <span class="filepath"> Maps\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Couleur </td> 
   <td colname="col2"> Le vecteur de couleur du RGB, qui est exprimé sous la forme (rouge, vert, bleu). Pour chaque couleur du vecteur, vous pouvez saisir une valeur comprise entre 0,0 et 1,0. Par exemple, (1,0, 0,0, 0,0) est rouge vif et (0,5, 0,5, 0,5) est gris. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alpha </td> 
   <td colname="col2"> Contrôle la transparence des vecteurs affichés sur le globe. La plage est comprise entre 0 et 1, 0 étant le plus transparent. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Largeur </td> 
   <td colname="col2"> Facultatif. Définit la largeur des données en pixels. La plage recommandée est comprise entre 1 et 4. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Facteur d’erreur </td> 
   <td colname="col2"> Contrôle la précision du dessin des vecteurs. Pour les valeurs plus élevées, les vecteurs sont dessinés de manière moins précise mais plus rapide. La valeur par défaut est 5. </td> 
  </tr> 
 </tbody> 
</table>
