---
description: Vous pouvez créer une couche vectorielle qui référence un ou plusieurs fichiers vectoriels (.vec), qui contient les données qui définissent les vecteurs à dessiner sur le globe.
title: Définir des calques vectoriels faisant référence à des fichiers vectoriels
uuid: fe6639fb-98fb-4246-9cc1-1a928df6ae0a
exl-id: d78fa7ea-e2a9-42b7-9071-5f72409c5b7a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 7%

---

# Définir des calques vectoriels faisant référence à des fichiers vectoriels{#define-vector-layers-referencing-vector-files}

Vous pouvez créer une couche vectorielle qui référence un ou plusieurs fichiers vectoriels (.vec), qui contient les données qui définissent les vecteurs à dessiner sur le globe.

Pour définir un calque vectoriel faisant référence à un ou plusieurs fichiers [!DNL .vec], vous devez disposer des éléments suivants :

* **Un ou plusieurs  [!DNL .vec]** fichiers contenant les données utilisées pour dessiner les vecteurs sur le globe.

   >[!NOTE]
   >
   >Pour obtenir des fichiers [!DNL .vec] à utiliser avec vos calques vectoriels, contactez l’Adobe.

* **Un** fichier de calque spécifiant l’emplacement des  [!DNL .vec] fichiers. Pour plus d’informations sur le format requis du fichier de calque, voir [Format de fichier de couche vectorielle](../../../../home/c-get-started/c-im-layers/c-vctr-layers/c-ref-vctr-files.md#section-83a0077cf0c8479b9e7b2939bc761af1).

   >[!NOTE]
   >
   >Le fichier [!DNL Boundaries.layer], fourni avec le profil [!DNL Geography], est une couche vectorielle qui référence les fichiers [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec] et [!DNL mwisland.vec].

## Format de fichier de calque vectoriel {#section-83a0077cf0c8479b9e7b2939bc761af1}

Chaque fichier de calque vectoriel référençant des fichiers [!DNL .vec] doit être formaté à l’aide du modèle suivant :

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
| Couleur | Vecteur de couleur RVB, exprimé sous la forme (rouge, vert, bleu). Pour chaque couleur du vecteur, vous pouvez entrer une valeur comprise entre 0.0 et 1.0. Par exemple, (1.0, 0.0, 0.0) est rouge vif et (0.5, 0.5, 0.5) est gris. |
| Alpha | Contrôle la transparence des vecteurs affichés sur le globe. La plage est comprise entre 0 et 1, 0 étant le plus transparent. |
| Largeur | Facultatif. Définit la largeur des données en pixels. La plage recommandée est comprise entre 1 et 4. |
| Facteur d’erreur | Contrôle la précision du tracé des vecteurs. Pour les valeurs plus élevées, les vecteurs sont dessinés de manière moins précise mais plus rapide. La valeur par défaut est 5. |

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
