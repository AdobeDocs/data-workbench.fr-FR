---
description: Règles de syntaxe pour les formules.
solution: Analytics
title: Syntaxe de n’importe quelle expression
topic: Data workbench
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Syntaxe de n’importe quelle expression{#syntax-for-any-expression}

Règles de syntaxe pour les formules.

* Dans une formule, les mots-clés sont sensibles à la casse et doivent être saisis exactement comme ils apparaissent.
* Dans une formule, une mesure, une dimension et des noms de filtre qui incluent des espaces doivent utiliser des traits de soulignement entre les mots. Par exemple : [!DNL Page_Views]
* Pour les chaînes dans les expressions, vous devez échapper à certains guillemets simples, guillemets doubles et barres obliques inverses. Par exemple :

   * [!DNL “can’t”] est acceptable et n&#39;a pas besoin d&#39;être échappé, mais [!DNL ‘can’t’] est inacceptable et doit s&#39;échapper comme [!DNL ‘can\’t’].

   * [!DNL c:\windows] doit être échappé comme [!DNL c:\\windows].

