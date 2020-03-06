---
description: Les expressions régulières sont utilisées dans tous les champs de recherche des outils de données, y compris les panneaux d’entité de requête.
solution: Analytics
title: Expressions régulières
topic: Data workbench
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Regular Expressions{#regular-expressions}

Les expressions régulières sont utilisées dans tous les champs de recherche des outils de données, y compris les panneaux d’entité de requête.

* [A propos des expressions régulières](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [Terminologie des expressions régulières](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [A propos de la correspondance littérale](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [Utilisation de métacaractères](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [Extraction de motif](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## A propos des expressions régulières {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

Une expression régulière est un modèle de texte, composé d’une combinaison de caractères alphanumériques et de caractères spéciaux appelés métacaractères, qui localise les modèles et extrait les sous-chaînes du texte. Les expressions régulières sont largement utilisées dans la programmation informatique et font partie intégrante de langues telles que le Perl.

Pour identifier et extraire des modèles de chaînes complexes, le serveur de l’outil de données utilise des expressions régulières dans certaines des transformations et conditions. Ce qui suit est un bref guide des expressions régulières.

Cette annexe n’est pas une introduction complète aux expressions régulières. Une référence particulièrement intéressante est la publication O&#39;Reilly *Maîtrise des expressions régulières, 2e édition* de Jeffrey E. F. Friedl.

## Terminologie des expressions régulières {#section-80b0d54f731e448391532ab3eb3c525c}

| Terme | Définition |
|---|---|
| Littéral | Un littéral est un caractère que nous utilisons dans une expression régulière pour localiser une séquence de caractères spécifique. Par exemple, pour trouver le produit dans [!DNL shop/products.html], le produit de la chaîne est un littéral ou ce que nous recherchons littéralement dans la chaîne. |
| Métacharactère | Un caractère de métacaractère est un caractère spécial qui a une interprétation unique dans le contexte des expressions régulières. Par exemple, le point (.) est un métacaractère utilisé pour correspondre à n’importe quel caractère. |
| Séquence d’échappement | Une séquence d’échappement est simplement une façon de dire au moteur d’expression régulière que nous aimerions utiliser l’un des métacaractères comme littéral. Les séquences d’échappement commencent toujours par la barre oblique inverse (`\`). En plaçant la barre oblique inverse (qui est également un caractère de métacaractère) devant un caractère de métacaractère, le moteur d’expression régulière interprète ce caractère comme un littéral. Par exemple, si vous souhaitez faire correspondre la période du métacaractère (`.`), vous devez utiliser une séquence d’échappement. Cependant, pour correspondre à l’une des périodes de la chaîne 168.196.0.11, vous pouvez utiliser l’expression régulière sous la forme d’une barre oblique inverse et d’un point (`\.`). |
| Motif | Il s’agit de la terminologie abrégée de l’expression régulière. Essentiellement, une expression régulière est un modèle que vous tentez de faire correspondre à la chaîne cible. |
| Chaîne cible | Ce terme fait référence à la chaîne dans laquelle nous recherchons pour localiser le modèle souhaité. |

## A propos de la correspondance littérale {#section-ec4497e3160c47ba9b828d939761b3e0}

La correspondance littérale prend une chaîne littérale sans caractère d’échappement et recherche dans la chaîne cible pour voir s’il s’agit d’une sous-chaîne de la chaîne cible.

Dans cet exemple, vous voyez comment fonctionne la correspondance littérale. Supposons que des données soient collectées à partir du trafic du site Web et que le champ cs(referrer) contienne la valeur suivante :

`http://www.abc.com/adventurenews/today.html?ad=123AZ45`

Pour déterminer si le référent représente une personne ayant cliqué sur l’une des publicités, vous devez vérifier si le référent contient la publicité sous forme de chaîne. Vous pouvez simplement utiliser la chaîne littérale de publicité pour rechercher la chaîne cible et déterminer si une publicité a été utilisée pour acheminer le trafic vers le site. Bien que cette chaîne corresponde à la chaîne cible, elle correspond à deux emplacements et est donc ambiguë et peut entraîner des faux positifs.

L’URL suivante contient la chaîne publicitaire à deux emplacements différents :

`http://www.abc.com/ad vertnews/today.html?ad =123AZ45`

Ainsi, si vous essayez de déterminer les sessions qui ont commencé suite à une campagne publicitaire particulière, il est évident que l’utilisation de la publicité littérale comme expression régulière n’est pas suffisante. Si vous modifiez le littéral en &quot;ad=&quot;, cette ambiguïté disparaîtra et l’expression ne fera qu’une seule correspondance. Cependant, même cela peut ne pas suffire à garantir que le référent faisait partie de la campagne publicitaire. Examinez le référent suivant :

`http://www.xyz.com/hello.html?pad=something`

Vous n’avez aucun contrôle sur les URL que d’autres utilisateurs peuvent utiliser pour créer des liens vers le site. La correspondance littérale est un mécanisme trop simple pour localiser les sessions qui ont commencé à la suite de la campagne de publicité. La section suivante explique comment utiliser les métacaractères pour une correspondance plus souple et plus puissante.

## Utilisation de métacaractères {#section-e29a804336304ea1ba33d40d60139aa2}

Un métacaractère est un caractère spécial dans un programme ou un champ de données qui fournit des informations sur d’autres caractères.

| métacaractère | description |
|---|---|
| . (point) | Correspond à un caractère unique, par exemple : `re:x.z` correspond à &quot;xyz&quot; ou &quot;xxz&quot;. |
| * (étoile) | Correspond à un ou plusieurs caractères, par exemple : `re:Z*` correspond à &quot;ZZZ&quot;. |
| ? (caractère générique) | Correspond à 0 ou 1 de l’expression précédente pour forcer une correspondance minimale, par exemple : `xy?z` correspond à &quot;xy&quot; et &quot;xyz&quot;. |

D’autres expressions régulières courantes peuvent également être utilisées pour créer des chaînes de recherche plus complexes.

**Listes, Plages et OU**

La correspondance littérale vous permet de rechercher une chaîne unique, mais les crochets, les tirets et les barres verticales vous permettent de définir une liste des éléments à rechercher dans la chaîne cible.

<table id="table_18B86955EC3748079E7C176273ADE92B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour ce métacaractère... </th> 
   <th colname="col2" class="entry"> Le processeur d'expression régulière va... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Crochets carrés ([ ]) </td> 
   <td colname="col2"> Faites correspondre n’importe lequel des caractères à l’intérieur du crochet à une position de caractère unique. Par exemple, [AB] est une instruction qui correspond à la lettre A ou B et [0123456789] indique qu’elle correspond à un caractère compris entre 0 et 9. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiret (-) </td> 
   <td colname="col2"> <p>Correspond à une plage de caractères. Ainsi, au lieu d'écrire [0123456789], nous pourrions simplement écrire [0-9]. </p> <p> Cette option peut être étendue aux plages de caractères et à plusieurs plages d’un jeu de crochets. Par exemple, [0-9A-C] correspond aux caractères 0 à 9 et A à C. </p> <p> <p>Remarque :  Pour tester un tiret (-) comme littéral à l’intérieur des crochets, il doit être placé en premier ou en dernier. Par exemple, [-0-9] teste - et 0 à 9. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pipe (|) </td> 
   <td colname="col2"> Faites correspondre l’un des deux choix à une chaîne cible donnée. Par exemple, b|nat correspond à bat ou nat. </td> 
  </tr> 
 </tbody> 
</table>

Prenons les exemples suivants :

| Motif | Chaîne | Correspond à |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| Leçon`[A-Z]` | Leçon a | Aucune correspondance, car a de minuscules n’est pas compris dans la plage des zones de A à Z supérieures. |

**Négation**

La négation est une manière de dire que vous souhaitez faire correspondre n’importe quoi, à l’exception des caractères donnés. Le métacaractère de négation, le circonflexe ou le caret (`^`), est utilisé comme premier caractère entre crochets pour dire que vous souhaitez que la correspondance soit autre chose que les autres caractères entre crochets. Par exemple, pour faire correspondre un caractère autre qu’un point-virgule (`;`), vous devez écrire

[`^;`]

Cela correspondrait à n’importe quel caractère, à l’exception du point-virgule.

**Positionnement**

Pour forcer une correspondance au début ou à la fin d’une chaîne cible, l’un des deux métacaractères est utilisé.

| Pour ce métacaractère... | Le processeur d&#39;expression régulière va... |
|---|---|
| Circumflex ou caret (`^`) | Faire correspondre au début de la chaîne. Par exemple, ^`[Tt]`il correspondrait à la chaîne cible &quot;Le début&quot; mais pas à &quot;C&#39;est le début&quot;. |
| Symbole du dollar (`$`) | Faire correspondre à la fin de la chaîne. Par exemple, `[Ee]`nd$ correspondrait à &quot;C’est la fin&quot;, mais pas à &quot;La fin est un moment spécial&quot;. |

>[!NOTE]
>
>Lorsque l’expression régulière contient ^ au début et $ à la fin, la chaîne cible entière doit correspondre à l’expression régulière.

**Correspondance avec tout**

Le point (.) est un caractère spécial qui correspond à n’importe quel caractère de la chaîne cible. Par exemple, l’expression régulière `^…$` correspond à toute chaîne cible de trois caractères exactement. L’expression régulière &quot;...&quot; correspond à toute chaîne cible contenant au moins trois caractères.

**Modèles répétés**

Les métacaractères d’itération vous permettent de faire correspondre un modèle plusieurs fois.

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour ce métacaractère... </th> 
   <th colname="col2" class="entry"> Le processeur d'expression régulière va... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Point d'interrogation (?) </td> 
   <td colname="col2"> Ne correspond à aucune instance ou instance du caractère qui précède immédiatement le caractère de remplacement (?). Par exemple, le modèle rea?d correspond à red et read. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Astérisque (*) </td> 
   <td colname="col2"> Correspond à zéro ou plusieurs occurrences du caractère qui précède immédiatement le caractère de remplacement (*). Par exemple, le modèle [0-9]* correspond à n’importe quel nombre de caractères compris entre 0 et 9 (tout entier). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plus (+) </td> 
   <td colname="col2"> Correspondance à une ou plusieurs occurrences du caractère ou de la plage précédent. Par exemple, le modèle trois+ correspondrait à trois, mais pas à travers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n} </td> 
   <td colname="col2"> <p>Faites correspondre le caractère ou la plage de traitement exactement n fois. Le modèle suivant correspond aux numéros de téléphone des États-Unis : [0-9]{3}-[0-9]{3}-[0-9]{4}. </p> <p> Bien qu’il ne s’agisse pas d’un modèle optimal, il détermine si la chaîne cible est dans le bon format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n,m} </td> 
   <td colname="col2"> Faites correspondre le caractère précédent au moins n fois et au plus m fois. Par exemple, fo{1,2}d correspondrait à la nourriture et à la nourriture, mais pas à la nourriture. </td> 
  </tr> 
 </tbody> 
</table>

## Extraction de motif {#section-4389779653b64f6cb7c47615b25c1a79}

La correspondance de modèles n’est qu’une partie de la puissance des expressions régulières. Les expressions régulières fournissent également un mécanisme permettant d’extraire des parties clés d’une chaîne cible. Pour ce faire, utilisez les parenthèses gauche et droite. Ces extractions sont généralement utilisées comme entrée dans un autre processus et sont accessibles via l&#39;utilisation de *%position%*, où position est un entier faisant référence au nombre de parenthèses correspondantes.

Examinez les exemples suivants d’extraction de motif :

<table id="table_BC8D471B966844049FFFCDEC0F183941"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Motif </th> 
   <th colname="col2" class="entry"> Chaîne </th> 
   <th colname="col3" class="entry"> Correspond à </th> 
   <th colname="col4" class="entry"> Extraction </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Win(9[58]) </td> 
   <td colname="col2"> OS=Win95 </td> 
   <td colname="col3"> Win95 </td> 
   <td colname="col4"> %1% = 95 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> (Win)(95|8) </td> 
   <td colname="col2"> OS=Win98 </td> 
   <td colname="col3"> Win98 </td> 
   <td colname="col4"> <p>%1% = Win </p> <p> %2% = 98 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mozilla/([0-9]).([0-9]) </td> 
   <td colname="col2"> Mozilla/3.0 </td> 
   <td colname="col3"> Mozilla/3.03 </td> 
   <td colname="col4"> <p>%1% = 3 </p> <p> %2% = 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lesson([A-Z]) </td> 
   <td colname="col2"> Leçon a </td> 
   <td colname="col3"> Aucune correspondance, car a minuscule n’est pas compris dans la plage des A à Z majuscules </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>
