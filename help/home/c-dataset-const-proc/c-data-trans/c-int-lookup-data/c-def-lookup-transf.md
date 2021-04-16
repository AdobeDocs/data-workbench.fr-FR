---
description: Informations sur les transformations que vous pouvez utiliser pour incorporer des données de recherche dans le jeu de données.
title: Définition des transformations Lookup
uuid: 4f7358b1-9e6a-4d03-b0c6-411e454fc11e
exl-id: 7b1504be-8669-4340-8400-e33f9663b602
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2288'
ht-degree: 3%

---

# Définition des transformations Lookup{#defining-lookup-transformations}

Informations sur les transformations que vous pouvez utiliser pour incorporer des données de recherche dans le jeu de données.

Notez que tous les types ne peuvent pas être utilisés pendant les deux phases du processus de construction du jeu de données.

* [Catégoriser](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-8474376c14e54d14ae73749696ada468)
* [FlatFileLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-e09b2eeb96444a859b14f03cdaab31f2)
* [ODBCLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-4dcc3747e42e45c0a057e85f308a83cc)

## Catégoriser {#section-8474376c14e54d14ae73749696ada468}

La transformation [!DNL Categorize] utilise une table de recherche à deux colonnes composée de paires modèle-chaîne/valeur. Au cours de cette transformation, le serveur de l’outil de données lit à son tour chaque enregistrement de données de événement et compare le contenu d’un champ désigné dans l’enregistrement à chacune des chaînes de modèle répertoriées dans la première colonne de la table de choix. Si le champ désigné correspond à l’une des chaînes de modèle, le serveur de l’outil de données écrit la valeur (figurant dans la deuxième colonne) associée à cette chaîne de modèle dans un champ de sortie désigné de l’enregistrement.

Les chaînes de la première colonne de la table de choix peuvent éventuellement s’début avec le caractère ^ et/ou se terminer dans le caractère $ pour forcer la correspondance au début et/ou à la fin. Cette transformation n’accepte pas les expressions régulières pour définir les conditions de correspondance dans la première colonne. Si la valeur d’entrée est un vecteur de chaînes, chaque chaîne est exécutée dans la transformation et le ou les résultats sont ajoutés à un vecteur de chaîne de sortie.

Une transformation [!DNL Categorize] est généralement plus facile et plus rapide que l&#39;utilisation d&#39;une transformation [!DNL Regular Expression] pour accomplir la même chose.

>[!NOTE]
>
>Le test de sous-chaîne utilisé dans [!DNL Categorize] est sensible à la casse, sauf indication contraire à l&#39;aide du paramètre [!DNL Case Sensitive].

<table id="table_1773344FAAE34BD4919CC4414249FDEE"> 
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
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez entrer n'importe quel nom ici. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Respect de la casse </td> 
   <td colname="col2"> Vrai ou faux. Indique si le test de sous-chaîne est sensible à la casse. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions d'application de cette transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Par défaut </td> 
   <td colname="col2"> Valeur par défaut à utiliser si le test de condition réussit et qu’aucune entrée dans le fichier de catégorisation ne correspond à l’entrée ou si le champ d’entrée n’est pas défini dans l’entrée de journal donnée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Délimiteur </td> 
   <td colname="col2"> <p>Chaîne utilisée pour séparer les colonnes dans le fichier de recherche. Doit être un caractère de longueur unique. </p> <p> Si vous maintenez la touche Ctrl enfoncée et cliquez avec le bouton droit dans le paramètre Délimiteur, un menu <span class="wintitle"> Insérer</span> s'affiche. Ce menu contient une liste de caractères spéciaux qui sont souvent utilisés comme délimiteurs. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeurs multiples </td> 
   <td colname="col2"> Vrai ou faux. Si la valeur est true, lorsque plusieurs lignes du fichier correspondent à l’entrée, chaque correspondance entraîne l’ajout d’une valeur au vecteur de sortie des chaînes. Si la valeur est false, seule la première ligne correspondante du fichier est utilisée dans la sortie. Dans ce dernier cas, si l’entrée est un vecteur, la sortie est également un vecteur de longueur équivalente. Si l’entrée est une chaîne simple, la sortie est également une chaîne simple. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier </td> 
   <td colname="col2"> Chemin d’accès et nom de fichier du fichier de catégorisation. Les chemins relatifs concernent le répertoire d’installation du serveur de l’outil de données. Ce fichier se trouve généralement dans le répertoire Lookups du répertoire d’installation du serveur de l’outil de données. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> Le fichier de catégorisation compare ses sous-chaînes à la valeur de ce champ pour identifier la ligne correspondante dans le fichier. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sortie </td> 
   <td colname="col2"> Nom du champ associé au résultat. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Considérations relatives à la catégorisation**

* Les modifications apportées aux fichiers de recherche dans les transformations [!DNL Categorize] définies dans le fichier [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include] nécessitent une retransformation du jeu de données. Les fichiers de recherche pour les transformations [!DNL Categorize] définies dans le fichier [!DNL Log Processing.cfg] ou un fichier [!DNL Log Processing Dataset Include] ne sont pas soumis à cette restriction. Pour plus d’informations sur le retraitement de vos données, voir [Retraitement et retransformation](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL Categorize] les transformations définies dans le  [!DNL Log Processing.cfg] fichier ou dans un  [!DNL Log Processing Dataset Include] fichier rechargent leurs fichiers de recherche chaque fois que les fichiers de recherche changent. Les modifications ne sont pas appliquées rétroactivement, mais elles s’appliquent à toutes les données du journal lues après la modification.

Cet exemple illustre l&#39;utilisation de la transformation [!DNL Categorize] pour intégrer les données de recherche aux données de événement collectées à partir du trafic du site Web. Supposons qu’un site Web particulier comporte des sections commerciales et qu’il soit nécessaire de pouvoir examiner et comparer les données en fonction du flux de trafic et de la valeur générés par les différentes sections. Vous pouvez créer un fichier de recherche qui liste les sous-chaînes utilisées pour identifier ces différentes sections.

Le fichier de recherche [!DNL Lookups\custommap.txt] contient le tableau suivant :

| /products/ | Produits |
|---|---|
| ^/sports/ | Sports |
| ^/actualités/ | News |
| ... | ... |

Ce fichier de catégorisation fait correspondre tout ce qui contient la chaîne &quot;/products/&quot; à la valeur &quot;Products&quot;, tout ce qui commence par &quot;/sports/&quot; à la valeur &quot;Sports&quot; et tout ce qui commence par &quot;/news/&quot; à la valeur &quot;News&quot;. La transformation de catégorisation suivante utilise la valeur du champ cs-uri-stem comme chaîne dans laquelle nous recherchons une sous-chaîne correspondante. Le résultat de la transformation est placé dans le champ x-custommap.

![](assets/cfg_TransformationType_Categorize.png)

En supposant que le paramètre Valeurs multiples soit défini sur false, l&#39;exemple produirait les valeurs suivantes pour x-custommap en fonction des valeurs répertoriées pour cs-uri-stem.

| [!DNL cs-uri-stem] | [!DNL x-custommap] |
|---|---|
| [!DNL /sports/news/today.php] | Sports |
| [!DNL /sports/products/buy.php] | Produits |
| [!DNL /news/headlines.php] | News |
| [!DNL /news/products/subscribe.php] | Produits |

La sortie est basée sur l’ordre des sous-chaînes dans le fichier de recherche. Par exemple, le cs-uri-stem [!DNL /sports/products/buy.php] renvoie &quot;Products&quot;. Bien que la racine URI soit début avec &quot;/sports/&quot;, la chaîne &quot;/products/&quot; est répertoriée avant &quot;/sports/&quot; dans le fichier de recherche. Si le paramètre Valeurs multiples était défini sur true, il y aurait une valeur supplémentaire pour x-custommap, car le dernier exemple correspondrait à deux lignes de la table de choix : Produits et actualités.

## FlatFileLookup {#section-e09b2eeb96444a859b14f03cdaab31f2}

La transformation [!DNL FlatFileLookup] utilise une table de choix composée de n&#39;importe quel nombre de colonnes et de lignes (bien que, rappelez-vous qu&#39;elle réside dans la mémoire). Au cours de ce type de transformation, le serveur de l’outil de données lit chaque enregistrement de données de événement à son tour et compare le contenu d’un champ désigné dans l’enregistrement à chacune des valeurs d’une colonne désignée de la table de choix. S’il existe une correspondance, le serveur de l’outil de données écrit une ou plusieurs valeurs de la ligne correspondante dans la table de recherche dans un ou plusieurs champs de sortie désignés dans l’enregistrement de données du événement.

La table de recherche utilisée pendant cette transformation est renseignée à partir d&#39;un fichier plat dont vous spécifiez l&#39;emplacement lorsque vous définissez la transformation.

<table id="table_772B8ABF3B44493F99069010DDB5F77A"> 
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
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez entrer n'importe quel nom ici. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions d'application de cette transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Par défaut </td> 
   <td colname="col2"> Valeur par défaut à utiliser si la condition est remplie et si aucune entrée dans le fichier de recherche ne correspond à l’entrée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Délimiteur </td> 
   <td colname="col2"> <p>Chaîne utilisée pour séparer les colonnes dans le fichier de recherche. Doit être un caractère de longueur unique. </p> <p> Si vous maintenez la touche Ctrl enfoncée et cliquez avec le bouton droit dans le paramètre Délimiteur, un menu <span class="wintitle"> Insérer</span> s'affiche. Ce menu contient une liste de caractères spéciaux qui sont souvent utilisés comme délimiteurs. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier </td> 
   <td colname="col2"> Chemin d’accès et nom de fichier du fichier de recherche. Les chemins relatifs concernent le répertoire d’installation du serveur de l’outil de données. Ce fichier se trouve généralement dans le répertoire Lookups du répertoire d’installation du serveur de l’outil de données. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rangée d’en-tête </td> 
   <td colname="col2"> Vrai ou faux. Indique que la première rangée du tableau est une rangée d’en-tête à ignorer lors du traitement. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> <span class="wintitle"> Nom de colonne </span> est le nom de la colonne utilisée pour faire correspondre l'entrée aux lignes du fichier. Si la valeur Rangée d’en-tête est true, il peut s’agir du nom d’une colonne dans le fichier de recherche. Dans le cas contraire, il doit s’agir du numéro de colonne de base zéro pour lequel une correspondance doit être établie. <span class="wintitle"> Nom de champ </span> est le nom du champ utilisé pour localiser la ligne dans le fichier de recherche. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeurs multiples </td> 
   <td colname="col2"> <p>Vrai ou faux. Détermine si une seule valeur (une ligne correspondante) ou plusieurs valeurs doivent être renvoyées (une pour chaque ligne correspondante). </p> <p> <p>Remarque :  Si <span class="wintitle"> plusieurs valeurs</span> est défini sur false, vous devez vous assurer qu’il n’y a pas plusieurs correspondances. Lorsque plusieurs correspondances se produisent, il n'y a aucune garantie quant à la correspondance qui sera renvoyée. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sorties </td> 
   <td colname="col2"> <p>Vecteur d’objets de colonne (résultats) dans lequel chaque objet est défini par les noms de colonne et de champ. </p> <p> <span class="wintitle"> Le </span> nom de colonne est la colonne à partir de laquelle la valeur de sortie est obtenue. Si <span class="wintitle"> Rangée d’en-tête</span> est vraie, il peut s’agir du nom d’une colonne dans le fichier de recherche. Dans le cas contraire, il doit s’agir du numéro de colonne de base zéro pour lequel une correspondance doit être établie. </p> <p> <span class="wintitle"> Nom de champ </span> est le nom du champ utilisé pour capturer la sortie. Notez qu’il peut s’agir d’un vecteur de résultats, un pour chaque ligne identifiée dans le cas où le paramètre Valeurs multiples a la valeur true. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Considérations relatives aux[!DNL FlatFileLookup]**

* La correspondance du champ d’entrée au fichier de recherche est toujours sensible à la casse.
* Les modifications apportées aux fichiers de recherche dans les transformations [!DNL FlatFileLookup] définies dans le fichier [!DNL Transformation.cfg] ou les fichiers [!DNL Transformation Dataset Include] nécessitent une retransformation du jeu de données. Les fichiers de recherche pour les transformations [!DNL FlatFileLookup] définies dans le fichier [!DNL Log Processing.cfg] ou les fichiers [!DNL Log Processing Dataset Include] ne sont pas soumis à cette restriction. Pour plus d’informations sur le retraitement de vos données, voir [Retraitement et retransformation](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL FlatFileLookup] dans le  [!DNL Log Processing.cfg] fichier ou les  [!DNL Log Processing Dataset Include] fichiers rechargent leurs fichiers de recherche chaque fois que les fichiers de recherche changent. Les modifications ne sont pas appliquées rétroactivement, mais elles s’appliquent à toutes les données du journal lues après la modification.

Cet exemple illustre l&#39;utilisation de la transformation [!DNL FlatFileLookup] pour intégrer les données de recherche aux données de événement collectées à partir du trafic du site Web. Supposons que vous souhaitiez isoler les partenaires du site Web qui transforment le trafic du routage vers le site Web et transformer leurs identifiants de partenaire en noms plus conviviaux. Vous pouvez ensuite utiliser les noms conviviaux pour créer des dimensions et des visualisations étendues qui correspondent plus clairement à la relation d’affaires que la relation site à site utilisée pour le trafic de routage.

L&#39;exemple de transformation recherche la paire nom-valeur dans le champ cs(parrain-requête) de l&#39;ID de partenaire et, s&#39;il se trouve, le fichier de recherche [!DNL Lookups\partners.txt] est utilisé pour comparer la valeur de l&#39;ID de partenaire aux valeurs de la colonne [!DNL Partner] de la table. Si une ligne est située, le champ de sortie x-partner-name reçoit le nom de la colonne [!DNL PrintName] de la ligne identifiée.

![](assets/cfg_TransformationType_FlatFileLookup.png)

Si la table de choix contenait les informations suivantes :

| ID | Partenaire | Démarré | PrintName |
|---|---|---|---|
| 1 | P154 | 21 août 1999 | Yahoo |
| 2 | P232 | 10 juillet 2000 | Microsoft |
| 3 | P945 | 12 janvier 2001 | Amazon |

Les exemples suivants se transformeraient comme suit :

* Si cs(parrain)(PartnerID) renvoie P232, le champ x-partner-name reçoit la valeur &quot;Microsoft&quot;.
* Si cs(parrain)(PartnerID) renvoie P100, le champ x-partner-name reçoit la valeur &quot;No Partner&quot;.
* Si cs(parrain)(PartnerID) ne renvoyait rien, le champ x-partner-name recevrait la valeur &quot;Aucun partenaire&quot; spécifiée par le paramètre par défaut.

## ODBCLookup {#section-4dcc3747e42e45c0a057e85f308a83cc}

La transformation [!DNL ODBCLookup] fonctionne comme une transformation [!DNL FlatFileLookup]. La seule différence est que la table de recherche utilisée pendant cette transformation est renseignée à partir d&#39;une base de données ODBC et non d&#39;un fichier plat.

>[!NOTE]
>
>[!DNL ODBCLookup] les transformations ne peuvent être exécutées que pendant la phase de transformation du processus de construction des ensembles de données. Dans la mesure du possible, l&#39;Adobe vous recommande d&#39;utiliser la transformation [!DNL FlatFileLookup] au lieu de la transformation [!DNL ODBCLookup]. [!DNL FlatFileLookup] les transformations sont intrinsèquement plus fiables parce qu&#39;elles ne dépendent pas de la disponibilité d&#39;un système externe. De plus, il y a moins de risque que la table de recherche soit modifiée si elle réside dans un fichier plat que vous contrôlez localement.

<table id="table_B903DB291BCC4F44B09D54300216D288"> 
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
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez entrer n'importe quel nom ici. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions d'application de cette transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom de la source de données </td> 
   <td colname="col2"> Un DSN, fourni par un administrateur de l'ordinateur serveur de l'outil de données sur lequel le jeu de données est traité, qui fait référence à la base de données à partir de laquelle les données doivent être chargées. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mot de passe de base de données </td> 
   <td colname="col2">mot de passe à utiliser lors de la connexion à la base de données. Si un mot de passe a été configuré pour le DSN dans l'<span class="wintitle"> Administrateur de source de données</span>, il peut rester vide. Tout mot de passe fourni ici remplace le mot de passe configuré pour le DSN dans l'<span class="wintitle"> Administrateur de source de données</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID utilisateur de base de données </td> 
   <td colname="col2">ID utilisateur à utiliser lors de la connexion à la base de données. Si un ID utilisateur a été configuré pour le DSN dans l'<span class="wintitle"> Administrateur de la source de données</span>, il peut rester vide. Tout ID utilisateur fourni ici remplace l’ID utilisateur configuré pour le DSN dans l’<span class="wintitle"> Administrateur de source de données</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Par défaut </td> 
   <td colname="col2"> Valeur par défaut à utiliser si la condition est remplie et qu’aucune entrée dans le fichier de recherche ne correspond à l’entrée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonne d’entrée </td> 
   <td colname="col2"> <span class="wintitle"> Le </span> nom de colonne est le nom de colonne ou l'expression SQL des données qui correspondent à l'entrée. <span class="wintitle"> Nom </span> du champ est le nom du champ contenant les données à rechercher. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeurs multiples </td> 
   <td colname="col2"> <p>Vrai ou faux. Détermine si une seule valeur (une ligne correspondante) ou plusieurs valeurs doivent être renvoyées (une pour chaque ligne correspondante). </p> <p> <p>Remarque :  Si <span class="wintitle"> plusieurs valeurs</span> est défini sur false, vous devez vous assurer qu’il n’y a pas plusieurs correspondances. Lorsque plusieurs correspondances se produisent, il n'y a aucune garantie quant à la correspondance qui sera renvoyée. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonnes de sortie </td> 
   <td colname="col2"> <p>Vecteur d’objets de colonne (résultats) où chaque objet est défini par les noms de colonne et de champ. </p> <p> <span class="wintitle"> Le </span> nom de colonne est le nom ou l'expression SQL de la colonne à partir de laquelle la valeur de sortie est obtenue. <span class="wintitle"> Nom de champ </span> est le nom du champ utilisé pour capturer la sortie. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Identifiant de table</span> </td> 
   <td colname="col2"> Expression SQL qui nomme la table ou la vue à partir de laquelle les données doivent être chargées. Un identifiant de tableau type est le SCHÉMA.TABLE. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

* Les paramètres Nom de la source de données, [!DNL Database User ID], [!DNL Database Password] et Identificateur de table sont identiques aux paramètres des mêmes noms décrits pour les sources de données ODBC. Voir [Sources de données ODBC](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

* Contrairement aux sources de données ODBC, les transformations [!DNL ODBCLookup] ne nécessitent pas une colonne d&#39;ID croissante. Voir [Sources de données ODBC](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3). Cela est dû au fait que le contenu de la table de choix ne doit en aucun cas changer tant que le jeu de données est principal. Les modifications d’une table de choix ou d’une vue ne peuvent pas être détectées tant que la transformation n’a pas eu lieu. Pour plus d’informations sur le retraitement de vos données, voir [Retraitement et retransformation](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

Supposons que vous souhaitiez convertir des enregistrements DNS obsolètes en enregistrements mis à jour. Les deux jeux d&#39;enregistrements sont stockés dans une base de données SQL. Pour effectuer cette tâche, vous référenceriez une table de recherche générée à partir de la base de données et remplacerez les enregistrements DNS obsolètes.

Notre exemple de transformation recherche le champ s-dns dans les entrées du journal et, s&#39;il se trouve, la table de recherche VISUAL.LOOKUP est utilisée pour comparer l&#39;entrée s-dns aux entrées de la colonne [!DNL OLDDNS] de la table. Si une ligne se trouve dans la table, le champ de sortie s-dns reçoit l&#39;entrée d&#39;enregistrement DNS mise à jour de la colonne [!DNL NEWDNS] de la ligne identifiée.

![](assets/cfg_TransformationType_ODBCLookup.png)
