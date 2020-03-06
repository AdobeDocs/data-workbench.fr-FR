---
description: La transformation Tokenize applique de manière itérative une expression régulière à la chaîne d’entrée.
solution: Analytics
title: Tokenize
topic: Data workbench
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tokenize{#tokenize}

La transformation Tokenize applique de manière itérative une expression régulière à la chaîne d’entrée.

Toutefois, contrairement à [!DNL RETransform], [!DNL Tokenize] ne doit pas nécessairement correspondre à la chaîne entière : l’expression régulière utilisée pour la [!DNL Tokenize] transformation peut correspondre à un sous-ensemble de l’entrée. Après avoir trouvé une correspondance, [!DNL Tokenize] applique de nouveau l’expression régulière, en commençant par le caractère après la fin de la dernière correspondance.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Respect de la casse | True ou false. Indique si la correspondance est sensible à la casse. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d’application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible ou que l’expression régulière ne correspond pas à la valeur d’entrée. |  |
| Expression | Expression régulière utilisée pour la correspondance. |  |
| Sorties | Noms des chaînes de sortie. Vous pouvez avoir plusieurs sorties pour une chaîne d’entrée donnée. Le nombre de sorties doit correspondre au nombre de sous-modèles capturés dans l’expression régulière. |  |

Dans l’exemple suivant, la [!DNL Tokenize] transformation utilise une expression régulière pour capturer les noms des chaînes de requête (dans cs-uri-query) et générer le sous-modèle capturé (le nom de la requête) en x-pull-query-name.

![](assets/cfg_TransformationType_Tokenize.png)

Pour la chaîne de requête &quot;a=b&amp;c=d&quot;, la sortie serait un vecteur contenant &quot;a&quot; et &quot;c&quot;.

Pour plus d’informations sur les expressions régulières, voir Expressions [régulières](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
