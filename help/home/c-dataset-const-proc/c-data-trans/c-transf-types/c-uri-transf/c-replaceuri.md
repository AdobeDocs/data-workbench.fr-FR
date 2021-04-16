---
description: La transformation ReplaceURI remplace la valeur de la dimension URI interne par une nouvelle valeur.
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 5%

---

# ReplaceURI{#replaceuri}

La transformation ReplaceURI remplace la valeur de la dimension URI interne par une nouvelle valeur.

Si [!DNL URI Prefix] est spécifié, la valeur résultante est simplement le préfixe URI concaténé avec la valeur d’entrée fournie.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez entrer n&#39;importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d&#39;application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. |  |
| Entrée | Valeur de remplacement de l’URI. |  |
| Préfixe URI | Valeur (chaîne) devant être précédée de la valeur dans le champ [!DNL Input]. |  |

>[!NOTE]
>
>Avant d&#39;appliquer des transformations [!DNL ReplaceURI], vous devez créer une nouvelle dimension simple avec un parent de [!DNL Page View]à partir d&#39;une copie de cs-uri-stem ou cs-uri. Pour obtenir de l&#39;aide, contactez l&#39;Adobe.

Cet exemple montre comment utiliser [!DNL ReplaceURI] pour remplacer les chaînes de requête &quot;page=*pageid*&quot; par &quot; [!DNL homepage.html]&quot; lorsque *pageid* indique que la page d&#39;accueil du site Web a été consultée. Le résultat final est une vue plus conviviale de l’URI.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

Pour la transformation affichée, la page

* [!DNL www.examplesite.com/info.html?page=1550]

serait remplacé par

* [!DNL www.examplesite.com/homepage.html]
