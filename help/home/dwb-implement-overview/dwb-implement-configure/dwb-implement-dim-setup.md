---
description: Cette section explique les différents types de Dimensions et comment les configurer dans DWB.
title: Configuration des dimensions
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
exl-id: 04afd773-e938-49f7-83c9-1d706a6dc525
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 4%

---

# Configuration des dimensions{#dimension-setup}

{{eol}}

Cette section explique les différents types de Dimensions et comment les configurer dans DWB.

## Que sont les Dimensions {#section-dac631943df24706827cedc6f0641543}

Au niveau le plus élémentaire, les dimensions sont des catégories dans lesquelles les données du jeu de données peuvent être ventilées.

Bonne pratique : Vous pouvez attribuer n’importe quel nom aux Dimensions du schéma de données. Les noms de Dimensions utilisés et expliqués dans ce cours sont considérés comme une bonne pratique. Les Dimensions peuvent être nommées différemment. À mesure que vous vous familiarisez avec d’autres jeux de données, vous commencez à voir des différences dans les jeux de données. Il est important de comprendre l’objectif des dimensions plutôt que leur nom. Par exemple, qu’il s’agisse de &quot;Visiteur&quot;, &quot;Client&quot;, &quot;Personne&quot;, &quot;Consommateur&quot; ou &quot;Utilisateur&quot;, il est important de comprendre qu’il s’agit de termes couramment utilisés pour faire référence à la dimension dénombrable de niveau supérieur utilisée pour recueillir des informations sur une personne unique.

Pour plus d’informations, voir [Configuration des jeux de données](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/c-dataset-constr.html) guide.

## Types de Dimensions dans DWB {#section-a4fbb7bf2bde44528ac0f94a96465862}

Il existe deux types de dimensions en Data Workbench : Dimensions étendues et Dimensions dérivées.

Les Dimensions étendues sont créées à partir des champs des fichiers de données &quot;brutes&quot;. Les dimensions étendues sont utilisées pour catégoriser les données &quot;brutes&quot; et spécifier les relations qui existent entre les données. Les dimensions étendues sont créées par les architectes Data Workbench.

Les Dimensions dérivées sont créées par un utilisateur &quot;côté client&quot; après le traitement du jeu de données à l’aide de définitions de dimension étendues existantes. Par exemple, en fonction de la dimension URI existante, un utilisateur peut choisir de créer une dimension Nom de page dérivé, qui affiche un nom de page plus convivial au lieu d’un URI donné. Toutes les dimensions se composent d’éléments ou d’éléments qui ont été catégorisés (regroupés) pour former la dimension. Vous trouverez ci-dessous trois dimensions et leurs éléments.

Bon nombre de dimensions dérivées sont créées automatiquement afin de générer différents types de visualisations. Par exemple, lorsqu’un utilisateur crée un site ou une cartographie des processus, les serveurs DWB créent une dimension de préfixe. D’autres dimensions (c’est le cas, par exemple, des dimensions temporelles de création de rapports) sont définies par des fichiers dans le répertoire Dimensions d’un profil.

>[!NOTE]
>
>Les éléments apparaissant dans une dimension donnée ne reflètent que les valeurs qui existent dans les enregistrements choisis pour être chargés dans le jeu de données. Par exemple, s’il n’existe aucune donnée pour &quot;12 mai&quot;, ce mois n’apparaîtra pas dans la dimension &quot;Mois&quot;.

## Dimensions étendues {#section-5fc51fa539034941a30a2df606f7d727}

Types de dimensions étendues

**1) Dimensions dénombrables**

Les dimensions dénombrables se trouvent au niveau supérieur. Les dimensions dénombrables remplissent deux fonctions principales. Tout d’abord, il s’agit de dimensions dont vous souhaitez compter les éléments. En d’autres termes, les compteurs répondent aux questions suivantes :

* &quot;Combien de visiteurs ont visité votre page d’accueil ?&quot;
* &quot;Combien de visites sont venues de google.com ?&quot;

C’est pourquoi les compteurs sont souvent utilisés comme élément de base de la création de mesures.

La deuxième fonction principale des compteurs est qu’ils forment la colonne vertébrale de la structure de votre schéma de jeu de données. Votre schéma de données et toutes les autres dimensions sont organisés pour être regroupés sous et appartenir à un dénombrable. En d’autres termes, si nous considérons les dimensions comme des &quot;catégories&quot;, les compteurs sont la manière dont nous organisons ces &quot;catégories&quot; en groupes.

Lorsque des dimensions sont regroupées sous une dimension dénombrable, elles sont dites se trouver au &quot;niveau&quot; de la dimension dénombrable. Par exemple, &quot;Adresse électronique&quot; peut se trouver au niveau du visiteur et &quot;Navigateur&quot; au niveau de la visite. &quot;Parent&quot; et &quot;enfant&quot; se rapportent à la relation entre le dénombrable et les dimensions regroupées sous celui-ci. Par exemple, Visiteur est un &quot;parent&quot; de l’adresse électronique. Inversement, l’adresse électronique est un &quot;enfant&quot; du visiteur.

**2) Dimensions simples**

Les dimensions les plus courantes de toutes sont les dimensions simples. Les dimensions simples ont une relation de type &quot;un à plusieurs&quot; avec une dimension dénombrable parent et sont généralement utilisées dans les visualisations afin que vous puissiez afficher leurs éléments. Cela signifie qu’une dimension dénombrable peut avoir une valeur pour une dimension simple, mais que la dimension simple peut appartenir à un ou plusieurs décomptes. Par exemple, un client porte le nom &quot;John&quot; : ce client ne peut avoir qu’un seul prénom, mais de nombreux autres clients peuvent avoir le nom &quot;John;&quot;. Autre exemple : un seul navigateur (Firefox, par exemple) peut être utilisé pour n’importe quelle visite particulière sur un site web, mais ce navigateur peut être utilisé pour de nombreuses visites différentes.

Si les dimensions dénombrables répondent &quot;Combien ?&quot;, alors les dimensions simples répondent &quot;lesquelles ?&quot;. En suivant le même exemple que celui utilisé dans la section Dimension dénombrable ; Nom de page est la dimension simple. En utilisant le tableau et la dimension simple Nom de page, nous pouvons répondre à des questions telles que :

* &quot;Quelle page a enregistré le plus de pages vues ?&quot;
* &quot;De toutes les pages du panier, laquelle a eu le plus de visites ?&quot;

**3) Dimensions multiples-à-multiples**

Plusieurs à plusieurs dimensions ont une relation de type &quot;plusieurs à plusieurs&quot; avec une dimension dénombrable parent. Par exemple, si une dimension nommée Terme de recherche externe se trouve au niveau Visite ; un terme de recherche externe donné peut être utilisé dans une ou plusieurs visites et une visite donnée peut inclure un ou plusieurs termes de recherche externe. Par conséquent, le terme de recherche externe est une dimension &quot;plusieurs à plusieurs&quot;.

**4) Dimensions numériques**

Les dimensions numériques sont un type de dimension simple qui possède une valeur numérique. Les dimensions numériques sont souvent créées pour être utilisées dans les mesures. Parmi les exemples de dimensions numériques, citons &quot;Recettes&quot;, &quot;Commandes&quot; et &quot;Unités&quot;. Dans l’exemple ci-dessus, la dimension &quot;Commandes du client&quot; est une dimension numérique.
**5) Dimensions non normalisées** Les dimensions non normalisées sont des dimensions qui ont une relation un-à-un avec une dimension dénombrable parent. Les dimensions Denormal sont souvent utilisées avec des dimensions présentant une cardinalité élevée (de nombreux éléments uniques), comme les données d’identification. Par exemple, un visiteur ne peut avoir qu’un seul ID utilisateur et un ID utilisateur ne peut appartenir qu’à un seul visiteur. Il s&#39;agit donc d&#39;une relation de type &quot;un à un&quot; qui peut être une dimension dénormalisée.

Par exemple, l’identifiant utilisateur web Geometrixx est une dimension Denormal au niveau du client. Puisqu’il est dénormalisé, il entretient une relation de type &quot;un à un&quot; avec sa dimension parent, ce qui signifie que chaque ID d’utilisateur web comporte un client et que chaque client n’a qu’un seul ID d’utilisateur web. Par conséquent, la mesure &quot;Clients&quot; ne peut être que &quot;1&quot; pour chaque élément de l’identifiant utilisateur web Geometrixx.

**6) Dimensions temporelles**

Les dimensions temporelles vous permettent de créer un ensemble de dimensions temporelles locales absolues ou périodiques en fonction du champ d’horodatage que vous spécifiez. Parmi les exemples de dimensions temporelles, citons &quot;Jour&quot;, &quot;Heure&quot;, &quot;Semaine&quot; et &quot;Heure du jour&quot;. Dans l’exemple ci-dessus, le tableau &quot;Heure de la journée&quot; indique le nombre de visites et de pages vues reçues au cours des différentes heures de la journée.

>[!NOTE]
>
>Les échappement en % utilisés pour la mise en forme d’affichage sont identiques à la bibliothèque C standard. *strftime*.

## Définition des dimensions étendues {#section-38ee124ec74b43fb95f13194a9582b97}

Étapes pour définir la Dimension étendue :

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez le gestionnaire de profils et cliquez sur Jeu de données pour en afficher le contenu.
1. Ouvrez le fichier Transformation.cfg ou le fichier d’inclusion de jeux de données de transformation dans lequel vous souhaitez définir la dimension étendue.
1. Cliquez avec le bouton droit de la souris sur Transformations et cliquez sur Ajouter > `<Extended dimension type>`.
1. Saisissez les informations appropriées pour votre dimension étendue. Pour obtenir des descriptions des types de transformation et des informations sur leurs paramètres, reportez-vous aux sections suivantes :

   * [Dimensions dénombrables](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [Dimensions simples](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [Dimensions multiples-à-multiples](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [Dimensions numériques](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [Dimensions non normalisées](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [Dimensions Heure](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. Pour toute dimension étendue que vous définissez, vous pouvez ajouter une ou plusieurs lignes de commentaire au paramètre Commentaires afin de décrire plus en détail la dimension ou ajouter des notes sur son utilisation. Pour ajouter un commentaire, cliquez avec le bouton droit de la souris sur le *Commentaires* et cliquez sur* Ajouter > Ligne de commentaire*.

1. Après avoir défini votre ou vos dimensions étendues dans le fichier de configuration, enregistrez le fichier localement et enregistrez-le dans votre profil de jeu de données sur le serveur DWB.

## Masquage des dimensions étendues {#section-02339fb51658418eabc10186cd5957d7}

Les Dimensions étendues peuvent être masquées afin qu’elles ne s’affichent pas dans le menu Dimension de la base de données. Pour masquer la dimension, définissez la propriété Masqué sur &quot;True&quot; dans la définition de dimension.
