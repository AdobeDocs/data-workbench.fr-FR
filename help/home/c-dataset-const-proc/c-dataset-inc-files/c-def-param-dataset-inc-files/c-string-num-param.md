---
description: Les paramètres de chaîne et les paramètres numériques prennent comme valeurs les chaînes et les nombres, respectivement.
title: Paramètres de chaîne et numériques
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
exl-id: 37d004da-cde7-4b67-b0cb-0acbb6d8ad68
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 5%

---

# Paramètres de chaîne et numériques{#string-and-numeric-parameters}

Les paramètres de chaîne et les paramètres numériques prennent comme valeurs les chaînes et les nombres, respectivement.

Vous pouvez les utiliser de manière interchangeable, mais les paramètres numériques doivent être définis pour avoir une valeur numérique. Vous pouvez référencer des paramètres numériques et de chaîne lors de la définition de transformations, de conditions et de dimensions étendues, et vous pouvez référencer plusieurs paramètres dans la même ligne.

Vous ne pouvez pas référencer de paramètres numériques et de chaîne dans les champs [!DNL Input] ou [!DNL Output], mais vous pouvez utiliser un paramètre de chaîne pour définir un champ d’entrée constant. En outre, vous ne pouvez pas référencer de paramètres numériques et de chaîne dans les décodeurs ou les groupes de décodeurs.

Cet exemple montre un fichier [!DNL Log Processing Dataset Include] qui définit un paramètre de chaîne et un paramètre numérique. Notez que le paramètre de chaîne, appelé &quot;Recherches de valeur&quot;, définit un emplacement de fichier (Recherches\Valeurs) relatif au répertoire d’installation du serveur de l’outil de données.

![](assets/cfg_Parameters_StringNumeric.png)
