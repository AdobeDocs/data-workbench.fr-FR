---
description: Informations sur les transformations que vous pouvez utiliser pour incorporer des données de recherche dans le jeu de données.
title: Définition des transformations Lookup
uuid: 4f7358b1-9e6a-4d03-b0c6-411e454fc11e
exl-id: 7b1504be-8669-4340-8400-e33f9663b602
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2288'
ht-degree: 2%

---

# Définition des transformations Lookup{#defining-lookup-transformations}

{{eol}}

Informations sur les transformations que vous pouvez utiliser pour incorporer des données de recherche dans le jeu de données.

Notez que tous les types ne peuvent pas être utilisés lors des deux phases du processus de construction du jeu de données.

* [Catégorisation](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-8474376c14e54d14ae73749696ada468)
* [FlatFileLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-e09b2eeb96444a859b14f03cdaab31f2)
* [ODBCLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-4dcc3747e42e45c0a057e85f308a83cc)

## Catégorisation {#section-8474376c14e54d14ae73749696ada468}

Le [!DNL Categorize] La transformation utilise une table de recherche à deux colonnes composée de paires chaîne-modèle/valeur. Au cours de cette transformation, le serveur Data Workbench lit à son tour chaque enregistrement de données d’événement et compare le contenu d’un champ désigné dans l’enregistrement à chacune des chaînes de modèle répertoriées dans la première colonne de la table de recherche. Si le champ désigné correspond à l’une des chaînes de modèle, le serveur Data Workbench écrit la valeur (trouvée dans la deuxième colonne) associée à cette chaîne de modèle dans un champ de sortie désigné de l’enregistrement.

Les chaînes de la première colonne de la table de recherche peuvent éventuellement commencer par le caractère ^ et/ou se terminer par le caractère $ pour forcer la correspondance au début et/ou à la fin. Cette transformation n’accepte pas d’expressions régulières pour définir les conditions de correspondance dans la première colonne. Si la valeur d’entrée est un vecteur de chaînes, chaque chaîne est exécutée par la transformation et le ou les résultats sont ajoutés à un vecteur de chaîne de sortie.

A [!DNL Categorize] la transformation est généralement plus facile et plus rapide que l’utilisation d’une [!DNL Regular Expression] la transformation pour accomplir la même chose.

>[!NOTE]
>
>Test de sous-chaîne utilisé dans [!DNL Categorize] est sensible à la casse, sauf indication contraire de l’utilisation de la propriété [!DNL Case Sensitive] .

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
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Respect de la casse </td> 
   <td colname="col2"> True ou false. Indique si le test de sous-chaîne est sensible à la casse. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Les conditions dans lesquelles cette transformation est appliquée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Par défaut </td> 
   <td colname="col2"> La valeur par défaut à utiliser si le test de condition réussit et qu’aucune entrée dans le fichier de classification ne correspond à l’entrée ou si le champ d’entrée n’est pas défini dans l’entrée de journal donnée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Délimiteur </td> 
   <td colname="col2"> <p>Chaîne utilisée pour séparer les colonnes du fichier de recherche. Doit comporter un seul caractère. </p> <p> Si vous maintenez la touche Ctrl enfoncée et cliquez avec le bouton droit dans le paramètre Délimiteur, une <span class="wintitle"> Insérer</span> s’affiche. Ce menu contient une liste de caractères spéciaux, souvent utilisés comme délimiteurs. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plusieurs valeurs </td> 
   <td colname="col2"> True ou false. Si la valeur est true, lorsque plusieurs lignes du fichier correspondent à l’entrée, chaque correspondance entraîne l’ajout d’une valeur au vecteur de sortie des chaînes. Si la valeur est false, seule la première ligne correspondante du fichier est utilisée dans la sortie. Dans ce dernier cas, si l’entrée est un vecteur, la sortie est également un vecteur de longueur équivalente. Si l’entrée est une chaîne simple, la sortie est également une chaîne simple. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier </td> 
   <td colname="col2"> Chemin et nom de fichier du fichier de catégorisation. Les chemins d’accès relatifs concernent le répertoire d’installation du serveur Data Workbench. Ce fichier se trouve généralement dans le répertoire Recherches du répertoire d’installation du serveur Data Workbench. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> Le fichier de classification correspond à ses sous-chaînes par rapport à la valeur de ce champ afin d’identifier la ligne correspondante dans le fichier. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sortie </td> 
   <td colname="col2"> Nom du champ associé au résultat. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Observations relatives à la catégorisation**

* Modifications apportées aux fichiers de recherche dans [!DNL Categorize] transformations définies dans la variable [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include] nécessite une retransformation du jeu de données. Fichiers de recherche pour [!DNL Categorize] transformations définies dans la variable [!DNL Log Processing.cfg] ou un [!DNL Log Processing Dataset Include] ne sont pas soumis à cette limitation. Pour plus d’informations sur le retraitement de vos données, voir [Retraitement et retransformation](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL Categorize] transformations définies dans la variable [!DNL Log Processing.cfg] ou un [!DNL Log Processing Dataset Include] rechargez leurs fichiers de recherche chaque fois que les fichiers de recherche changent. Les modifications ne sont pas appliquées rétroactivement, mais elles s’appliquent à toutes les données de journal lues après la modification.

Cet exemple illustre l’utilisation de la fonction [!DNL Categorize] transformation pour intégrer les données de recherche aux données d’événement collectées à partir du trafic du site web. Supposons qu’un site web particulier comporte des sections commerciales et qu’il soit nécessaire de pouvoir examiner et effectuer des comparaisons en fonction du flux de trafic et de la valeur générés par les différentes sections. Vous pouvez créer un fichier de recherche qui répertorie les sous-chaînes utilisées pour identifier ces différentes sections.

Le fichier de recherche [!DNL Lookups\custommap.txt] contient le tableau suivant :

| /produits/ | Produits |
|---|---|
| ^/sports/ | Sports |
| ^/actualités/ | News |
| ... | ... |

Ce fichier de classification associe tout ce qui contient la chaîne &quot;/products/&quot; à la valeur &quot;Products&quot;, tout ce qui commence par &quot;/sports/&quot; à la valeur &quot;Sports&quot; et tout ce qui commence par &quot;/news/&quot; à la valeur &quot;News&quot;. La transformation de classification suivante utilise la valeur du champ cs-uri-stem comme chaîne dans laquelle nous recherchons une sous-chaîne correspondante. Le résultat de la transformation est placé dans le champ x-custommap .

![](assets/cfg_TransformationType_Categorize.png)

En supposant que le paramètre Plusieurs valeurs soit défini sur false, l’exemple produirait les valeurs suivantes pour x-custommap , selon les valeurs répertoriées pour cs-uri-stem.

| [!DNL cs-uri-stem] | [!DNL x-custommap] |
|---|---|
| [!DNL /sports/news/today.php] | Sports |
| [!DNL /sports/products/buy.php] | Produits |
| [!DNL /news/headlines.php] | News |
| [!DNL /news/products/subscribe.php] | Produits |

La sortie est basée sur l’ordre des sous-chaînes dans le fichier de recherche. Par exemple, le système cs-uri-stem [!DNL /sports/products/buy.php] renvoie &quot;Products&quot;. Bien que la racine URI commence par &quot;/sports/&quot;, la chaîne &quot;/products/&quot; est répertoriée avant &quot;/sports/&quot; dans le fichier de recherche. Si le paramètre Valeurs multiples était défini sur true, il y aurait une valeur supplémentaire pour x-custommap, car le dernier exemple correspondrait à deux lignes dans le tableau de recherche : Produits et actualités.

## FlatFileLookup {#section-e09b2eeb96444a859b14f03cdaab31f2}

Le [!DNL FlatFileLookup] La transformation utilise une table de recherche composée de n’importe quel nombre de colonnes et de lignes (bien que, rappelez-vous qu’elle réside dans la mémoire). Pendant ce type de transformation, le serveur Data Workbench lit à son tour chaque enregistrement de données d’événement et compare le contenu d’un champ désigné dans l’enregistrement à chacune des valeurs d’une colonne désignée de la table de recherche. S’il existe une correspondance, le serveur Data Workbench écrit une ou plusieurs valeurs de la ligne correspondante dans le tableau de recherche vers un ou plusieurs champs de sortie désignés dans l’enregistrement de données d’événement.

La table de recherche utilisée pendant cette transformation est renseignée à partir d’un fichier plat dont vous spécifiez l’emplacement lorsque vous définissez la transformation.

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
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Les conditions dans lesquelles cette transformation est appliquée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Par défaut </td> 
   <td colname="col2"> Valeur par défaut à utiliser si la condition est remplie et si aucune entrée dans le fichier de recherche ne correspond à l’entrée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Délimiteur </td> 
   <td colname="col2"> <p>Chaîne utilisée pour séparer les colonnes du fichier de recherche. Doit comporter un seul caractère. </p> <p> Si vous maintenez la touche Ctrl enfoncée et cliquez avec le bouton droit dans le paramètre Délimiteur, une <span class="wintitle"> Insérer</span> s’affiche. Ce menu contient une liste de caractères spéciaux, souvent utilisés comme délimiteurs. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier </td> 
   <td colname="col2"> Chemin et nom de fichier du fichier de recherche. Les chemins d’accès relatifs concernent le répertoire d’installation du serveur Data Workbench. Ce fichier se trouve généralement dans le répertoire Recherches du répertoire d’installation du serveur Data Workbench. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rangée d’en-tête </td> 
   <td colname="col2"> True ou false. Indique que la première rangée du tableau est une rangée d’en-tête à ignorer lors du traitement. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> <span class="wintitle"> Nom de la colonne</span> est le nom de la colonne utilisée pour faire correspondre l’entrée à la ou aux lignes du fichier. Si la valeur de la ligne d’en-tête est true, il peut s’agir du nom d’une colonne dans le fichier de recherche. Dans le cas contraire, il doit s’agir du numéro de colonne de base zéro auquel la correspondance doit être établie. <span class="wintitle"> Nom du champ</span> est le nom du champ utilisé pour localiser la ligne dans le fichier de recherche. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plusieurs valeurs </td> 
   <td colname="col2"> <p>True ou false. Détermine si une seule valeur (une ligne correspondante) ou plusieurs valeurs doivent être renvoyées (une pour chaque ligne correspondante). </p> <p> <p>Remarque : If <span class="wintitle"> Plusieurs valeurs</span> est définie sur false, vous devez vous assurer qu’il n’y a pas plusieurs correspondances. Lorsque plusieurs correspondances se produisent, rien ne garantit que la correspondance sera renvoyée. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sorties </td> 
   <td colname="col2"> <p>Un vecteur d’objets de colonne (résultats) dans lequel chaque objet est défini par les noms de colonne et de champ. </p> <p> <span class="wintitle"> Nom de la colonne</span> est la colonne à partir de laquelle la valeur de sortie est obtenue. If <span class="wintitle"> Rangée d’en-tête</span> est définie sur true, il peut s’agir du nom d’une colonne dans le fichier de recherche. Dans le cas contraire, il doit s’agir du numéro de colonne de base zéro auquel la correspondance doit être établie. </p> <p> <span class="wintitle"> Nom du champ</span> est le nom du champ utilisé pour capturer la sortie. Notez qu’il peut s’agir d’un vecteur de résultats, un pour chaque ligne identifiée dans le cas où le paramètre Valeurs multiples est défini sur "true". </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Considérations pour[!DNL FlatFileLookup]**

* La correspondance du champ d’entrée avec le fichier de recherche est toujours sensible à la casse.
* Modifications apportées aux fichiers de recherche dans [!DNL FlatFileLookup] transformations définies dans la variable [!DNL Transformation.cfg] fichier ou [!DNL Transformation Dataset Include] Les fichiers nécessitent une retransformation du jeu de données. Fichiers de recherche pour [!DNL FlatFileLookup] transformations définies dans la variable [!DNL Log Processing.cfg] fichier ou [!DNL Log Processing Dataset Include] Les fichiers ne sont pas soumis à cette limitation. Pour plus d’informations sur le retraitement de vos données, voir [Retraitement et retransformation](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL FlatFileLookup] transformations dans la [!DNL Log Processing.cfg] fichier ou [!DNL Log Processing Dataset Include] Les fichiers rechargent leurs fichiers de recherche chaque fois que les fichiers de recherche changent. Les modifications ne sont pas appliquées rétroactivement, mais elles s’appliquent à toutes les données de journal lues après la modification.

Cet exemple illustre l’utilisation de la fonction [!DNL FlatFileLookup] transformation pour intégrer les données de recherche aux données d’événement collectées à partir du trafic du site web. Supposons que vous souhaitiez isoler les partenaires de site web qui acheminent le trafic vers le site web et transformer leurs ID de partenaire en noms plus conviviaux. Vous pouvez ensuite utiliser les noms conviviaux pour créer des dimensions et des visualisations étendues qui correspondent plus clairement aux relations commerciales qu’aux relations de site à site utilisées pour le routage du trafic.

L’exemple de transformation recherche la paire nom-valeur cs(referrer-query) dans le champ cs(referrer-query) et, si elle est localisée, le fichier de recherche. [!DNL Lookups\partners.txt] sert à comparer la valeur PartnerID aux valeurs de la variable [!DNL Partner] de la table. Si une ligne est située, le champ de sortie x-partner-name reçoit le nom de la fonction [!DNL PrintName] de la ligne identifiée.

![](assets/cfg_TransformationType_FlatFileLookup.png)

Si la table de recherche contenait les informations suivantes :

| ID | Partenaire | Démarré | PrintName |
|---|---|---|---|
| 1 | P154 | 21 août 1999 | Yahoo |
| 2 | P232 | 10 juillet 2000 | Microsoft |
| 3 | P945 | 12 janvier 2001 | Amazon |

Les exemples suivants transformeraient comme suit :

* Si cs(referrer)(PartnerID) renvoie P232, la valeur &quot;Microsoft&quot; est affectée au champ x-partner-name.
* Si cs(referrer)(PartnerID) renvoie P100, le champ x-partner-name reçoit la valeur &quot;No Partner&quot;.
* Si cs(referrer)(PartnerID) ne renvoie rien, le champ x-partner-name reçoit la valeur &quot;No Partner&quot; (Aucun partenaire) comme spécifié par le paramètre par défaut.

## ODBCLookup {#section-4dcc3747e42e45c0a057e85f308a83cc}

Le [!DNL ODBCLookup] la transformation fonctionne comme un [!DNL FlatFileLookup] transformation. La seule différence est que la table de recherche utilisée pendant cette transformation est renseignée à partir d’une base de données ODBC et non d’un fichier plat.

>[!NOTE]
>
>[!DNL ODBCLookup] les transformations ne peuvent être exécutées que pendant la phase de transformation du processus de construction du jeu de données. Si possible, Adobe vous recommande d’utiliser la variable [!DNL FlatFileLookup] plutôt que la transformation [!DNL ODBCLookup] transformation. [!DNL FlatFileLookup] Les transformations sont par nature plus fiables, car elles ne dépendent pas de la disponibilité d’un système externe. En outre, il y a moins de risque que la table de recherche soit modifiée si elle réside dans un fichier plat que vous contrôlez localement.

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
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Les conditions dans lesquelles cette transformation est appliquée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom de la source de données </td> 
   <td colname="col2"> Un DSN, fourni par un administrateur de l’ordinateur serveur Data Workbench sur lequel le jeu de données est traité, qui fait référence à la base de données à partir de laquelle les données doivent être chargées. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mot de passe de la base de données </td> 
   <td colname="col2">mot de passe à utiliser lors de la connexion à la base de données. Si un mot de passe a été configuré pour le DSN dans la variable <span class="wintitle"> Administrateur de source de données</span>, ce champ peut être laissé vide. Tout mot de passe fourni ici remplace le mot de passe configuré pour le DSN dans la variable <span class="wintitle"> Administrateur de source de données</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Identifiant utilisateur de base de données </td> 
   <td colname="col2">Identifiant utilisateur à utiliser lors de la connexion à la base de données. Si un ID utilisateur a été configuré pour le DSN dans la variable <span class="wintitle"> Administrateur de source de données</span>, ce champ peut être laissé vide. Tout ID utilisateur fourni ici remplace l’ID utilisateur configuré pour le DSN dans la variable <span class="wintitle"> Administrateur de source de données</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Par défaut </td> 
   <td colname="col2"> La valeur par défaut à utiliser si la condition est remplie et qu’aucune entrée dans le fichier de recherche ne correspond à l’entrée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonne d’entrée </td> 
   <td colname="col2"> <span class="wintitle"> Nom de la colonne</span> est le nom de colonne ou l’expression SQL des données correspondantes à l’entrée. <span class="wintitle"> Nom du champ</span> est le nom du champ contenant les données à rechercher. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plusieurs valeurs </td> 
   <td colname="col2"> <p>True ou false. Détermine si une seule valeur (une ligne correspondante) ou plusieurs valeurs doivent être renvoyées (une pour chaque ligne correspondante). </p> <p> <p>Remarque : If <span class="wintitle"> Plusieurs valeurs</span> est définie sur false, vous devez vous assurer qu’il n’y a pas plusieurs correspondances. Lorsque plusieurs correspondances se produisent, rien ne garantit que la correspondance sera renvoyée. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonnes de sortie </td> 
   <td colname="col2"> <p>Un vecteur d’objets de colonne (résultats) où chaque objet est défini par les noms de colonne et de champ. </p> <p> <span class="wintitle"> Nom de la colonne</span> est le nom de ou l’expression SQL de la colonne à partir de laquelle la valeur de sortie est obtenue. <span class="wintitle"> Nom du champ</span> est le nom du champ utilisé pour capturer la sortie. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Identifiant de tableau</span> </td> 
   <td colname="col2"> Une expression SQL qui nomme la table ou la vue à partir de laquelle les données doivent être chargées. Un identifiant de tableau standard est du formulaire SCHEMA.TABLE. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

* Le nom de la source de données, [!DNL Database User ID], [!DNL Database Password], et les paramètres d’identifiant de tableau sont identiques à ceux des mêmes noms décrits pour les sources de données ODBC. Voir [Sources de données ODBC](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

* Contrairement aux sources de données ODBC, [!DNL ODBCLookup] Les transformations ne nécessitent pas d’augmentation de la colonne ID. Voir [Sources de données ODBC](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3). Cela est dû au fait que le contenu de la table de recherche ne doit pas changer d’aucune manière pendant que le jeu de données est principal. Les modifications d’une table ou d’une vue de recherche ne peuvent pas être détectées tant que la retransformation n’a pas eu lieu. Pour plus d’informations sur le retraitement de vos données, voir [Retraitement et retransformation](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

Supposons que vous souhaitiez convertir des enregistrements DNS obsolètes en enregistrements mis à jour. Les deux ensembles d&#39;enregistrements sont stockés dans une base de données SQL. Pour effectuer cette tâche, vous devez référencer une table de recherche générée à partir de la base de données et remplacer les enregistrements DNS obsolètes.

Notre exemple de transformation recherche les entrées de journal pour le champ s-dns et, s’il est localisé, la table de recherche VISUAL.LOOKUP est utilisée pour comparer l’entrée s-dns aux entrées dans la variable [!DNL OLDDNS] de la table. Si une ligne se trouve dans le tableau, le champ de sortie s-dns reçoit l’entrée d’enregistrement DNS mise à jour de la [!DNL NEWDNS] de la ligne identifiée.

![](assets/cfg_TransformationType_ODBCLookup.png)
