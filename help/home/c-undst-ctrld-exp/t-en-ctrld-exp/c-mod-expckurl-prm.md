---
description: Le paramètre ExpCookieURL peut être utilisé pour tester le bon fonctionnement de votre expérience contrôlée.
solution: Analytics,Analytics
title: Modification du paramètre ExpCookieURL (facultatif)
topic: Data workbench
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---


# Modification du paramètre ExpCookieURL (facultatif){#modifying-the-expcookieurl-paramter-optional}

Le paramètre ExpCookieURL peut être utilisé pour tester le bon fonctionnement de votre expérience contrôlée.

Ce paramètre définit l’URL d’une page virtuelle qui, lorsqu’elle est demandée, vous place dans une expérience et un groupe spécifiés, puis vous redirige vers la racine de votre site Web. De ce point à la fin de l&#39;expérience, vous faites partie de l&#39;expérience et du groupe spécifiés.

La page par défaut de ce paramètre est [!DNL setcookie.htm], mais vous pouvez utiliser n’importe quelle URL virtuelle valide.

>[!NOTE]
>
>Il doit s’agir d’une URL virtuelle et non d’une page ou d’un élément de contenu existant. Aucun fichier ne doit se trouver sur le serveur Web au chemin d’accès spécifié avec le nom spécifié.

Voici un exemple du paramètre ExpCookieURL :

[!DNL ExpCookieURL /setcookie.htm]
