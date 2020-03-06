---
description: Le serveur de l'outil de données (InsightServer64.exe) peut lire les données d'événement de toute base de données SQL (Oracle ou Microsoft SQL Server, par exemple) disposant d'un pilote compatible ODBC 3.0.
solution: Analytics
title: Sources de données ODBC
topic: Data workbench
uuid: 5b37cd41-2d79-472c-8e6d-00ff894991a9
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Sources de données ODBC{#odbc-data-sources}

Le serveur de l&#39;outil de données (InsightServer64.exe) peut lire les données d&#39;événement de toute base de données SQL (Oracle ou Microsoft SQL Server, par exemple) disposant d&#39;un pilote compatible ODBC 3.0.

La prise en charge ODBC du serveur de l’outil de données est similaire à la prise en charge existante pour le chargement de données à partir de Sensors ou de fichiers journaux générés par des processus externes. Il y a cependant d&#39;autres considérations et limitations :

* La prise en charge ODBC du serveur de l’outil de données est compatible avec les fonctionnalités de mise en grappe. Les données sont distribuées entre tous les serveurs de traitement et tout traitement ultérieur (y compris le traitement des requêtes) bénéficie pleinement de la mise en grappe.
* La prise en charge d&#39;ODBC dépend des pilotes ODBC tiers. Pour que la prise en charge d’ODBC fonctionne, ces pilotes doivent être configurés sur l’ordinateur sur lequel le serveur de l’outil de données s’exécute, à l’aide d’outils externes à la plate-forme Adobe. Les ordinateurs des outils de données ne nécessitent aucune configuration supplémentaire.
* La table ou la vue à partir de laquelle les données sont chargées doit comporter une colonne d’ID croissante. Pour une ligne, la valeur de cette colonne (qui peut être une colonne réelle dans la table ou une expression de colonne SQL) ne doit pas diminuer lorsque de nouvelles lignes sont insérées dans la base de données. Si cette contrainte est violée, les données sont perdues. Pour des performances adéquates, un index est requis sur cette expression de colonne ou de colonne.

   >[!NOTE]
   >
   >Il est possible que plusieurs lignes aient la même valeur dans la [!DNL Increasing ID] colonne. Une possibilité est une colonne d&#39;horodatage avec une précision inégale.

* Le serveur de l’outil de données ne peut pas charger de colonnes avec des données longues (données supérieures à une certaine longueur, comme déterminé par l’application de base de données spécifique utilisée).
* La récupération des données d’une base de données est plus lente que la lecture d’un fichier de disque. Le traitement des jeux de données qui chargent des données à partir d&#39;une source ODBC prend beaucoup plus de temps (en particulier lors du retraitement) que les jeux de données de taille équivalente dont les données proviennent de Sensors ou d&#39;autres fichiers de disque.

Pour plus d’informations sur le retraitement de vos données, voir [Retraitement et retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

**Pour configurer Insight Server pour ODBC[!DNL event data]**

La configuration du serveur de l’outil de données pour charger des données à partir d’une base de données SQL requiert d’abord les étapes suivantes dans l’ordre :

1. Installez le logiciel client de base de données approprié, y compris un pilote ODBC, sur l’ordinateur du serveur de l’outil de données sur lequel le jeu de données est traité.

   >[!NOTE]
   >
   >Si vous chargez des données d’événement ODBC pour traitement sur une grappe de serveurs de outils de données, vous devez installer le logiciel client de base de données sur tous les serveurs de traitement de la grappe. Pour plus d’informations sur la spécification des serveurs de traitement dans une grappe, voir le Guide *d’installation et d’administration des produits* serveur.

1. Configurez une source de données à l’aide de l’administrateur de source de données ODBC pour Windows.

   Il est important de noter que le serveur de l’outil de données (InsightServer64.exe) s’exécute en tant que service Windows. Par conséquent, la source de données doit normalement être configurée en tant que DSN système plutôt qu’en tant que DSN utilisateur pour que le serveur de l’outil de données puisse l’utiliser. Vous trouverez plus d’informations sur cette étape de configuration dans la documentation de votre logiciel de base de données.

Après avoir installé le logiciel client de base de données sur l’ordinateur serveur approprié de l’outil de données, vous pouvez configurer l’ensemble de données pour utiliser la source de données ODBC en modifiant les paramètres appropriés dans le fichier de [!DNL Log Processing] configuration pour le profil souhaité.

## Paramètres {#section-15c0218d93364693a565f2609a12f73e}

Pour les données provenant de bases de données utilisant la norme ODBC (Open Database Connectivity), les paramètres suivants sont disponibles :

<table id="table_606D8A90DA4A43C29F2C6130F8C753F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> Identifiant de la source ODBC. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom de la source de données </td> 
   <td colname="col2"> Un DSN, fourni par un administrateur de l’ordinateur serveur de l’outil de données sur lequel le jeu de données est traité, qui fait référence à la base de données à partir de laquelle les données doivent être chargées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mot de passe de base de données </td> 
   <td colname="col2"> mot de passe à utiliser lors de la connexion à la base de données. Si un mot de passe a été configuré pour le DSN dans l’administrateur <span class="wintitle"></span>de la source de données, il se peut que vous ne l’ayez pas renseigné. Tout mot de passe fourni ici remplace le mot de passe configuré pour le DSN dans l’administrateur <span class="wintitle"></span>de la source de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID utilisateur de base de données </td> 
   <td colname="col2"> ID utilisateur à utiliser lors de la connexion à la base de données. Si un ID utilisateur a été configuré pour le DSN dans l’administrateur <span class="wintitle"></span>de la source de données, il est possible que ce champ ne soit pas renseigné. Tout ID utilisateur fourni ici remplace l’ID utilisateur configuré pour le DSN dans l’administrateur <span class="wintitle"></span>de la source de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Champs </td> 
   <td colname="col2"> Vectorisation d’objets de colonne qui spécifie un mappage entre les colonnes de données de la base de données et les champs de données dans le moteur d’exécution du serveur de l’outil de données. Chaque colonne comporte des entrées <span class="wintitle"> Nom</span> de colonne et Nom <span class="wintitle"> de champ</span>. <span class="wintitle"> Le nom</span> de colonne est une expression de colonne SQL qui doit être valide dans le contexte de la table identifiée par l'identifiant <span class="wintitle"> de</span> table décrit ci-dessus. Il peut s’agir d’un nom de colonne ou d’une expression SQL basée sur n’importe quel nombre de colonnes dans la table. Une fonction de formatage peut être nécessaire pour convertir des valeurs de certains types de données en chaînes d’une manière qui ne perde pas de précision. Toutes les données sont implicitement converties en chaînes à l’aide de la méthode de formatage par défaut de la base de données, ce qui peut entraîner une perte de données pour certains types de données de colonne (tels que les types de données date/heure) si des expressions de formatage explicites ne sont pas utilisées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Augmentation de la colonne d’ID </td> 
   <td colname="col2"> <p>Nom de colonne ou expression de colonne SQL qui répond au critère selon lequel elle augmente (ou au moins ne diminue pas) à mesure que de nouvelles lignes sont ajoutées. Autrement dit, si la rangée B est ajoutée à la table à une date ultérieure à celle de la rangée A, la valeur de cette colonne (ou expression de colonne) de la rangée B doit être supérieure (selon l’ordre de tri natif de la base de données) à la valeur correspondante de la rangée A. </p> <p> 
     <ul id="ul_EBF6AEE4746B41B3B5BB6CC74194DAED"> 
      <li id="li_A5C9BE52B01649DE9726ECEC68B99828"> Le <span class="wintitle"> nom de colonne d’ID </span>croissant peut être identique au nom d’une colonne existante, mais il n’est pas obligatoire de le faire. </li> 
      <li id="li_CF69EAB4AFB14F4894F7A5CDCAF06947"> Cette expression est supposée avoir un type de données de caractère SQL. Si la colonne d’ID croissante réelle est d’un autre type de données, cette valeur doit être une expression de colonne pour la convertir en chaîne. Comme cela signifie généralement que les comparaisons sont lexicographiques (caractère par caractère), il est important de formater la valeur avec soin. </li> 
      <li id="li_58977431962E48039C898CFC47C53323"> L’expression est utilisée dans les clauses SQL ORDER BY et comparée à dans les clauses SQL WHERE. Il est essentiel de créer un index basé sur l’expression de colonne exacte utilisée. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID source du journal </td> 
   <td colname="col2"> <p>La valeur de ce paramètre peut être n’importe quelle chaîne. Si une valeur est spécifiée, ce paramètre vous permet de différencier les entrées de journal des différentes sources de journal pour l’identification de la source ou le traitement ciblé. Le champ x-log-source-id est renseigné par une valeur identifiant la source du journal pour chaque entrée du journal. Par exemple, si vous souhaitez identifier les entrées de journal d'une source ODBC nommée ODBCSource01, vous pouvez saisir <span class="filepath"> depuis ODBCSource01.</span> et cette chaîne serait transmise au champ x-log-source-id pour chaque entrée de journal à partir de cette source. </p> <p> Pour plus d’informations sur le champ x-log-source-id, voir Champs <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> d’enregistrement des données d’</a>événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exécuter sur le serveur </td> 
   <td colname="col2"> Valeur d’index dans le fichier <span class="filepath"> .cfg</span> profile du serveur de traitement qui effectue les requêtes ODBC pour obtenir les données de la base de données. (Le paramètre Serveurs de traitement du fichier <span class="filepath"> .cfg</span> répertorie tous les serveurs de traitement du jeu de données et chaque serveur a une valeur d’index, la première étant 0.) La valeur par défaut est 0. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Identifiant de tableau </td> 
   <td colname="col2"> Expression SQL qui nomme la table ou la vue à partir de laquelle les données doivent être chargées. Un identifiant de tableau type se trouve dans le formulaire SCHEMA.TABLE. </td> 
  </tr> 
 </tbody> 
</table>

Cet exemple montre la fenêtre de [!DNL Log Processing] configuration dans l&#39;outil de données avec une source de données ODBC. Cette source de données récupère les données d’une table appelée [!DNL VISUAL.VSL] dans une base de données avec [!DNL Data Source Name] &quot;VSTestO&quot;. Cinq (5) objets de colonne ( [!DNL Fields]) mappent les données des colonnes de données de la base de données au serveur de l’outil de données.

![](assets/cfg_LogProcessing_LogSources_ODBC.png)

