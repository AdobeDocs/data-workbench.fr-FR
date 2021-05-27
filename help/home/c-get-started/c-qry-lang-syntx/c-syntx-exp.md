---
description: Règles de syntaxe des formules.
title: Syntaxe de toute expression
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%

---

# Syntaxe de toute expression{#syntax-for-any-expression}

Règles de syntaxe des formules.

* Dans une formule, les mots-clés sont sensibles à la casse et doivent être entrés exactement comme ils apparaissent.
* Lorsque vous vous trouvez dans une formule, un nom de mesure, de dimension et de filtre qui comprend des espaces, vous devez utiliser des traits de soulignement entre des mots. Par exemple : [!DNL Page_Views]
* Pour les chaînes d’expressions, vous devez échapper certains guillemets simples, guillemets doubles et barres obliques inverses. Par exemple :

   * [!DNL “can’t”] est acceptable et n’a pas besoin d’être échappé, mais  [!DNL ‘can’t’] est inacceptable et doit être ignoré comme  [!DNL ‘can\’t’].

   * [!DNL c:\windows] doivent être placées dans une séquence d’échappement en tant que  [!DNL c:\\windows].
