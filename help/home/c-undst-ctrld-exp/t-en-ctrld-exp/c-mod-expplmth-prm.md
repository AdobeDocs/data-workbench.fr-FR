---
description: Modification du paramètre ExpPartialMatch (facultatif)
title: Modification du paramètre ExpPartialMatch (facultatif)
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 18%

---

# Modification du paramètre ExpPartialMatch (facultatif){#modifying-the-exppartialmatch-parameter-optional}

Si vous souhaitez permettre à vos expériences contrôlées de remapper l’intégralité de votre site web ou un sous-répertoire entier de votre site web vers un autre emplacement, vous pouvez définir le paramètre ExpPartialMatch dans le fichier [!DNL txlogd.conf] sur &quot;on&quot;. La valeur par défaut est &quot;off&quot;.

Voici un exemple du paramètre ExpPartialMatch :

[!DNL ExpPartialMatch off]

Soyez très prudent lorsque vous définissez ce paramètre sur &quot;activé&quot;, car il peut entraîner un remapping accidentel de l’ensemble de votre site web.
