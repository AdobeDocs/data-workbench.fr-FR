---
description: Cette section contient des informations sur les conditions d’opération de test, y compris la comparaison, non pas vide, la plage, l’expression régulière et la correspondance de chaîne.
solution: Analytics
title: Conditions d’opération de test
topic: Data workbench
uuid: 6a117569-1372-4095-972b-76289a45f19e
translation-type: tm+mt
source-git-commit: 0727e5b18c89a22b6ee775b1293d3b68e5cee81c
workflow-type: tm+mt
source-wordcount: '1119'
ht-degree: 6%

---


# Conditions d’opération de test{#test-operation-conditions}

Cette section contient des informations sur les conditions d’opération de test, y compris la comparaison, non pas vide, la plage, l’expression régulière et la correspondance de chaîne.

* [Comparer](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac)
* [Non vide](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)
* [Plage](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1db31583bb09418b8f49481a897b08a6)
* [Expression régulière](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-ae9c016502cb44128760c58f2d2d5297)
* [Correspondance de chaîne](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f)

## Comparer {#section-fb2bdb3838504099b324b9838cdeeaac}

La [!DNL Compare] condition compare des valeurs numériques ou de chaîne. Pour comparer des valeurs de chaîne, vous pouvez indiquer si la casse doit être prise en compte.

Les paramètres de la [!DNL Compare] condition sont décrits dans le tableau suivant :

<table id="table_05B1FBB2AED242D99081E62BE2FBEC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Respect de la casse </td> 
   <td colname="col2">Vrai ou faux. Utilisé uniquement si le type est <span class="wintitle"> LEXIQUE</span>. Si la valeur est définie sur false, les lettres majuscules et minuscules sont considérées comme égales. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la condition. </td> 
   <td colname="col3"> Commentaires </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée A </td> 
   <td colname="col2"> Première des deux valeurs à comparer. Cette valeur représente l’opérande de gauche dans la condition. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée B </td> 
   <td colname="col2"> Seconde des deux valeurs à comparer. Cette valeur représente l’opérande approprié dans la condition. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opération </td> 
   <td colname="col2"> <p>Opération de comparaison. Les opérations disponibles (et leur signification) sont les suivantes : 
     <ul id="ul_74F3C298E9CC4FE89897BA0052A9EB9F"> 
      <li id="li_1605FA73474E404A84056D40E7082623"> = or == (Entrée A = Entrée B) </li> 
      <li id="li_F694A262ED7A4787B2A68B877339620C"> &lt;&gt; ou != (L’entrée A n’est pas égale à l’entrée B) </li> 
      <li id="li_1A75437E23B64BEB92297E1C771092B0"> &lt; (L’entrée A est inférieure à l’entrée B) </li> 
      <li id="li_B80ED6BE9DEA41FE84BC6BA3B7759276"> &lt;= (L’entrée A est inférieure ou égale à l’entrée B) </li> 
      <li id="li_93148F34065F489E8E198DFB9F9F0E70"> &gt; (L’entrée A est supérieure à l’entrée B) </li> 
      <li id="li_8A98EE9AED2445429805169040BB253D"> &gt;= (L’entrée A est supérieure ou égale à l’entrée B) </li> 
     </ul> </p> </td> 
   <td colname="col3"> = </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Type </td> 
   <td colname="col2">Type de comparaison à effectuer. Les types disponibles sont <span class="wintitle"> LEXICAL</span>, <span class="wintitle"> NUMERIQUE</span>et <span class="wintitle"> DATETIME</span>. Pour obtenir la description des types, voir Types de <a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a"> test pour les opérations</a>de test. </td> 
   <td colname="col3"> <span class="wintitle"> LEXIQUE</span> </td> 
  </tr> 
 </tbody> 
</table>

Cet exemple utilise une [!DNL Compare] condition pour définir la [!DNL Log Entry Condition]condition. Lorsque le serveur de l’outil de données lit chaque enregistrement de données de événement, il compare les valeurs numériques x-age et 55. Si pour une entrée de journal donnée, x-age est inférieur ou égal à 55, l&#39;entrée de journal est incluse dans le processus de construction du jeu de données.

![](assets/cfg_Condition_CompareCondition.png)

## Non vide {#section-1decb9d887894073a1b6b3d985729ac8}

La [!DNL Not Empty] condition vérifie un champ pour déterminer s’il contient une valeur ou s’il est vide. La condition est remplie pour toute entrée de journal dont la valeur pour le [!DNL Input] champ n’est pas vide.

Les paramètres de la [!DNL Not Empty] condition sont décrits dans le tableau suivant :

| Paramètre | Description | Par défaut |
|---|---|---|
| Commentaires | Facultatif. Remarques sur la condition. | Commentaires |
| Entrée | Nom du champ de l&#39;entrée de journal pour vérifier le contenu. |  |

Cet exemple prend comme entrée x-some-field et vérifie si le champ n’est pas vide. La condition est remplie si le champ est renseigné.

![](assets/cfg_Condition_NotEmpty.png)

## Plage {#section-1db31583bb09418b8f49481a897b08a6}

La [!DNL Range] condition utilise un champ d’entrée et détermine si la valeur de ce champ est incluse dans les valeurs de paramètre minimales (Min) et maximales (Max) données.

Les paramètres de la [!DNL Range] condition sont décrits dans le tableau suivant :

<table id="table_1587D8D333804FC28024C0DFC2F2D4D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Respect de la casse </td> 
   <td colname="col2">Vrai ou faux. Utilisé uniquement si le <span class="wintitle"> type</span> est <span class="wintitle"> LEXIQUE</span>. Si la valeur est définie sur false, les lettres majuscules et minuscules sont considérées comme égales. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la condition. </td> 
   <td colname="col3"> Commentaires </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> Nom du champ de l'entrée de journal à utiliser comme entrée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> min </td> 
   <td colname="col2"> <p>Limite inférieure de la plage. </p> <p> La valeur de ce paramètre doit être une valeur littérale ou une chaîne, et non un nom de champ. Si vous utilisez une date pour ce champ, vous devez spécifier un fuseau horaire. Pour obtenir la liste des abréviations de fuseau horaire prises en charge, voir Codes <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"></a>de fuseau horaire. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Max </td> 
   <td colname="col2"> <p>Limite supérieure de la plage. </p> <p> <p>Remarque : La valeur de ce paramètre doit être une valeur littérale ou une chaîne, et non un nom de champ. Si vous utilisez une date pour ce champ, vous devez spécifier un fuseau horaire. Pour obtenir la liste des abréviations de fuseau horaire prises en charge, voir Codes <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"></a>de fuseau horaire. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Type </td> 
   <td colname="col2">Type de comparaison à effectuer. Les types disponibles sont <span class="wintitle"> LEXICAL</span>, <span class="wintitle"> NUMERIQUE</span>et <span class="wintitle"> DATETIME</span>. Pour obtenir la description des types, voir Types de <a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a"> test pour les opérations</a>de test. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Cet exemple utilise une [!DNL Range] condition pour définir la [!DNL Log Entry Condition]condition. Lorsque le serveur de l’outil de données lit chaque [!DNL event data] enregistrement, il compare les valeurs numériques x-age et 55. Si pour une entrée de journal donnée, x-age est d&#39;au moins 55 ans, l&#39;entrée de journal est incluse dans le processus de construction des jeux de données. Cet exemple exécute la même fonction que l&#39;exemple de [!DNL Compare] condition. Voir [Comparaison](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac).

>[!NOTE]
>
>Si le paramètre Min. ou Max. n’est pas renseigné, le serveur de l’outil de données remplace les valeurs entières minimales ou maximales disponibles. La valeur minimale est zéro (0) et la valeur maximale est infinity.

![](assets/cfg_Condition_RangeCondition.png)

## Expression régulière {#section-ae9c016502cb44128760c58f2d2d5297}

Le test de [!DNL Regular Expression] condition utilise la correspondance de modèles d’expressions régulières (voir Expressions [](../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)régulières) pour déterminer si la valeur du champ d’entrée spécifié contient une chaîne qui correspond à l’un des modèles spécifiés dans le paramètre Correspond.

Si l’entrée est un vecteur de chaînes, seule la première valeur du vecteur est utilisée pour le test. La [!DNL Regular Expression] condition effectue des comparaisons de chaînes complètes. Si vous souhaitez identifier des sous-chaînes, vous devez ajouter en préfixe et en suffixe &quot;.*&quot; à la chaîne.

Les paramètres de la [!DNL Regular Expression] condition sont décrits dans le tableau suivant :

<table id="table_0BF5F89F87C9493B8DABA97620074FAD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Respect de la casse </td> 
   <td colname="col2"> Vrai ou faux. Si la valeur est définie sur false, les lettres majuscules et minuscules sont considérées comme égales. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la condition. </td> 
   <td colname="col3"> Commentaires </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> Nom du champ de l'entrée de journal à utiliser comme entrée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Correspond à </td> 
   <td colname="col2"> <p>Le ou les modèles d’expression standard à faire correspondre à la valeur du champ d’entrée. </p> <p> <b> Pour ajouter un modèle d’expression normal</b> 
     <ol id="ol_6D6467FF74334DEA8E8625C3B155D11D"> 
      <li id="li_9E13A63558FF44749C2E49BD50B7F770">Cliquez avec le bouton droit de la souris sur <span class="uicontrol"> Correspond</span>. </li> 
      <li id="li_195A2F3B6B9442F5B1DACDE0FC96CE5C">Cliquez sur <span class="uicontrol"> Ajouter une nouvelle</span> &gt; <span class="uicontrol"> Expression</span>régulière. </li> 
      <li id="li_225E98F8EF39426A9483B86EA2CFE6DF">Saisissez l’expression régulière souhaitée dans la zone de texte. </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Cet exemple illustre l’utilisation de la [!DNL Regular Expression] condition pour correspondre à un champ de données collecté à partir du trafic du site Web. La condition renvoie true uniquement si le champ cs(parrain-requête) contient une chaîne correspondant à l’expression normale `campaign=C[1-9][0-9]{4}`. Cette expression régulière correspond à toute chaîne contenant &quot;campaign=C12345&quot;. Cependant, le modèle ne correspondrait pas à la chaîne &quot;campaign=C0123&amp;&quot;, car le premier caractère situé après &quot;C&quot; ne se trouve pas dans la plage 1-9.

![](assets/cfg_Condition_RegularExpression.png)

## Correspondance de chaîne {#section-f8d132085c6b4500bfbe4515b848142f}

La [!DNL String Match] condition teste l’égalité des chaînes. Il prend un champ spécifié comme entrée et teste la valeur de ce champ dans chaque entrée de journal par rapport aux chaînes spécifiées dans le paramètre Correspond à l’opération. Si l’une de ces chaînes de correspondance sensible à la casse est identique à la valeur du champ d’entrée fourni, l’opération renvoie true. Dans le événement où la [!DNL StringCondition] variable contient aucune chaîne de correspondance, la condition renvoie false. Si l’entrée est un vecteur de chaînes, seule la première valeur (chaîne) du vecteur est utilisée pour le test.

<table id="table_BD599BAA5DD54B278813B6C38AC8DE6B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Respect de la casse </td> 
   <td colname="col2"> Vrai ou faux. Si la valeur est définie sur false, les lettres majuscules et minuscules sont considérées comme égales. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la condition. </td> 
   <td colname="col3"> Commentaires </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrée </td> 
   <td colname="col2"> Nom du champ de l'entrée de journal à utiliser comme entrée. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Correspond à </td> 
   <td colname="col2"> <p>Chaîne(s) à comparer à la valeur du champ d’entrée. </p> <p> <b>Pour ajouter une chaîne</b> 
     <ol id="ol_9E32218C771445D88357960475FAD6EB"> 
      <li id="li_A700747858D0470491783E9B3933DAFE">Cliquez avec le bouton droit de la souris sur <span class="uicontrol"> Correspond</span>. </li> 
      <li id="li_9D1A2462EA404B0F84426176737CAFED">Click <span class="uicontrol"> Add new</span> &gt; <span class="uicontrol"> String</span>. </li> 
      <li id="li_E84D2439B59548E5B1803C64A295A18E">Entrez la chaîne de votre choix dans la zone de texte. </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Cet exemple utilise les données collectées à partir du trafic du site Web pour illustrer l’utilisation de la [!DNL String Match] condition. La condition teste si le champ d&#39;entrée (cs-uri-stem) correspond à l&#39;une des deux chaînes spécifiées dans le paramètre Correspond et si le champ cs-uri-stem correspond à la chaîne exacte [!DNL /navigation/footer.asp] ou à la chaîne exacte [!DNL /navigation/header.asp].

![](assets/cfg_Condition_StringMatch.png)

