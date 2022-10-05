---
description: La transformation d’URI Unescape permet de libérer les caractères d’une chaîne qui ont été échappés.
title: UnescapeURI
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
exl-id: abf20906-5052-4bbe-9ffb-522b850669a6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 7%

---

# UnescapeURI{#unescapeuri}

{{eol}}

La transformation d’URI Unescape permet de libérer les caractères d’une chaîne qui ont été échappés.

>[!NOTE]
>
>Les caractères avec échappement remplacent les caractères non sécurisés dans une chaîne URI. Elles sont représentées par un triplet constitué d’un signe de pourcentage suivi de deux chiffres hexadécimaux (par exemple, %20).

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Les conditions dans lesquelles cette transformation est appliquée. |  |
| Par défaut | La valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. |  |
| Entrée | Chaîne d’URI à extraire. |  |
| Sortie | Nom du champ dans lequel la chaîne sans séquence d’échappement doit être stockée. |  |

La transformation suivante annule l’échappement de la valeur docname dans un champ d’en-tête HTTP et stocke la sortie dans le champ x-docname-unescaped :

![](assets/cfg_TransformationType_UnescapeURI.png)

Si la valeur docname était

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

alors la valeur de x-docname-unescape serait

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]
