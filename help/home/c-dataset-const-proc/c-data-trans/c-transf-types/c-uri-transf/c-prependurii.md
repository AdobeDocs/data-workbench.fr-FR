---
description: Tout comme la transformation AppendURI, la transformation PrependURI affecte le champ interne utilisé par le serveur Data Workbench pour construire la dimension URI.
title: PrependURI
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
exl-id: c39d9241-ed66-446e-b59d-fdb11942d0e8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 6%

---

# PrependURI{#prependuri}

Tout comme la transformation AppendURI, la transformation PrependURI affecte le champ interne utilisé par le serveur Data Workbench pour construire la dimension URI.

La transformation [!DNL PrependURI] fonctionne en ajoutant la valeur dans le champ d’entrée identifié au début de la valeur actuellement dans l’URI.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Les conditions dans lesquelles cette transformation est appliquée. |  |
| Par défaut | La valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. |  |
| Entrée | Nom du champ dont la valeur est précédée de l’URI. |  |

L’exemple suivant fait simplement précéder le champ s-dns de l’URI, étendant la représentation de la dimension URI pour inclure le domaine demandé par l’appareil client.

![](assets/cfg_TransformationType_PrependURI.png)

Dans cet exemple, ajouter le champ s-dns à l’URI

* [!DNL /modelview.asp&id=login]

génère l’URL suivante :

* [!DNL www.adobe.com/modelview.asp?id=login]

Désormais, l’URI est étendu pour inclure le domaine demandé.
