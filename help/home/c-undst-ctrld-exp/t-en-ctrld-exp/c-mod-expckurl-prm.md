---
description: Le paramètre ExpCookieURL peut être utilisé pour tester le bon fonctionnement de votre expérience contrôlée.
solution: Analytics
title: Modification du paramètre ExpCookieURL (facultatif)
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---

# Modification du paramètre ExpCookieURL (facultatif){#modifying-the-expcookieurl-paramter-optional}

{{eol}}

Le paramètre ExpCookieURL peut être utilisé pour tester le bon fonctionnement de votre expérience contrôlée.

Ce paramètre définit l’URL d’une page virtuelle qui, si nécessaire, vous place dans une expérience et un groupe spécifiés, puis vous redirige vers la racine de votre site web. De ce point à la fin de l’expérience, vous faites partie de l’expérience et du groupe spécifiés.

La page par défaut de ce paramètre est [!DNL setcookie.htm], mais vous pouvez utiliser n’importe quelle URL virtuelle valide.

>[!NOTE]
>
>Il doit s’agir d’une URL virtuelle et non d’une page ou d’un élément de contenu existant. Aucun fichier ne doit se trouver sur le serveur web à l’emplacement spécifié avec le nom spécifié.

Voici un exemple du paramètre ExpCookieURL :

[!DNL ExpCookieURL /setcookie.htm]
