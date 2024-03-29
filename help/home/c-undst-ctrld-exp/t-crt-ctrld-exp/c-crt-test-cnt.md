---
description: Avant de configurer l’expérience, vous devez créer le contenu alternatif que vous souhaitez utiliser dans l’expérience.
solution: Analytics
title: Création du contenu test
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
exl-id: fd46c6af-37e8-452a-880d-147b7d0cfe21
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---

# Création du contenu test{#creating-the-test-content}

{{eol}}

Avant de configurer l’expérience, vous devez créer le contenu alternatif que vous souhaitez utiliser dans l’expérience.

La population témoin est envoyée à l’URI d’origine, tandis que le groupe test est envoyé au nouvel URI alternatif.

Pour éviter toute confusion, ne réutilisez pas les noms de fichiers de groupe de test. Par exemple, si vous exécutez une expérience en utilisant un fichier de groupe de test nommé [!DNL test2.asp], n’utilisez pas [!DNL test2.asp] comme nom du fichier de test dans votre prochaine expérience.

Pour l’hypothèse que le déplacement du lien graphique &quot;Demander une démonstration&quot; sur votre page d’accueil impacte la conversion du visiteur, nous créons la page d’accueil alternative contenant le lien graphique &quot;Demander une démonstration&quot; dans la nouvelle position. La section suivante décrit la manière dont vous spécifiez ensuite l’URI du groupe de contrôle [!DNL index.asp] être remplacé par l’URI du groupe de test [!DNL index2.asp] pour un certain pourcentage de visiteurs.
