---
description: valeur nulle
solution: Insight,Analytics
title: Modification du paramètre ExpPartialMatch (facultatif)
topic: Data workbench
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modification du paramètre ExpPartialMatch (facultatif){#modifying-the-exppartialmatch-parameter-optional}

Si vous souhaitez permettre à vos expériences contrôlées de remapper la totalité de votre site Web ou un sous-répertoire entier de votre site Web vers un autre emplacement, vous pouvez définir le paramètre ExpPartialMatch dans le [!DNL txlogd.conf] fichier sur &quot;on&quot;. La valeur par défaut est &quot;off&quot;.

Voici un exemple du paramètre ExpPartialMatch :

[!DNL ExpPartialMatch off]

Soyez très prudent lorsque vous définissez ce paramètre sur &quot;on&quot;, car il peut entraîner un remappage accidentel de l’ensemble de votre site Web.
