---
description: Le serveur Insight vous permet de définir des dimensions dénombrables, simples, de type "plusieurs à plusieurs", numériques, dénormalisées et temporelles à inclure dans votre jeu de données.
title: Types de dimensions étendues
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
exl-id: 13a52ece-b68b-45bc-ac2d-d68c91742c9d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 2%

---

# Types de dimensions étendues{#types-of-extended-dimensions}

Le serveur Insight vous permet de définir des dimensions dénombrables, simples, de type &quot;plusieurs à plusieurs&quot;, numériques, dénormalisées et temporelles à inclure dans votre jeu de données.

Chaque type de dimension comporte un ensemble de paramètres dont vous modifiez les valeurs afin de fournir des instructions spécifiques au serveur Insight pour créer les dimensions pendant la phase de transformation de la construction du jeu de données.

Bien que certains paramètres diffèrent entre les types de dimension, tous nécessitent la spécification d’une dimension parent (le paramètre Parent). La dimension parente détermine les entrées de journal provenant des sources de journal fournies en tant qu’entrée à la nouvelle dimension. En d’autres termes, les entrées de journal associées aux éléments de la dimension parent sont celles associées à la nouvelle dimension avant toute application de filtrage. La dimension parente détermine également la position de la nouvelle dimension dans la hiérarchie du jeu de données, appelée schéma du jeu de données. Pour plus d’informations sur l’interface qui affiche le schéma du jeu de données, voir [Outils de configuration du jeu de données](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

Une fois que le serveur Insight utilise la dimension parente pour déterminer les entrées de journal à prendre en compte dans la création de la dimension, il applique la ou les conditions spécifiées (le paramètre de condition) pour vider les entrées de journal qui ne respectent pas la condition. Le serveur identifie ensuite la valeur du champ d’entrée spécifié (le paramètre Input ) pour chaque entrée de journal et applique l’opération spécifiée (le paramètre Operation ), le cas échéant.

>[!NOTE]
>
>Si une entrée de journal ne satisfait pas la condition d’une dimension étendue, le serveur Insight remplace les valeurs vides de tous les champs de l’entrée de journal. L’entrée réelle du journal existe toujours et l’opération spécifiée détermine si la valeur vide du champ [!DNL Input] est utilisée.
