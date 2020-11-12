---
description: Les expressions régulières sont utilisées dans tous les champs de recherche des outils de données, y compris les panneaux d’entité de requête.
solution: Analytics
title: Expressions régulières
topic: Data workbench
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
translation-type: tm+mt
source-git-commit: 0727e5b18c89a22b6ee775b1293d3b68e5cee81c
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 2%

---


# Expressions régulières{#regular-expressions}

Les expressions régulières sont utilisées dans tous les champs de recherche des outils de données, y compris les panneaux d’entité de requête.

* [A propos des Expressions régulières](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [Terminologie des Expressions régulières](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [A propos de la correspondance littérale](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [Utilisation de caractères de métadonnées](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [Extraction de modèle](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## A propos des Expressions régulières {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

Une expression régulière est un modèle de texte, composé d’une combinaison de caractères alphanumériques et de caractères spéciaux, appelés métacaractères, qui localise les modèles et extrait les sous-chaînes du texte. Les expressions régulières sont largement utilisées dans la programmation informatique et font partie intégrante de langues telles que le Perl.

Pour identifier et extraire des modèles de chaînes complexes, le serveur de l’outil de données utilise des expressions régulières dans certaines des transformations et conditions. Ce qui suit est un bref guide des expressions régulières.

Cette annexe n&#39;est pas une introduction complète aux expressions régulières. La publication O&#39;Reilly *Mastering Regular Expressions, 2e édition* de Jeffrey E. F. Friedl est une référence particulièrement intéressante.

## Terminologie des Expressions régulières {#section-80b0d54f731e448391532ab3eb3c525c}

| Terme | Définition |
|---|---|
| Littéral | Un littéral est un caractère que nous utilisons dans une expression régulière pour localiser une séquence de caractères spécifique. Par exemple, pour trouver un produit dans [!DNL shop/products.html], le produit de la chaîne est un littéral, ou ce que nous recherchons littéralement dans la chaîne. |
| Métacharactère | Un métacaractère est un caractère spécial qui a une interprétation unique dans le contexte des expressions régulières. Par exemple, le point (.) est un caractère de métacaractère utilisé pour faire correspondre n’importe quel caractère. |
| Séquence d’échappement | Une séquence d&#39;échappement est simplement un moyen de dire au moteur d&#39;expression normal que nous aimerions utiliser l&#39;un des métacaractères comme littéral. Les séquences d’échappement sont toujours débuts avec la barre oblique inverse (`\`). En plaçant la barre oblique inverse (qui est également un caractère de métacaractère) devant un caractère de métacaractère, le moteur d&#39;expression classique interprète le caractère de métacaractère échappé comme un littéral. Par exemple, si vous souhaitez faire correspondre la période de métacaractère (`.`), vous devez utiliser une séquence d’échappement. Cependant, pour faire correspondre l’un des points de la chaîne 168.196.0.11, vous pouvez utiliser l’expression régulière composée d’une barre oblique inverse et d’un point (`\.`). |
| Modèle | C&#39;est la terminologie abrégée de l&#39;expression ordinaire. Essentiellement, une expression régulière est un modèle que vous essayez de faire correspondre à la chaîne de cible. |
| Chaîne de cible | Ce terme fait référence à la chaîne dans laquelle nous recherchons le modèle souhaité. |

## A propos de la correspondance littérale {#section-ec4497e3160c47ba9b828d939761b3e0}

La correspondance littérale prend une chaîne littérale sans caractère d’échappement et recherche dans la chaîne de cible s’il s’agit d’une sous-chaîne de la chaîne de cible.

Dans cet exemple, vous voyez comment fonctionne la correspondance littérale. Supposons que des données soient collectées à partir du trafic du site Web et que le champ cs(parrain) contienne la valeur suivante :

`http://www.abc.com/adventurenews/today.html?ad=123AZ45`

Pour déterminer si le parrain représente une personne ayant cliqué sur l’une des publicités, vous devez vérifier si le parrain contient la publicité à chaînes. Vous pouvez simplement utiliser la chaîne littérale de la publicité pour rechercher la chaîne de cible et déterminer si une publicité a été utilisée pour acheminer le trafic vers le site. Bien que cette chaîne corresponde à la chaîne de cible, elle correspond à deux emplacements et est donc ambiguë et peut conduire à des faux positifs.

L’URL suivante contient la chaîne publicitaire à deux emplacements différents :

`http://www.abc.com/ad vertnews/today.html?ad =123AZ45`

Par conséquent, si vous essayez de déterminer quelles sessions ont commencé à la suite d’une campagne publicitaire particulière, il est évident que l’utilisation de la publicité littérale comme expression régulière n’est pas suffisante. Le fait de remplacer le littéral par &quot;ad=&quot; éliminerait cette ambiguïté et ne ferait qu’une seule correspondance avec l’expression. Cependant, même cela peut ne pas suffire pour s&#39;assurer que le parrain faisait partie de la campagne publicitaire. Examinez le parrain suivant :

`http://www.xyz.com/hello.html?pad=something`

Vous n’avez aucun contrôle sur les URL que d’autres utilisateurs peuvent utiliser pour créer des liens vers le site. La correspondance littérale est un mécanisme trop simple pour localiser les sessions qui ont commencé à la suite de la campagne publicitaire. La section suivante explique comment utiliser les caractères de remplacement pour une correspondance plus souple et plus puissante.

## Utilisation de caractères de métadonnées {#section-e29a804336304ea1ba33d40d60139aa2}

Un métacaractère est un caractère spécial dans un programme ou un champ de données qui fournit des informations sur d&#39;autres caractères.

| métacharactère | description |
|---|---|
| . (point) | Correspond à un caractère unique, par exemple : `re:x.z` correspond à &quot;xyz&quot; ou &quot;xxz&quot;. |
| * (étoile) | Correspond à un ou plusieurs caractères, par exemple : `re:Z*` correspond à &quot;ZZZ&quot;. |
| ? (caractère générique) | Correspond à 0 ou 1 de l’expression précédente pour forcer une correspondance minimale, par exemple : `xy?z` correspond à &quot;xy&quot; et &quot;xyz&quot;. |

D’autres expressions courantes peuvent également être utilisées pour créer des chaînes de recherche plus complexes.

**Listes, plages et OU**

La correspondance littérale vous permet de rechercher une chaîne unique, mais les crochets, les tirets et les barres verticales vous permettent de définir une liste de choses à rechercher dans la chaîne de cible.

<table id="table_18B86955EC3748079E7C176273ADE92B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour ce métacaractère... </th> 
   <th colname="col2" class="entry"> Le processeur d'expression classique... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> crochets ([ ]) </td> 
   <td colname="col2"> Faites correspondre n’importe lequel des caractères à l’intérieur du crochet à une position de caractère unique. Par exemple, [AB] est une instruction qui correspond à la lettre A ou à la lettre B et [0123456789] indique qu’elle correspond à tout caractère compris entre 0 et 9. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiret (-) </td> 
   <td colname="col2"> <p>Correspond à une plage de caractères. Ainsi, au lieu d'écrire [0123456789], nous pourrions simplement écrire [0-9]. </p> <p> Cette option peut être étendue à des plages de caractères et à plusieurs plages dans un jeu de crochets. Par exemple, [0-9A-C] correspond aux caractères 0 à 9 et A à C. </p> <p> <p>Remarque :  Pour tester un tiret (-) comme littéral entre les crochets, il doit être placé en premier ou en dernier. Par exemple, [-0-9] teste - et 0 à 9. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tube (|) </td> 
   <td colname="col2"> Faites correspondre l’un des deux choix à une chaîne de cible donnée. Par exemple, b|nat correspond à bat ou nat. </td> 
  </tr> 
 </tbody> 
</table>

Prenons les exemples suivants :

| Modèle | Chaîne | Correspond à |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| Leçon`[A-Z]` | Leçon a | Aucune correspondance car a de minuscule n&#39;est pas compris dans la plage de A à Z de majuscule. |

**Négation**

La négation est un moyen de dire que vous souhaitez faire correspondre n&#39;importe quoi, sauf les caractères donnés. Le métacaractère de négation, le circonflexe ou le caret (`^`), est utilisé comme premier caractère entre crochets pour dire que vous souhaitez que la correspondance soit autre que les autres caractères entre crochets. Par exemple, pour faire correspondre n’importe quel caractère à l’exception d’un point-virgule (`;`), vous écrivez

[`^;`]

Ceci correspondrait à n’importe quel caractère, à l’exception du point-virgule.

**Positionnement**

Pour forcer une correspondance au début ou à la fin d’une chaîne de cible, deux caractères de remplacement sont utilisés.

| Pour ce métacaractère... | Le processeur d&#39;expression classique... |
|---|---|
| Circumflex ou caret (`^`) | Faire correspondre au début de la chaîne. Par exemple, ^`[Tt]`il correspondrait à la chaîne de cible &quot;Le début&quot; mais ne correspondrait pas à &quot;C&#39;est le début&quot;. |
| Symbole du dollar (`$`) | Faire correspondre à la fin de la chaîne. Par exemple, `[Ee]`nd$ correspondrait à &quot;C’est la fin&quot; mais pas à &quot;La fin est une heure spéciale&quot;. |

>[!NOTE]
>
>Lorsque l’expression normale contient ^ au début et $ à la fin, la chaîne de cible entière doit correspondre à l’expression normale.

**Correspondance avec tout**

La période (.) est un caractère de métacaractère spécial qui correspond à n’importe quel caractère de la chaîne de cible. Par exemple, l’expression régulière `^…$` correspond à toute chaîne de cible contenant exactement trois caractères. L&#39;expression régulière &quot;...&quot; correspond à toute chaîne de cible contenant au moins trois caractères.

**Modèles répétés**

Les métacaractères d’itération vous permettent de faire correspondre un modèle plusieurs fois.

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour ce métacaractère... </th> 
   <th colname="col2" class="entry"> Le processeur d'expression classique... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Point d'interrogation (?) </td> 
   <td colname="col2"> Ne correspond à aucune instance ou instance du caractère qui précède immédiatement le caractère métacaractère (?). Par exemple, le modèle rea?d correspond au rouge et à la lecture. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Astérisque (*) </td> 
   <td colname="col2"> Correspond à zéro ou plusieurs occurrences du caractère qui précède immédiatement le caractère de remplacement (*). Par exemple, le modèle [0-9]* correspond à n’importe quel nombre de caractères compris entre 0 et 9 (tout entier). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plus (+) </td> 
   <td colname="col2"> Correspond à une ou plusieurs occurrences du caractère ou de la plage précédente. Par exemple, le modèle trois+ correspondrait à trois, mais pas à travers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n} </td> 
   <td colname="col2"> <p>Faire correspondre le caractère ou la plage de traitement exactement n fois. Le modèle suivant correspond aux numéros de téléphone des États-Unis : <code>[0-9]{3}-[0-9]{3}-[0-9]{4}</code>. </p> <p> Bien qu’il ne s’agisse pas d’un modèle optimal, il détermine si la chaîne de cible est au format approprié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n,m} </td> 
   <td colname="col2"> Faites correspondre le caractère précédent au moins n fois et au plus m fois. Par exemple, fo{1,2}d correspond à la nourriture et à la nourriture, mais pas à la nourriture. </td> 
  </tr> 
 </tbody> 
</table>

## Extraction de modèle {#section-4389779653b64f6cb7c47615b25c1a79}

La mise en correspondance des schémas n&#39;est qu&#39;une partie de la puissance des expressions régulières. Les expressions régulières offrent également un mécanisme permettant d’extraire des parties clés d’une chaîne de cible. Pour ce faire, il faut utiliser les parenthèses gauche et droite. Ces extractions sont généralement utilisées comme entrée dans un autre processus et sont accessibles via l&#39;utilisation de *%position%*, où position est un entier faisant référence au nombre de parenthèses correspondantes.

Examinez les exemples suivants d’extraction des modèles :

<table id="table_BC8D471B966844049FFFCDEC0F183941"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Modèle </th> 
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
   <td colname="col3"> Aucune correspondance car a de minuscule n'est pas compris dans la plage des zones A à Z de majuscule </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>

