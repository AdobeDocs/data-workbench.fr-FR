---
description: Avant de configurer l’expérience, vous devez créer le contenu alternatif que vous souhaitez utiliser dans l’expérience.
solution: Insight,Analytics
title: Création du contenu du test
topic: Data workbench
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Création du contenu du test{#creating-the-test-content}

Avant de configurer l’expérience, vous devez créer le contenu alternatif que vous souhaitez utiliser dans l’expérience.

Le groupe de contrôle est envoyé à l’URI d’origine, tandis que le groupe de test est envoyé au nouvel URI alternatif.

Pour éviter toute confusion, ne réutilisez pas les noms de fichier de groupe de tests. Par exemple, si vous exécutez une expérience à l’aide d’un fichier de groupe de tests nommé [!DNL test2.asp], n’utilisez pas [!DNL test2.asp] comme nom du fichier de test dans votre prochaine expérience.

Pour l’hypothèse selon laquelle le déplacement du lien graphique &quot;Demander une démo&quot; sur votre page d’accueil aurait un impact sur la conversion des visiteurs, nous créons la page d’accueil alternative contenant le lien graphique &quot;Demander une démo&quot; dans la nouvelle position. La section suivante décrit la procédure à suivre pour spécifier que l’URI du groupe de contrôle [!DNL index.asp] soit remplacé par l’URI [!DNL index2.asp] du groupe de test pour un certain pourcentage de visiteurs.
