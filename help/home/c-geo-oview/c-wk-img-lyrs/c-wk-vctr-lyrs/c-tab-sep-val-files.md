---
description: Lors de la création d’une couche vectorielle faisant référence à un fichier de valeurs séparées par des tabulations (.tsv), les données vectorielles sont obtenues en récupérant les instructions de dessin ainsi que les données de longitude et de latitude du fichier .tsv.
solution: Analytics
title: Calques vectoriels faisant référence à des fichiers de valeurs séparées par des tabulations
topic: Data workbench
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Calques vectoriels faisant référence à des fichiers de valeurs séparées par des tabulations{#vector-layers-referencing-tab-separated-values-files}

Lors de la création d’une couche vectorielle faisant référence à un fichier de valeurs séparées par des tabulations (.tsv), les données vectorielles sont obtenues en récupérant les instructions de dessin ainsi que les données de longitude et de latitude du fichier .tsv.

Pour définir un calque vectoriel faisant référence à un [!DNL .tsv] fichier, vous devez disposer des éléments suivants :

* **Fichier[!DNL .tsv]** contenant les données utilisées pour dessiner les vecteurs sur le globe, y compris les données de longitude et de latitude. Pour plus d’informations sur le format requis du [!DNL .tsv] fichier, voir Format [de fichier TSV](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e)vectoriel.

* **Fichier** de calque spécifiant l’emplacement du [!DNL .tsv] fichier. Pour plus d’informations sur le format requis du fichier de calque, voir Format [de fichier de couche](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf)vectorielle.

## Format de fichier TSV vectoriel {#section-a29012c9ff4444ac8a6d41c68482828e}

Le [!DNL .tsv] fichier doit contenir les trois colonnes séparées par des tabulations suivantes :

* **[!DNL Begin]:**Cette colonne doit indiquer s’il faut commencer une nouvelle ligne. Les valeurs de cette colonne peuvent être 0 (ne commencez pas de nouvelle ligne) ou 1 (commencez une nouvelle ligne).
* **[!DNL Longitude]:**Cette colonne doit contenir des valeurs de longitude.
* **[!DNL Latitude]:**Cette colonne doit contenir des valeurs de latitude.

>[!NOTE]
>
>Toutes les colonnes supplémentaires sont ignorées.

Voici un exemple de [!DNL .tsv] fichier contenant des données pour une couche vectorielle :

![](assets/tsv_vectorlayer.png)

## Format de fichier de calque vectoriel {#section-c430923f341f4c93852e9f24b61e82bf}

Chaque fichier de calque vectoriel référençant [!DNL .tsv] des fichiers doit être formaté à l’aide du modèle suivant :

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
   <td colname="col2"> <p>Chemin(s) vers le ou les fichiers <span class="filepath"> .tsv</span> contenant les données vectorielles. </p> <p>Exemple : <span class="filepath"> Maps\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Couleur </td> 
   <td colname="col2"> Vecteur de couleur RVB, exprimé sous la forme (rouge, vert, bleu). Pour chaque couleur du vecteur, vous pouvez saisir une valeur comprise entre 0,0 et 1,0. Par exemple, (1.0, 0.0, 0.0) est rouge vif et (0.5, 0.5, 0.5) est gris. </td> 
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
   <td colname="col2"> Contrôle la précision du tracé des vecteurs. Pour les valeurs plus élevées, les vecteurs sont dessinés de manière moins précise mais plus rapide. La valeur par défaut est 5. </td> 
  </tr> 
 </tbody> 
</table>

