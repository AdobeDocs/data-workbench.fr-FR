---
description: Tout comme la transformation AppendURI, la transformation PrependURI affecte le champ interne utilisé par le serveur de l’outil de données pour construire la dimension URI.
title: PrependURI
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
exl-id: c39d9241-ed66-446e-b59d-fdb11942d0e8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 6%

---

# PrependURI{#prependuri}

Tout comme la transformation AppendURI, la transformation PrependURI affecte le champ interne utilisé par le serveur de l’outil de données pour construire la dimension URI.

La transformation [!DNL PrependURI] fonctionne en ajoutant la valeur dans le champ d&#39;entrée identifié au début de la valeur actuellement dans l&#39;URI.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez entrer n&#39;importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d&#39;application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. |  |
| Entrée | Nom du champ dont la valeur est précédée de l’URI. |  |

L’exemple suivant ajoute simplement le champ s-dns à l’URI, en étendant la représentation de la dimension URI pour inclure le domaine demandé par le périphérique client.

![](assets/cfg_TransformationType_PrependURI.png)

Dans cet exemple, le préfixe du champ s-dns sur l’URI

* [!DNL /modelview.asp&id=login]

génère l’URL suivante :

* [!DNL www.adobe.com/modelview.asp?id=login]

Désormais, l’URI est étendu pour inclure le domaine demandé.
