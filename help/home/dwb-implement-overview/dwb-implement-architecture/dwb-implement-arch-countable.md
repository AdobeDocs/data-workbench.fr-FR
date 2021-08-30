---
description: Explication des tables dans Data Workbench (DWB) pour la conception et l’implémentation du schéma.
title: Structures comptables de conception de schéma
uuid: 2530980d-1c6b-4a96-b9c1-431fc75678bb
exl-id: 4f2a2f8a-7b42-42bb-8ba1-2675ffe6b2c2
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 3%

---

# Structures comptables de conception de schéma{#schema-design-countable-structures}

Explication des tables dans Data Workbench (DWB) pour la conception et l’implémentation du schéma.

## Présentation de la dénombrable dans Data Workbench {#section-6e6b8d1c17634d669e62c91a80a0bc62}

Les dimensions dénombrables se trouvent au niveau supérieur. Les dimensions dénombrables remplissent deux fonctions principales. Tout d’abord, il s’agit de dimensions dont vous souhaitez compter les éléments. En d’autres termes, les compteurs répondent aux questions suivantes :

* Combien de visiteurs ont visité votre page d’accueil ?

* Combien de visites sont venues de Google.com ?

`<discoiqbr>`Les dimensions dénombrables sont généralement utilisées pour créer des mesures de somme, qui renvoient le nombre, ou la somme, de tous les éléments de la dimension. Vous pouvez définir des dimensions dénombrables pour comptabiliser des instances telles que les réservations ou les commandes de produits. Par exemple, vous pouvez définir les commandes de dimension dénombrables dont les éléments (entrées de journal correspondant aux commandes de votre boutique en ligne) peuvent être comptabilisés. Si vous souhaitez afficher un nombre de commandes dans une visualisation, vous pouvez définir la mesure de somme des commandes, qui peut être évaluée sur une dimension ou pour laquelle des filtres sont appliqués.

Les dimensions dénombrables peuvent entretenir des relations de type parents/enfants.

Bien que la dimension dénombrable racine n’ait pas à être associée aux ID de suivi dans les données, Adobe vous recommande de configurer la dimension dénombrable racine du jeu de données afin d’utiliser le champ ID de suivi (x-trackingid) comme clé. Par conséquent, chaque élément du dénombrable racine est associé à une valeur unique de x-trackingid, et toutes les données de chaque élément sont regroupées.

Les dimensions dénombrables sont définies par les paramètres suivants :

<table id="table_5E00B72CFDD645368ADCC25AB9B5E53D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Par défaut </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> Nom descriptif de la dimension tel qu’il apparaît à l’utilisateur dans Data Workbench. Le nom de la dimension ne peut pas contenir de trait d’union (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Commentaires </p> </td> 
   <td colname="col2"> <p>Facultatif. Remarques sur la dimension étendue.

    &lt;/p> &lt;/td>
<td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Condition </p> </td> 
   <td colname="col2"> <p>Les conditions dans lesquelles le champ de saisie contribue à la création de la dimension dénombrable. Si elle est spécifiée, une condition limite l’ensemble des entrées de journal visibles pour la dimension et tous ses enfants dans le schéma du jeu de données. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Masqué </td> 
   <td colname="col2"> Détermine si la dimension apparaît dans l’interface de Data Workbench. Par défaut, ce paramètre est défini sur false. Si, par exemple, la dimension doit être utilisée uniquement comme base d’une mesure, vous pouvez définir ce paramètre sur true pour masquer la dimension de l’affichage Data Workbench. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clé </td> 
   <td colname="col2"> <p>Facultatif. Nom du champ à utiliser comme clé. Si vous définissez ce paramètre, il existe un élément de la dimension dénombrable pour chaque combinaison d’un élément du parent de la dimension dénombrable et une valeur distincte du champ spécifié comme clé. </p> <p>Chaque élément de la dimension dénombrable doit être associé à un ensemble contigu d’entrées de journal. Par conséquent, si les entrées du journal ne sont pas triées par la clé, un élément de la dimension dénombrable est créé chaque fois que le champ clé change. Pour éviter cette situation, Adobe vous recommande d’utiliser une clé unique contiguë dans l’ordre du temps. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> <p> Nom de la dimension parent. Toute dimension dénombrable peut être une dimension parente. Pour faire d’une dimension la dimension de niveau supérieur dans le schéma du jeu de données, définissez le paramètre sur "root". La dimension définie devient la dimension dénombrable racine du jeu de données. Par exemple, si vous utilisez Site, la dimension Visiteur est la dimension dénombrable racine de votre jeu de données. </p> <p>Remarque : Bien que la dimension dénombrable racine n’ait pas à être associée aux ID de suivi dans les données, Adobe vous recommande de configurer la dimension dénombrable racine du jeu de données afin d’utiliser le champ ID de suivi (x-trackingid) comme clé. Par conséquent, chaque élément du dénombrable racine est associé à une valeur unique de x-trackingid, et toutes les données de chaque élément sont regroupées. Si vous souhaitez configurer votre jeu de données différemment, contactez Adobe. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Cet exemple illustre la définition d’une dimension dénombrable à l’aide des données d’événement collectées à partir du trafic du site web. La dimension dénombrable comptabilise les événements de campagne web au cours d’une session donnée. Il est supposé que toutes les ressources de campagne par e-mail sont demandées au serveur web avec &quot;email=&quot; dans le cadre de la requête cs-uri. Dans cet exemple, le nombre de fois où le visiteur répond à une campagne par courrier électronique au cours d’une session donnée est intéressant, et non la valeur réelle du champ cs-uri-query(email) .

![](assets/dwb_impl_arch_1.png)

La deuxième fonction principale des compteurs est qu’ils forment la colonne vertébrale de la structure de votre schéma de jeu de données. Votre schéma de données et toutes les autres dimensions sont organisés pour être regroupés sous et appartenir à un dénombrable. En d’autres termes, si nous considérons les dimensions comme des &quot;catégories&quot;, les compteurs sont la manière dont nous organisons ces &quot;catégories&quot; en groupes.
Lorsque des dimensions sont regroupées sous une dimension dénombrable, elles sont dites se trouver au &quot;niveau&quot; de la dimension dénombrable. Par exemple, dans la figure ci-dessous, vous pouvez constater que &quot;Adresse électronique&quot; se trouve au niveau du visiteur et que &quot;Navigateur&quot; se trouve au niveau de la visite. &quot;Parent&quot; et &quot;enfant&quot; se rapportent à la relation entre le dénombrable et les dimensions regroupées sous celui-ci. Par exemple, Visiteur est un &quot;parent&quot; de l’adresse électronique. Inversement, l’adresse électronique est un &quot;enfant&quot; du visiteur. ![](assets/dwb_impl_arch_2.png) ![](assets/dwb_impl_arch_3.png)

## Création dénombrable dans Data Workbench {#section-491f3e8e4fbc429e95d6c97f012a208e}

Effectuez les étapes suivantes pour créer le dénombrable dans Data Workbench :

1. Ouvrir Profile Manager
1. Sous le dossier Transformation , créez un fichier de configuration et ouvrez-le dans le poste de travail.
1. Sous Dimensions étendues, cliquez avec le bouton droit de la souris et choisissez Ajouter nouveau -> Comptable comme illustré ci-dessous : ![](assets/dwb_impl_arch_4.png)

1. Saisissez le nom du nouveau dénombrable. Dans l’exemple ci-dessous, le compte à rebours du client est défini. S’il s’agit du niveau le plus élevé dénombrable, alors dans la racine d’écriture parente. ![](assets/dwb_impl_arch_5.png)

   Si le décompte n’est pas le niveau supérieur, dans le champ parent, indiquez le nom du décompte parent. Dans l’exemple ci-dessous, Engagement Countable est créé et le Parent de ce dénombrable est Client. ![](assets/dwb_impl_arch_5.png)

Pour plus d’informations sur l’architecture du Data Workbench pour la conception de schémas, les structures dénombrables et les configurations de flux de données hors ligne, voir [Interface du schéma du jeu de données](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-dtst-sch-intrf.html).
