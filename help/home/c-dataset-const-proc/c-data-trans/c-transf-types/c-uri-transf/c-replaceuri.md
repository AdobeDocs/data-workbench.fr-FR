---
description: La transformation ReplaceURI transforme la valeur de la dimension URI interne en une nouvelle valeur.
solution: Analytics
title: ReplaceURI
topic: Data workbench
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ReplaceURI{#replaceuri}

La transformation ReplaceURI transforme la valeur de la dimension URI interne en une nouvelle valeur.

Si [!DNL URI Prefix] est spécifié, la valeur obtenue est simplement le préfixe URI concaténé avec la valeur d’entrée fournie.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d’application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. |  |
| Entrée | Valeur de remplacement de l’URI. |  |
| Préfixe URI | La valeur (chaîne) à ajouter à la valeur du [!DNL Input] champ. |  |

>[!NOTE]
>
>Avant d’appliquer [!DNL ReplaceURI] des transformations, vous devez créer une nouvelle dimension simple avec un parent de [!DNL Page View]à partir d’une copie de cs-uri-stem ou cs-uri. Pour obtenir de l’aide à ce sujet, contactez Adobe.

Cet exemple illustre l&#39;utilisation de [!DNL ReplaceURI] pour remplacer les chaînes de requête &quot;page=*pageid*&quot; par &quot; [!DNL homepage.html]&quot; lorsque pageid ** indique que la page d&#39;accueil du site Web a été consultée. Le résultat final est une vue plus conviviale de l’URI.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

Pour la transformation affichée, la page

* [!DNL www.examplesite.com/info.html?page=1550]

serait remplacé par

* [!DNL www.examplesite.com/homepage.html]

