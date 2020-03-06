---
description: Les expressions de mesure, de dimension et de filtre peuvent utiliser des identifiants pour faire référence à des mesures, dimensions et filtres nommés.
solution: Analytics
title: Syntaxe des identifiants
topic: Data workbench
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Syntaxe des identifiants{#syntax-for-identifiers}

Les expressions de mesure, de dimension et de filtre peuvent utiliser des identifiants pour faire référence à des mesures, dimensions et filtres nommés.

Ces identifiants sont sensibles à la casse et doivent être saisis exactement tels qu’ils sont définis.

Un identifiant valide peut contenir un ou plusieurs des éléments suivants :

* Signets de soulignement (_). Les traits de soulignement dans un identifiant représentent des espaces dans la mesure, la dimension ou le nom du filtre. Par exemple, la dimension Référent de session est appelée [!DNL Session_Referrer] dans une expression.
* Signes en pourcentage (%)
* Lettres majuscules (A-Z)
* Lettres en minuscules (a-z)
* Signes en dollars ($)
* Nombres (0-9), sauf comme premier caractère d’un identifiant.
* Caractères non ASCII

Tous les autres caractères sont interdits dans un identifiant.

Ces mêmes règles s’appliquent aux noms des mesures, des dimensions et des filtres lorsqu’ils sont utilisés en dehors des expressions, sauf que les noms peuvent contenir des espaces mais pas des traits de soulignement. Par exemple, vous pouvez définir la dimension Référent de session dans le [!DNL Transformation.cfg] fichier comme Référent de session, mais pas [!DNL Session_Referrer].
