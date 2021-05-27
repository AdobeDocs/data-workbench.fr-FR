---
description: La transformation ReplaceURI remplace la valeur de la dimension URI interne par une nouvelle valeur.
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 5%

---

# ReplaceURI{#replaceuri}

La transformation ReplaceURI remplace la valeur de la dimension URI interne par une nouvelle valeur.

Si [!DNL URI Prefix] est spécifié, la valeur obtenue est simplement le préfixe URI concaténé avec la valeur d’entrée fournie.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Les conditions dans lesquelles cette transformation est appliquée. |  |
| Par défaut | La valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. |  |
| Entrée | La valeur pour remplacer l’URI. |  |
| Préfixe URI | La valeur (string) à ajouter en préfixe à la valeur dans le champ [!DNL Input]. |  |

>[!NOTE]
>
>Avant d’appliquer des transformations [!DNL ReplaceURI], vous devez créer une nouvelle dimension simple avec un parent de [!DNL Page View]à partir d’une copie de cs-uri-stem ou cs-uri. Pour obtenir de l’aide à ce sujet, contactez Adobe.

Cet exemple illustre l’utilisation de [!DNL ReplaceURI] pour remplacer les chaînes de requête &quot;page=*pageid*&quot; par &quot;[!DNL homepage.html]&quot; lorsque *pageid* indique que la page d’accueil du site Web a été consultée. Le résultat final est une vue plus conviviale de l’URI.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

Pour la transformation affichée, la page

* [!DNL www.examplesite.com/info.html?page=1550]

est remplacé par

* [!DNL www.examplesite.com/homepage.html]
