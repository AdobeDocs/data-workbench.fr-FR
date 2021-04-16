---
description: La transformation Unescape URI annule l’échappement des caractères d’une chaîne qui ont été placés en séquence d’échappement.
title: UnescapeURI
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
exl-id: abf20906-5052-4bbe-9ffb-522b850669a6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 6%

---

# UnescapeURI{#unescapeuri}

La transformation Unescape URI annule l’échappement des caractères d’une chaîne qui ont été placés en séquence d’échappement.

>[!NOTE]
>
>Les caractères non sécurisés dans une chaîne URI sont remplacés par des caractères non sécurisés. Ils sont représentés par un triolet constitué d&#39;un signe de pourcentage suivi de deux chiffres hexadécimaux (par exemple, %20).

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez entrer n&#39;importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d&#39;application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. |  |
| Entrée | Chaîne URI à extraire. |  |
| Sortie | Nom du champ dans lequel la chaîne sans échappement doit être stockée. |  |

La transformation suivante annule l’échappement de la valeur docname dans un champ d’en-tête HTTP et stocke la sortie dans le champ x-docname-unescape ed :

![](assets/cfg_TransformationType_UnescapeURI.png)

Si la valeur docname était

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

alors la valeur de x-docname-unescape serait

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]
