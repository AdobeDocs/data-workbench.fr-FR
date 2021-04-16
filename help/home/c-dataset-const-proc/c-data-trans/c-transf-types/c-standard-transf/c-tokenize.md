---
description: La transformation Tokenize applique itérativement une expression régulière à la chaîne d'entrée.
title: Tokenize
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
exl-id: c1f39b5b-4717-44f6-99c7-4e6a215f3542
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 5%

---

# Tokenize{#tokenize}

La transformation Tokenize applique itérativement une expression régulière à la chaîne d&#39;entrée.

Cependant, contrairement à [!DNL RETransform], [!DNL Tokenize] ne doit pas nécessairement correspondre à la chaîne entière : l&#39;expression régulière utilisée pour la transformation [!DNL Tokenize] peut correspondre à un sous-ensemble de l&#39;entrée. Après avoir trouvé une correspondance, [!DNL Tokenize] applique de nouveau l&#39;expression normale, en commençant par le caractère après la fin de la dernière correspondance.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez entrer n&#39;importe quel nom ici. |  |
| Respect de la casse | Vrai ou faux. Indique si la correspondance est sensible à la casse. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d&#39;application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible ou que l’expression régulière ne correspond pas à la valeur d’entrée. |  |
| Expression | Expression régulière utilisée pour la correspondance. |  |
| Sorties | Noms des chaînes de sortie. Vous pouvez avoir plusieurs sorties pour une chaîne d’entrée donnée. Le nombre de sorties doit correspondre au nombre de sous-modèles capturés dans l’expression régulière. |  |

Dans l&#39;exemple suivant, la transformation [!DNL Tokenize] utilise une expression régulière pour capturer les noms des chaînes de requête (dans cs-uri-requête) et générer le sous-modèle capturé (le nom de la requête) en x-pull-requête-name.

![](assets/cfg_TransformationType_Tokenize.png)

Pour la chaîne de requête &quot;a=b&amp;c=d&quot;, la sortie serait un vecteur contenant &quot;a&quot; et &quot;c&quot;.

Pour plus d&#39;informations sur les expressions régulières, voir [Expressions régulières](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
