---
description: La transformation Unescape URI annule les caractères d’une chaîne qui ont été placés en séquence d’échappement.
solution: Analytics
title: UnescapeURI
topic: Data workbench
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# UnescapeURI{#unescapeuri}

La transformation Unescape URI annule les caractères d’une chaîne qui ont été placés en séquence d’échappement.

>[!NOTE]
>
>Les caractères non sécurisés remplacent les caractères non sécurisés dans une chaîne URI. Ils sont représentés par un triplet constitué d&#39;un signe de pourcentage suivi de deux chiffres hexadécimaux (par exemple, %20).

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d’application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. |  |
| Entrée | Chaîne URI à débloquer. |  |
| Sortie | Nom du champ dans lequel la chaîne sans séquence d’échappement doit être stockée. |  |

La transformation suivante annule la valeur docname dans un champ d’en-tête HTTP et stocke la sortie dans le champ x-docname-unescape ed :

![](assets/cfg_TransformationType_UnescapeURI.png)

Si la valeur docname était

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

alors la valeur de x-docname-unescape serait

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]

