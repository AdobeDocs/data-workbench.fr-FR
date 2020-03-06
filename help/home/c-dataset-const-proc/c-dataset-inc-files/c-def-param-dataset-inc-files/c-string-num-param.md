---
description: Les paramètres de chaîne et les paramètres numériques prennent comme valeurs les chaînes et les nombres, respectivement.
solution: Analytics
title: Paramètres de chaîne et de nombres
topic: Data workbench
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Paramètres de chaîne et de nombres{#string-and-numeric-parameters}

Les paramètres de chaîne et les paramètres numériques prennent comme valeurs les chaînes et les nombres, respectivement.

Vous pouvez les utiliser de manière interchangeable, mais les paramètres numériques doivent être définis pour avoir une valeur numérique. Vous pouvez référencer des paramètres numériques et de chaîne lors de la définition de transformations, de conditions et de dimensions étendues, et vous pouvez référencer plusieurs paramètres dans la même ligne.

Vous ne pouvez pas référencer de paramètres numériques et de chaîne dans [!DNL Input] ou [!DNL Output] les champs, mais vous pouvez utiliser un paramètre de chaîne pour définir un champ d’entrée constant. En outre, vous ne pouvez pas référencer de paramètres numériques et de chaîne dans les décodeurs ou les groupes de décodeurs.

Cet exemple montre un [!DNL Log Processing Dataset Include] fichier qui définit un paramètre de chaîne et un paramètre numérique. Notez que le paramètre de chaîne, appelé &quot;Recherches de valeur&quot;, définit un emplacement de fichier (Recherches\Valeurs) relatif au répertoire d’installation du serveur de l’outil de données.

![](assets/cfg_Parameters_StringNumeric.png)

