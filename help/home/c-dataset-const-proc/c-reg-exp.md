---
description: Les expressions régulières sont utilisées dans tous les champs de recherche Data Workbench, y compris les panneaux d’entités de requête.
title: Expressions régulières
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
exl-id: 75841a70-e78a-429b-b00d-ac107b7a87aa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 2%

---

# Expressions régulières{#regular-expressions}

Les expressions régulières sont utilisées dans tous les champs de recherche Data Workbench, y compris les panneaux d’entités de requête.

* [À propos des expressions régulières](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [Terminologie des expressions régulières](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [À propos de la correspondance littérale](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [Utilisation de métacaractères](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [Extraction de modèle](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## À propos des expressions régulières {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

Une expression régulière est un modèle de texte constitué d’une combinaison de caractères alphanumériques et de caractères spéciaux, appelés métacaractères, qui localise les modèles et extrait les sous-chaînes du texte. Les expressions régulières sont largement utilisées dans la programmation informatique et font partie intégrante de langues telles que Perl.

Pour identifier et extraire des modèles de chaîne complexes, le serveur Data Workbench utilise des expressions régulières dans certaines des transformations et conditions. Voici un bref guide sur les expressions régulières.

Cette annexe n’est pas une introduction complète aux expressions régulières. Une référence particulièrement intéressante est la publication de O&#39;Reilly *Mastering Regular Expressions, 2nd Edition* de Jeffrey E. F. Friedl.

## Terminologie des expressions régulières {#section-80b0d54f731e448391532ab3eb3c525c}

| Terme | Définition |
|---|---|
| Littéral | Un littéral est un caractère que nous utilisons dans une expression régulière pour localiser une séquence de caractères spécifique. Par exemple, pour trouver un produit dans [!DNL shop/products.html], le produit de chaîne est un littéral ou ce que nous recherchons littéralement dans la chaîne. |
| Metacharacter | Un métacaractère est un caractère spécial qui a une interprétation unique dans le contexte des expressions régulières. Par exemple, le point (.) est un métacaractère utilisé pour faire correspondre n’importe quel caractère. |
| Séquence d’échappement | Une séquence d’échappement est simplement une façon de dire au moteur d’expression régulière que nous aimerions utiliser l’un des métacaractères comme littéral. Les séquences d’échappement commencent toujours par la barre oblique inverse (`\`). En plaçant la barre oblique inverse (qui est également un métacaractère) devant un métacaractère, le moteur d’expression régulière interprète le métacaractère avec échappement comme un littéral. Par exemple, si vous souhaitez faire correspondre la période du métacaractère (`.`), vous devez utiliser une séquence d’échappement. Cependant, pour correspondre à l’une des périodes de la chaîne 168.196.0.11, vous pouvez utiliser l’expression régulière composée d’une barre oblique inverse et d’un point (`\.`). |
| Modèle | Il s’agit de la terminologie courte de l’expression régulière. Essentiellement, une expression régulière est un modèle que vous essayez de faire correspondre avec la chaîne cible. |
| Chaîne cible | Ce terme fait référence à la chaîne dans laquelle nous recherchons pour localiser le modèle souhaité. |

## À propos de la correspondance littérale {#section-ec4497e3160c47ba9b828d939761b3e0}

La correspondance littérale prend une chaîne littérale sans caractère d’échappement et recherche dans la chaîne cible s’il s’agit d’une sous-chaîne de la chaîne cible.

Dans cet exemple, vous voyez comment fonctionne la correspondance littérale. Supposons que des données soient collectées à partir du trafic du site web et que le champ cs(referrer) contienne la valeur suivante :

`http://www.abc.com/adventurenews/today.html?ad=123AZ45`

Pour déterminer si le référent représente une personne ayant cliqué sur l’une des publicités, vous devez vérifier si le référent contient la publicité sous forme de chaîne. Vous pouvez simplement utiliser la chaîne littérale de l’annonce pour rechercher la chaîne cible et déterminer si une publicité a été utilisée pour acheminer le trafic vers le site. Bien que cela corresponde à la chaîne cible, il correspondrait à deux emplacements et est donc ambigu et peut entraîner des faux positifs.

L’URL suivante contient la publicité sous forme de chaîne à deux endroits différents :

`http://www.abc.com/ad vertnews/today.html?ad =123AZ45`

Par conséquent, si vous essayez de déterminer quelles sessions ont commencé suite à une campagne publicitaire particulière, il est évident que l’utilisation de la publicité littérale comme expression régulière ne suffit pas. Si vous modifiez le littéral en &quot;ad=&quot;, cette ambiguïté disparaîtra et l’expression ne fera qu’une seule correspondance. Cependant, cela peut ne pas suffire à garantir que le référent faisait partie de la campagne de publicité. Examinez le référent suivant :

`http://www.xyz.com/hello.html?pad=something`

Vous n’avez aucun contrôle sur les URL que d’autres utilisateurs peuvent utiliser pour créer des liens vers le site. La correspondance littérale est un mécanisme trop simple pour localiser les sessions qui ont commencé à la suite de la campagne de publicité. La section suivante explique comment utiliser les métacaractères pour une correspondance plus flexible et plus puissante.

## Utilisation de métacaractères {#section-e29a804336304ea1ba33d40d60139aa2}

Un métacaractère est un caractère spécial dans un programme ou un champ de données qui fournit des informations sur d’autres caractères.

| métacharactère | description |
|---|---|
| . (point) | Correspond à un caractère unique, par exemple : `re:x.z` correspond à &quot;xyz&quot; ou &quot;xxz&quot;. |
| * (étoile) | Correspond à un ou plusieurs caractères, par exemple : `re:Z*` correspond à &quot;ZZZ&quot;. |
| ? (caractère générique) | Correspond à 0 ou 1 de l’expression précédente pour forcer une correspondance minimale, par exemple : `xy?z` correspond à &quot;xy&quot; et &quot;xyz&quot;. |

D’autres expressions régulières courantes peuvent également être utilisées pour créer des chaînes de recherche plus complexes.

**Listes, plages et OU**

La correspondance littérale permet de rechercher une seule chaîne, mais les crochets, les tirets et les barres verticales permettent de définir une liste des éléments à rechercher dans la chaîne cible.

<table id="table_18B86955EC3748079E7C176273ADE92B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour ce métacaractère... </th> 
   <th colname="col2" class="entry"> Le processeur d’expression régulière.. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> crochets ([ ]) </td> 
   <td colname="col2"> Faites correspondre n’importe quel caractère du crochet à une seule position de caractère. Par exemple, [AB] est une instruction de correspondance de la lettre A ou de la lettre B et [0123456789] indique qu’une correspondance est établie avec n’importe quel caractère de la plage 0 à 9. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> tiret (-) </td> 
   <td colname="col2"> <p>Faire correspondre une plage de caractères. Ainsi, au lieu d'écrire [0123456789], nous pourrions simplement écrire [0-9]. </p> <p> Cela peut être étendu à des plages de caractères et à plusieurs plages entre crochets. Par exemple, [0-9A-C] correspond aux caractères 0 à 9 et A à C. </p> <p> <p>Remarque :  Pour tester un tiret (-) comme littéral entre crochets, il doit être premier ou dernier. Par exemple, [-0-9] tests pour - et 0 à 9. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tube (|) </td> 
   <td colname="col2"> Faire correspondre l’une des deux options à une chaîne cible donnée. Par exemple, b|nat correspond à bat ou à nat. </td> 
  </tr> 
 </tbody> 
</table>

Prenons les exemples suivants :

| Modèle | Chaîne | Correspond à |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| Leçon`[A-Z]` | Leçon un | Aucune correspondance car a de minuscule n’est pas compris dans la plage de A à Z de majuscule. |

**Négation**

La négation est une manière de dire que vous souhaitez faire correspondre tout ce qui n’est pas les caractères donnés. Le métacaractère de négation, le circonflexe ou le caret (`^`), est utilisé comme premier caractère entre crochets pour dire que vous souhaitez que la correspondance soit autre que les autres caractères entre crochets. Par exemple, pour faire correspondre n’importe quel caractère à l’exception d’un point-virgule (`;`), vous écrivez

[`^;`]

Cela correspondrait à n’importe quel caractère, à l’exception du point-virgule.

**Positionnement**

Pour forcer une correspondance avec le début ou la fin d’une chaîne cible, deux métacaractères sont utilisés.

| Pour ce métacaractère... | Le processeur d’expression régulière.. |
|---|---|
| Circumflex ou accent circonflexe (`^`) | Établit une correspondance par rapport au début de la chaîne. Par exemple, ^`[Tt]`il correspondrait à la chaîne cible &quot;Le début&quot; mais ne correspondrait pas à &quot;C’est le début&quot;. |
| Symbole du dollar (`$`) | Établit une correspondance par rapport à la fin de la chaîne. Par exemple, `[Ee]`nd$ correspondrait à &quot;C’est la fin&quot;, mais pas à &quot;La fin est une heure spéciale&quot;. |

>[!NOTE]
>
>Lorsque l’expression régulière contient ^ au début et $ à la fin, la chaîne cible entière doit correspondre à l’expression régulière.

**Correspondance de tout**

La période (.) est un métacaractère spécial qui correspond à n’importe quel caractère de la chaîne cible. Par exemple, l’expression régulière `^…$` correspond à toute chaîne cible qui comporte exactement trois caractères. L’expression régulière &quot;...&quot; correspond à toute chaîne cible contenant au moins trois caractères.

**Modèles répétés**

Les métacaractères d’itération vous permettent de faire correspondre un modèle plusieurs fois.

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour ce métacaractère... </th> 
   <th colname="col2" class="entry"> Le processeur d’expression régulière.. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Point d’interrogation (?) </td> 
   <td colname="col2"> Ne correspond à aucune instance ou instance du caractère précédant immédiatement le métacaractère (?). Par exemple, le motif rea?d correspond au rouge et à la lecture. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Astérisque (*) </td> 
   <td colname="col2"> Correspondance de zéro ou plusieurs occurrences du caractère précédant immédiatement le métacaractère (*). Par exemple, le modèle [0-9]* correspond à n’importe quel nombre de caractères 0 à 9 (tout entier). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plus (+) </td> 
   <td colname="col2"> Correspondance d’une ou de plusieurs occurrences du caractère ou de la plage précédent. Par exemple, le modèle trois + correspondrait à trois, mais pas à travers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n} </td> 
   <td colname="col2"> <p>Faites correspondre le caractère ou la plage de traitement exactement n fois. Le modèle suivant correspond aux numéros de téléphone des États-Unis : <code>[0-9]{3}-[0-9]{3}-[0-9]{4}</code>. </p> <p> Bien qu’il ne s’agisse pas d’un modèle optimal, il détermine si la chaîne cible est dans le format approprié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n,m} </td> 
   <td colname="col2"> Faites correspondre le caractère précédent au moins n fois et au plus m fois. Par exemple, pour{1,2}d correspondrait à la nourriture et à la nourriture, mais pas à la nourriture. </td> 
  </tr> 
 </tbody> 
</table>

## Extraction de modèle {#section-4389779653b64f6cb7c47615b25c1a79}

La correspondance de motifs n’est qu’une partie de la puissance des expressions régulières. Les expressions régulières offrent également un mécanisme d’extraction des parties clés d’une chaîne cible. Pour ce faire, utilisez les parenthèses gauche et droite. Ces extractions sont généralement utilisées comme entrée dans un autre processus et sont accessibles via l’utilisation de *%position%*, où position est un entier faisant référence au nombre de parenthèses correspondantes.

Examinez les exemples suivants d’extraction de motifs :

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
   <td colname="col4"> %1 % = 95 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> (Win)(95|8) </td> 
   <td colname="col2"> OS=Win98 </td> 
   <td colname="col3"> Win98 </td> 
   <td colname="col4"> <p>%1% = Win </p> <p> %2 % = 98 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mozilla/([0-9]).([0-9]) </td> 
   <td colname="col2"> Mozilla/3.0 </td> 
   <td colname="col3"> Mozilla/3.03 </td> 
   <td colname="col4"> <p>%1% = 3 </p> <p> %2% = 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lesson([A-Z]) </td> 
   <td colname="col2"> Leçon un </td> 
   <td colname="col3"> Aucune correspondance car a de minuscule n’est pas compris dans la plage de A à Z de majuscule </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>
