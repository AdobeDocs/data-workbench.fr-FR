---
description: Le serveur Insight vous permet de définir des dimensions dénombrables, simples, de type "plusieurs à plusieurs", numériques, dénormalisées et temporelles à inclure dans votre jeu de données.
solution: Analytics
title: Types de dimensions étendues
topic: Data workbench
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Types de dimensions étendues{#types-of-extended-dimensions}

Le serveur Insight vous permet de définir des dimensions dénombrables, simples, de type &quot;plusieurs à plusieurs&quot;, numériques, dénormalisées et temporelles à inclure dans votre jeu de données.

Chaque type de dimension comporte un ensemble de paramètres dont vous modifiez les valeurs afin de fournir des instructions spécifiques au serveur Insight pour la création des dimensions pendant la phase de transformation de la construction du jeu de données.

Bien que certains des paramètres diffèrent entre les types de dimension, ils nécessitent tous la spécification d’une dimension parent (le paramètre parent). La dimension parente détermine les entrées de journal provenant des sources de journal qui sont fournies en entrée à la nouvelle dimension. En d’autres termes, les entrées de journal associées aux éléments de la dimension parent sont celles qui sont associées à la nouvelle dimension avant l’application d’un filtrage. La dimension parente détermine également la position de la nouvelle dimension dans la hiérarchie du jeu de données, appelée schéma du jeu de données. Pour plus d’informations sur l’interface qui affiche le schéma du jeu de données, voir Outils [de configuration des jeux de](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)données.

Une fois que le serveur Insight utilise la dimension parent pour déterminer les entrées de journal à prendre en compte lors de la création de la dimension, il applique la ou les conditions spécifiées (le paramètre Condition) pour vider les entrées de journal qui ne respectent pas la condition. Le serveur identifie ensuite la valeur du champ d’entrée spécifié (le paramètre Input) pour chaque entrée du journal et applique l’opération spécifiée (le paramètre Operation), le cas échéant.

>[!NOTE]
>
>Si une entrée de journal ne satisfait pas la condition d’une dimension étendue, le serveur Insight remplace les valeurs vides pour tous les champs de l’entrée de journal. L’entrée de journal réelle existe toujours et l’opération spécifiée détermine si la valeur vide du [!DNL Input] champ est utilisée.

