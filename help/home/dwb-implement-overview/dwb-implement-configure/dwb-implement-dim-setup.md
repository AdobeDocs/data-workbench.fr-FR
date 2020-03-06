---
description: Cette section explique les différents types de dimensions et comment les configurer dans DWB.
title: Configuration des dimensions
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Configuration des dimensions{#dimension-setup}

Cette section explique les différents types de dimensions et comment les configurer dans DWB.

## Que sont les dimensions ? {#section-dac631943df24706827cedc6f0641543}

Au niveau le plus élémentaire, les dimensions sont des catégories dans lesquelles les données du jeu de données peuvent être ventilées.

Meilleure pratique : Vous pouvez attribuer n’importe quel nom aux dimensions du schéma de données. Les noms de dimension utilisés et expliqués dans ce cours sont considérés comme une bonne pratique. Les dimensions peuvent être nommées différemment. Au fur et à mesure que vous vous exposerez à d’autres jeux de données, vous constaterez des différences entre les jeux de données. Il est important de comprendre l&#39;objectif des dimensions plutôt que leur nom. Par exemple, qu’il s’agisse de &quot;Visiteur&quot;, &quot;Client&quot;, &quot;Personne&quot;, &quot;Consommateur&quot; ou &quot;Utilisateur&quot;, il est important de comprendre qu’il s’agit de termes couramment utilisés pour faire référence à la dimension dénombrable de niveau supérieur utilisée pour recueillir des informations sur une personne particulière.

Pour obtenir des informations complètes, reportez-vous au guide Configuration [des jeux de](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html) données.

## Types de dimensions dans DWB {#section-a4fbb7bf2bde44528ac0f94a96465862}

Il existe deux types de dimensions dans les Outils de données : Dimensions étendues et Dimensions dérivées.

Les dimensions étendues sont créées à partir des champs des fichiers de données &quot;brutes&quot;. Les dimensions étendues sont utilisées pour classer les données &quot;brutes&quot; et spécifier les relations qui existent entre les données. Les dimensions étendues sont créées par Data Workbench Architects.

Les dimensions dérivées sont créées par un utilisateur &quot;côté client&quot; après le traitement du jeu de données à l’aide des définitions de dimension étendue existantes. Par exemple, en fonction de la dimension URI existante, un utilisateur peut choisir de créer une dimension Nom de page dérivée, qui affiche un nom de page plus convivial à la place d’un URI donné. Toutes les dimensions se composent d’éléments ou d’éléments qui ont été classés (regroupés) ensemble pour former la dimension. Vous trouverez ci-dessous trois dimensions et leurs éléments.

Bon nombre de dimensions dérivées sont créées automatiquement afin de générer différents types de visualisations. Par exemple, lorsqu’un utilisateur construit un site ou une carte de processus, les serveurs DWB créent une dimension de préfixe. D’autres dimensions (c’est le cas, par exemple, des dimensions temporelles de création de rapports) sont définies par des fichiers dans le répertoire Dimensions d’un profil.

>[!NOTE]
>
>Les éléments apparaissant dans une dimension donnée ne reflètent que les valeurs qui existent dans les enregistrements choisis pour être chargés dans le jeu de données. Par exemple, s’il n’existe aucune donnée pour &quot;Mai &#39;12&quot;, ce mois n’apparaîtra pas dans la dimension &quot;Mois&quot;.

## Extended Dimensions {#section-5fc51fa539034941a30a2df606f7d727}

Types de dimensions étendues

**1) Dimensions dénombrables**

Au niveau le plus élevé sont les dimensions dénombrables. Les dimensions dénombrables remplissent deux fonctions principales. Tout d’abord, ce sont des dimensions dont vous voulez compter les éléments. En d’autres termes, les compteurs répondent aux questions suivantes :

* &quot;Combien de visiteurs ont visité votre page d&#39;accueil ?&quot;
* &quot;Combien de visites sont venues de google.com ?&quot;

C’est pourquoi les comptes sont souvent utilisés comme élément de base fondamental pour créer des mesures.

La deuxième fonction principale des compteurs est qu’ils forment la colonne vertébrale de la structure de schéma de votre jeu de données. Votre schéma de données et toutes les autres dimensions sont organisés pour être regroupés sous et appartenir à un dénombrable. En d’autres termes, si nous considérons les dimensions comme des &quot;catégories&quot;, alors les décomptes sont la façon dont nous organisons ces &quot;catégories&quot; en groupes.

Lorsque les dimensions sont regroupées sous une dimension dénombrable, elles se situent, dit-on, au &quot;niveau&quot; de la dimension dénombrable. Par exemple, &quot;Adresse électronique&quot; peut se trouver au niveau du visiteur et &quot;Navigateur&quot; au niveau de la visite. &quot;Parent&quot; et &quot;enfant&quot; désignent la relation entre le dénombrable et les dimensions regroupées en dessous. Par exemple, Visiteur est un &quot;parent&quot; de l’adresse électronique. Inversement, l’adresse électronique est un &quot;enfant&quot; du visiteur.

**2) Dimensions simples**

Les dimensions les plus courantes sont les dimensions simples. Les dimensions simples ont une relation de type &quot;un à plusieurs&quot; avec une dimension dénombrable parent et sont généralement utilisées dans les visualisations afin que vous puissiez afficher leurs éléments. Cela signifie qu’une dimension dénombrable peut avoir une valeur pour une dimension simple, mais que la dimension simple peut appartenir à un ou plusieurs décomptes. Par exemple, un client a le nom &quot;John&quot; : ce client ne peut avoir qu’un prénom, mais de nombreux autres clients peuvent avoir le nom &quot;John;&quot;. Comme autre exemple, seul un navigateur (Firefox, par exemple) peut être utilisé pour une visite d&#39;un site Web particulier, mais ce navigateur peut être utilisé pour de nombreuses visites différentes.

Si les dimensions dénombrables répondent &quot;Combien ?&quot;, les dimensions simples répondent &quot;Lesquelles ?&quot;. En utilisant le même exemple que celui utilisé dans la section de dimension dénombrable ; Nom de page est la dimension simple. En utilisant le tableau et la dimension simple, Nom de page, nous pouvons répondre à des questions telles que :

* &quot;Quelle page a généré le plus de pages vues ?&quot;
* &quot;De toutes les pages du panier, laquelle a le plus visité ?&quot;

**3) Dimensions multiples à multiples**

Plusieurs à plusieurs dimensions ont une relation de plusieurs à plusieurs avec une dimension dénombrable parent. Par exemple, si une dimension nommée Terme de recherche externe se trouve au niveau Visite ; un terme de recherche externe donné peut être utilisé dans une ou plusieurs visites et une visite donnée peut inclure un ou plusieurs termes de recherche externe. Par conséquent, le terme de recherche externe est une dimension de type &quot;plusieurs à plusieurs&quot;.

**4) Dimensions numériques**

Les dimensions numériques sont un type de dimension simple avec une valeur numérique. Les dimensions numériques sont souvent créées pour être utilisées dans les mesures. Parmi les exemples de dimensions numériques, citons &quot;Recettes&quot;, &quot;Commandes&quot; et &quot;Unités&quot;. Dans l’exemple ci-dessus, les &quot;Commandes client&quot; sont une dimension numérique.
**5) Dimensions** Denormal Les dimensions Denormal sont des dimensions qui ont une relation un-à-un avec une dimension dénombrable parent. Les dimensions Denormal sont souvent utilisées avec des dimensions qui présentent une grande cardinalité (de nombreux éléments uniques), comme les données d’identification. Par exemple, un visiteur ne peut avoir qu’un seul ID utilisateur et un seul ID utilisateur peut appartenir à un seul visiteur. Il s&#39;agit donc d&#39;une relation de type &quot;un à un&quot; et peut être une dimension Denormal.

Par exemple, l’ID utilisateur Web de Geometrixx est une dimension Denormal au niveau du client. Puisqu’il est dénormalisé, il entretient une relation de type &quot;un à un&quot; avec sa dimension parent, ce qui signifie que chaque ID d’utilisateur Web a un client et que chaque client n’a qu’un seul ID d’utilisateur Web. Ainsi, la mesure &quot;Clients&quot; ne peut être que &quot;1&quot; pour chaque élément de l’ID utilisateur Web Geometrixx.

**6) Dimensions temporelles**

Les dimensions d’heure vous permettent de créer un ensemble de dimensions d’heure locale périodiques ou absolues en fonction du champ d’horodatage que vous spécifiez. Parmi les exemples de dimensions temporelles, citons &quot;Jour&quot;, &quot;Heure&quot;, &quot;Semaine&quot; et &quot;Heure du jour&quot;. Dans l’exemple ci-dessus, le tableau &quot;Heure du jour&quot; montre le nombre de visites et de pages vues reçues au cours des différentes heures du jour.

>[!NOTE]
>
>Les % d’échappement utilisés pour le formatage de l’affichage sont identiques à ceux de la bibliothèque C standard *strftime*.

## Définition de dimensions étendues {#section-38ee124ec74b43fb95f13194a9582b97}

Etapes de définition de la dimension étendue :

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez le Gestionnaire de profils et cliquez sur Jeu de données pour en afficher le contenu.
1. Ouvrez le fichier Transformation.cfg ou le fichier Transformation Dataset Include dans lequel vous souhaitez définir la dimension étendue.
1. Cliquez avec le bouton droit de la souris sur Transformations, puis cliquez sur Ajouter > `<Extended dimension type>`.
1. Saisissez les informations appropriées pour votre dimension étendue. Pour obtenir des descriptions des types de transformation et des informations sur leurs paramètres, consultez les sections suivantes :

   * [Dimensions dénombrables](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [Dimensions simples](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [Dimensions multiples](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [Dimensions numériques](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [Dimensions Denormal](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [Dimensions Heure](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. Pour toute dimension étendue que vous définissez, vous pouvez ajouter une ou plusieurs lignes de commentaire au paramètre Commentaires afin de décrire plus en détail la dimension ou d’ajouter des remarques sur son utilisation. Pour ajouter un commentaire, cliquez avec le bouton droit de la souris sur le libellé *Commentaires* et cliquez sur* Ajouter un nouveau > Ligne de commentaire*.

1. Après avoir défini vos dimensions étendues dans le fichier de configuration, enregistrez le fichier localement et enregistrez-le dans votre profil de jeu de données sur le serveur DWB.

## Masquage des dimensions étendues {#section-02339fb51658418eabc10186cd5957d7}

Les dimensions étendues peuvent être masquées afin qu’elles ne s’affichent pas dans le menu Dimension du DWB. Pour masquer la dimension, définissez la propriété Masqué sur &quot;True&quot; dans la définition de la dimension.
