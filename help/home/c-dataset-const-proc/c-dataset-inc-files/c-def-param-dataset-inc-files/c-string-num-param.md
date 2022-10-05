---
description: Les paramètres de chaîne et numériques prennent comme valeurs des chaînes et des nombres, respectivement.
title: Paramètres de chaîne et numériques
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
exl-id: 37d004da-cde7-4b67-b0cb-0acbb6d8ad68
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 5%

---

# Paramètres de chaîne et numériques{#string-and-numeric-parameters}

{{eol}}

Les paramètres de chaîne et numériques prennent comme valeurs des chaînes et des nombres, respectivement.

Vous pouvez les utiliser de manière interchangeable, mais les paramètres numériques doivent être définis pour avoir une valeur numérique. Vous pouvez référencer des paramètres de chaîne et numériques lors de la définition de transformations, de conditions et de dimensions étendues, et vous pouvez référencer plusieurs paramètres dans la même ligne.

Vous ne pouvez pas référencer de paramètres de chaîne et numériques dans [!DNL Input] ou [!DNL Output] , mais vous pouvez utiliser un paramètre de chaîne pour définir un champ d’entrée constant. En outre, vous ne pouvez pas référencer de paramètres de chaîne et numériques dans les décodeurs ou les groupes de décodeurs.

Cet exemple illustre une [!DNL Log Processing Dataset Include] qui définit un paramètre de chaîne et un paramètre numérique. Notez que le paramètre string, appelé &quot;Value Lookups&quot;, définit un emplacement de fichier (Lookups\Values) relatif au répertoire d’installation du serveur Data Workbench.

![](assets/cfg_Parameters_StringNumeric.png)
