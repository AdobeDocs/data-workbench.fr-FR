---
description: Vous pouvez créer une couche vectorielle qui référence un ou plusieurs fichiers vectoriels (.vec), qui contient les données qui définissent les vecteurs à dessiner sur le globe.
title: Définir des calques vectoriels faisant référence à des fichiers vectoriels
uuid: 162d4ecc-d305-42e3-a5d4-0c1609a40f29
exl-id: c6da3cd9-f42a-4e9c-ae48-9f4ffdc42f7b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 7%

---

# Définir des calques vectoriels faisant référence à des fichiers vectoriels{#defining-vector-layers-referencing-vector-files}

Vous pouvez créer une couche vectorielle qui référence un ou plusieurs fichiers vectoriels (.vec), qui contient les données qui définissent les vecteurs à dessiner sur le globe.

Pour définir une couche vectorielle qui référence un ou plusieurs fichiers [!DNL .vec], vous devez disposer des éléments suivants :

* Un ou plusieurs fichiers [!DNL .vec]contenant les données utilisées pour dessiner les vecteurs sur le globe.

   >[!NOTE]
   >
   >Pour obtenir des fichiers [!DNL .vec] à utiliser avec vos calques vectoriels, contactez Adobe.

* Fichier de calque spécifiant l’emplacement des fichiers [!DNL .vec]. Pour plus d’informations sur le format requis du fichier de calque, voir [Format de fichier de calque vectoriel](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-def-vctr-files.md#section-530d03f41ede4a339aebbb680e15240a).

   >[!NOTE]
   >
   >Le fichier [!DNL Boundaries.layer], fourni avec le profil [!DNL Geography], est une couche vectorielle qui référence les fichiers [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec] et [!DNL mwisland.vec].

## Format de fichier de calque vectoriel {#section-530d03f41ede4a339aebbb680e15240a}

Chaque fichier de calque vectoriel référençant des fichiers [!DNL .vec]doit être formaté à l’aide du modèle suivant :

```
Layer = VectorLayer:
  Vec Files = vector: n items
    0 = string: Maps\\.vec file 1
    1 = string: Maps\\.vec file 2
    . . .
    n-1 = string: Maps\\.vec file n
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

| Paramètre | Description |
|---|---|
| Fichiers Vec | Chemin(s) vers le ou les fichiers [!DNL .vec] contenant les données vectorielles. |
| Couleur | Le vecteur de couleur RVB, exprimé sous la forme (rouge, vert, bleu). Pour chaque couleur du vecteur, vous pouvez saisir une valeur comprise entre 0,0 et 1,0. Par exemple, (1,0, 0,0, 0,0) est rouge vif et (0,5, 0,5, 0,5) est gris. |
| Alpha | Contrôle la transparence des vecteurs affichés sur le globe. La plage est comprise entre 0 et 1, 0 étant le plus transparent. |
| Largeur | Facultatif. Définit la largeur des données en pixels. La plage recommandée est comprise entre 1 et 4. |
| Facteur d’erreur | Contrôle la précision du dessin des vecteurs. Pour les valeurs plus élevées, les vecteurs sont dessinés de manière moins précise mais plus rapide. La valeur par défaut est 5. |

Le fichier [!DNL Boundaries.layer] est formaté comme suit :

```
 Boundaries.layer file is formatted as follows:
Layer = VectorLayer:
  Vec Files = vector: 5 items
    0 = string: Maps\\mwnation.vec
    1 = string: Maps\\mwstate.vec
    2 = string: Maps\\mwcoast.vec
    3 = string: Maps\\mwlake.vec
    4 = string: Maps\\mwisland.vec
  Color = v3d: (.5,.5,1)
  Alpha = double: .5
  Error Factor = double: 4
```
