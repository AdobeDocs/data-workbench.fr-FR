---
description: Règles de syntaxe pour les formules.
title: Syntaxe de toute expression
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%

---

# Syntaxe de toute expression{#syntax-for-any-expression}

Règles de syntaxe pour les formules.

* Dans une formule, les mots-clés respectent la casse et doivent être saisis exactement comme ils s&#39;affichent.
* Dans une formule, les noms de mesure, de dimension et de filtre contenant des espaces doivent utiliser des traits de soulignement entre les mots. Par exemple : [!DNL Page_Views]
* Pour les chaînes dans les expressions, vous devez placer certains guillemets simples, guillemets de doublon et barres obliques inverses en échappement. Par exemple :

   * [!DNL “can’t”] est acceptable et n&#39;a pas besoin d&#39;être évité, mais  [!DNL ‘can’t’] est inacceptable et doit s&#39;échapper comme  [!DNL ‘can\’t’]une.

   * [!DNL c:\windows] doit être échappé en tant que  [!DNL c:\\windows].
