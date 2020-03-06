---
description: Vous pouvez créer une couche vectorielle qui référence un ou plusieurs fichiers vectoriels (.vec), qui contient les données qui définissent les vecteurs à dessiner sur le globe.
solution: Analytics
title: Définition de calques vectoriels faisant référence à des fichiers vectoriels
topic: Data workbench
uuid: fe6639fb-98fb-4246-9cc1-1a928df6ae0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Définition de calques vectoriels faisant référence à des fichiers vectoriels{#define-vector-layers-referencing-vector-files}

Vous pouvez créer une couche vectorielle qui référence un ou plusieurs fichiers vectoriels (.vec), qui contient les données qui définissent les vecteurs à dessiner sur le globe.

Pour définir un calque vectoriel faisant référence à un ou plusieurs [!DNL .vec] fichiers, vous devez disposer des éléments suivants :

* **Un ou plusieurs fichiers[!DNL .vec]** contenant les données utilisées pour dessiner les vecteurs sur le globe.

   >[!NOTE]
   >
   >Pour obtenir [!DNL .vec] des fichiers à utiliser avec vos calques vectoriels, contactez Adobe.

* **Fichier** de calque spécifiant l’emplacement des [!DNL .vec] fichiers. Pour plus d’informations sur le format requis du fichier de calque, voir Format [de fichier de couche](../../../../home/c-get-started/c-im-layers/c-vctr-layers/c-ref-vctr-files.md#section-83a0077cf0c8479b9e7b2939bc761af1)vectorielle.

   >[!NOTE]
   >
   >Le [!DNL Boundaries.layer] fichier, fourni avec le [!DNL Geography] profil, est un calque vectoriel qui référence les [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec]et [!DNL mwisland.vec] fichiers.

## Format de fichier de calque vectoriel {#section-83a0077cf0c8479b9e7b2939bc761af1}

Chaque fichier de calque vectoriel référençant [!DNL .vec] des fichiers doit être formaté à l’aide du modèle suivant :

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
| Fichiers Vec | Chemin(s) vers le(s) fichier(s) contenant les données vectorielles. [!DNL .vec] |
| Couleur | Vecteur de couleur RVB, exprimé sous la forme (rouge, vert, bleu). Pour chaque couleur du vecteur, vous pouvez saisir une valeur comprise entre 0,0 et 1,0. Par exemple, (1.0, 0.0, 0.0) est rouge vif et (0.5, 0.5, 0.5) est gris. |
| Alpha | Contrôle la transparence des vecteurs affichés sur le globe. La plage est comprise entre 0 et 1, 0 étant le plus transparent. |
| Largeur | Facultatif. Définit la largeur des données en pixels. La plage recommandée est comprise entre 1 et 4. |
| Facteur d’erreur | Contrôle la précision du tracé des vecteurs. Pour les valeurs plus élevées, les vecteurs sont dessinés de manière moins précise mais plus rapide. La valeur par défaut est 5. |

Le [!DNL Boundaries.layer] fichier est formaté comme suit :

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

