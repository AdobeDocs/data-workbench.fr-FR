---
description: Les expressions de mesure, de dimension et de filtre peuvent utiliser des identifiants pour faire référence à des mesures, dimensions et filtres nommés.
title: Syntaxe des identificateurs
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
exl-id: 79bc5585-7b21-4a9d-b044-28ff4bc5a885
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 3%

---

# Syntaxe des identificateurs{#syntax-for-identifiers}

Les expressions de mesure, de dimension et de filtre peuvent utiliser des identifiants pour faire référence à des mesures, dimensions et filtres nommés.

Ces identifiants sont sensibles à la casse et doivent être entrés exactement comme ils sont définis.

Un identifiant valide peut contenir un ou plusieurs des éléments suivants :

* Signets de soulignement (_). Les traits de soulignement d’un identifiant représentent des espaces dans la mesure, la dimension ou le nom du filtre. Par exemple, la dimension Référent de session est appelée [!DNL Session_Referrer] dans une expression.
* Symboles de pourcentage (%)
* Majuscules (A-Z)
* Lettres en minuscules (a-z)
* Signe dollar ($)
* Nombres (0-9), sauf comme premier caractère d’un identifiant.
* Caractères non ASCII

Tous les autres caractères sont interdits dans un identifiant.

Ces mêmes règles s’appliquent aux noms des mesures, dimensions et filtres lorsqu’ils sont utilisés en dehors des expressions, sauf que les noms peuvent contenir des espaces mais pas des traits de soulignement. Par exemple, vous pouvez définir la dimension Référent de session dans le fichier [!DNL Transformation.cfg] en tant que Référent de session, mais pas [!DNL Session_Referrer].
