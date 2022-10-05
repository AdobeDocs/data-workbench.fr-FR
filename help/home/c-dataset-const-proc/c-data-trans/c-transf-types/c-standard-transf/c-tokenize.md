---
description: La transformation Tokenize applique une expression régulière par rapport à la chaîne d’entrée.
title: Tokenize
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
exl-id: c1f39b5b-4717-44f6-99c7-4e6a215f3542
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 4%

---

# Tokenize{#tokenize}

{{eol}}

La transformation Tokenize applique une expression régulière par rapport à la chaîne d’entrée.

Cependant, contrairement à [!DNL RETransform], [!DNL Tokenize] ne doit pas nécessairement correspondre à la chaîne entière : l’expression régulière utilisée pour la variable [!DNL Tokenize] la transformation peut correspondre à un sous-ensemble de l’entrée. Une fois qu’une correspondance est trouvée, [!DNL Tokenize] applique à nouveau l’expression régulière, en commençant au caractère après la fin de la dernière correspondance.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Respect de la casse | True ou false. Indique si la correspondance est sensible à la casse. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Les conditions dans lesquelles cette transformation est appliquée. |  |
| Par défaut | La valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible ou que l’expression régulière ne correspond pas à la valeur d’entrée. |  |
| Expression | Expression régulière utilisée pour la correspondance. |  |
| Sorties | Les noms des chaînes de sortie. Vous pouvez avoir plusieurs sorties pour une chaîne d’entrée donnée. Le nombre de sorties doit correspondre au nombre de sous-modèles capturants dans l’expression régulière. |  |

Dans l’exemple suivant, la variable [!DNL Tokenize] transformation utilise une expression régulière pour capturer les noms des chaînes de requête (dans cs-uri-query) et générer le sous-modèle capturé (le nom de la requête) en x-pull-query-name.

![](assets/cfg_TransformationType_Tokenize.png)

Pour la chaîne de requête &quot;a=b&amp;c=d&quot;, la sortie serait un vecteur contenant &quot;a&quot; et &quot;c&quot;.

Pour plus d’informations sur les expressions régulières, voir [Expressions régulières](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
