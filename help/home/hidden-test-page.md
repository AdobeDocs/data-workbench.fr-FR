---
title: Page de test masqué
description: Cette page est masquée de la recherche et de la table des matières
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
exl-id: 25669153-b90c-4cf6-81aa-cabcbf2cbcb6
source-git-commit: 7f138d3a9372bc6662d1d54a2d026474a5eb8446
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 4%

---

# Page de test masqué

## Types de remarque


Tous les types de notes pris en charge.

>[!NOTE]
>
>This is a standard NOTE block.

>[!TIP]
>
>This is a standard tip.

>[!IMPORTANT]
>
>C&#39;est une note importante.

>[!WARNING]
>
>C&#39;est un avertissement.

>[!CAUTION]
>
>C&#39;est une mise en garde.

>[!ADMIN]
>
>Ceci est une note de l’administrateur. EXL uniquement.

>[!ADMINISTRATION]
>
>Il s’agit d’une note d’administration. EXL uniquement.

>[!AVAILABILITY]
>
>Ceci est une note de disponibilité. EXL uniquement.

>[!PREREQUISITES]
>
>Il s’agit d’une note Conditions préalables. EXL uniquement.

>[!INFO]
>
>Il s’agit d’une note d’informations. EXL uniquement.

>[!ERROR]
>
>Il s’agit d’une note d’erreur. EXL uniquement.

>[!SUCCESS]
>
>Il s’agit d’une note de réussite. EXL uniquement.

>[!MORELIKETHIS]
>
>* Page 1
>* Page 2


## Badges

Un badge est un libellé coloré utilisé comme indicateur de contenu. Par exemple, vous pouvez ajouter un badge pour marquer un article comme _Beta_ ou une section comme _Premium_. Vous pouvez modifier la couleur d’un badge et associer une URL et une info-bulle.

[!BADGE Exemple de badge]

Il existe deux types de badges, chacun avec une syntaxe différente :

* **Métadonnées** - Affiche le badge près du haut d’une page.
* **En ligne** - Affiche le badge contenant la syntaxe

### Badges de métadonnées

L’ajout de la syntaxe du badge dans les métadonnées place un badge au-dessus du titre de la page (H1) dans l’article.

Vous pouvez nommer des badges à l’aide de _badge1_ ou _badge2_. Vous pouvez également être plus créatif (à condition que le nom commence par _badge_).

Exemples de métadonnées :

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium :** Cet exemple affiche un badge Premium avec une URL et une info-bulle.

* **badgeExam :** Cet exemple affiche un badge sombre avec un numéro d’ID d’examen.

#### Badges en ligne

Indiquez les informations du badge sur sa propre ligne ou dans un en-tête, un tableau ou un autre élément de page.

Voici la syntaxe d’un badge inséré avec un libellé bêta, une couleur bleue, une URL et une info-bulle :

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### Couleurs de badge disponibles

Les badges utilisent des couleurs définies dans Adobe Spectrum :

| Type | Badge |
|---|---|
| Informatif (par défaut) | [!BADGE Version bêta]{type=Informative url="https://www.example.com"} |
| Positive | [!BADGE Nouvelle fonctionnalité]{type=Positive url="https://www.example.com" tooltip="Accédez à example.com"} |
| Négative | [!BADGE Arrêt]{type=negative tooltip="Cette fonctionnalité est désormais en fin de vie."} |
| Indifférente | [!BADGE Cela dépend]{type=Neutral tooltip="Un cavalier tomba du cheval..."} |
| Attention | [!BADGE Attention]{type=Caution tooltip="État jaune"} |

Exemples de syntaxe

```
|Type|Badge|
|---|---|
|Informative (default)|[!BADGE Beta]{type=Informative url="https://www.example.com"}|
|Positive|[!BADGE New Feature]{type=Positive url="https://www.example.com" tooltip="Go to example.com"}|
|Negative|[!BADGE Discontinued]{type=negative tooltip="This feature is now end of life"}|
|Neutral|[!BADGE Maybe]{type=Neutral tooltip="A rider fell off the horse..."}|
|Caution|[!BADGE Attention]{type=Caution tooltip="Yellow status"}|
```

### Conditions requises pour les badges

* Seuls deux badges sont autorisés dans les métadonnées. Cette règle est configurable. Indiquez donc si vous avez besoin d’une exception.
* Seul le libellé du badge est requis. Le `type`, `url`, et `tooltip` sont facultatifs. Le `type` détermine la couleur. Le `url` permet aux utilisateurs de cliquer sur le badge pour ouvrir un article ou une page. Le `tooltip` affiche le texte de l’info-bulle lorsque vous pointez dessus.
* Ajouter un badge au `TOC.md` affiche le badge sur chaque article du guide. Si vous spécifiez une URL pour le badge afin d’accéder à un article, veillez à utiliser un lien racine (par exemple, `/help/guide/article.md`) n’est pas un lien relatif (par exemple, `article.md`) pour tenir compte des articles dans différents dossiers.
* Ajouter un badge à `metadata-new.md` affiche le badge sur chaque article dans un référentiel.
* Pour les badges de métadonnées, assurez-vous que toutes les valeurs sont entourées de guillemets. Pour les badges intégrés, assurez-vous que `url` et `tooltip` sont entourés de guillemets.
* Les valeurs de type valides sont les suivantes : *Informatif* (par défaut, bleu), *Positif* (vert), *Négatif* (rouge), *Neutral* (gris foncé) et *Attention* (jaune).
* Les libellés de badge sont localisés.
* Si plusieurs badges de métadonnées sont spécifiés, ils s’affichent par ordre alphabétique en fonction du nom du badge, tel que `badge1:` ou `badgeWeb`.
* Si vous souhaitez que l’URL s’ouvre dans un nouvel onglet, utilisez la syntaxe suivante :

   ```
   [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
   ```

   Généré:

   [!BADGE Ouvrir dans un nouvel onglet]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Ouvrir adobe.com dans un nouvel onglet"}

## Mise en surbrillance de texte

L’équipe Workfront a demandé à pouvoir utiliser la mise en surbrillance jaune pour indiquer l’aperçu des fonctionnalités à venir. Voici comment ça marche.

Exemple 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

Généré:

Ce paragraphe entier ne doit PAS être mis en surbrillance. <span class="preview"> Ce mot est **gras** dans une phrase surlignée.</span> Et ceci n&#39;est que la dernière phrase.

Exemple 2:

```
Highlighting should start after this paragraph.

<div class="preview">

Start of DIV.

This is a new paragraph, then an image

![image](/help/home/assets/analytics-icon-24.png)

Last highlighted item.

</div>

Not highlighted
```

Généré:

La mise en surbrillance doit commencer après ce paragraphe.

<div class="preview">

Début de DIV.

Il s’agit d’un nouveau paragraphe, puis d’une image.

![image](/help/home/assets/analytics-icon-24.png)

Dernier élément en surbrillance.

</div>

Non surligné

## Mise en surbrillance de syntaxe pour les blocs de code

Experience League prend en charge la mise en surbrillance de la syntaxe pour les blocs de code. Veillez à spécifier une langue telle que `java` après l’ensemble d’ouverture des apostrophes ouvrantes pour vous assurer que la syntaxe est correctement mise en surbrillance. Pour obtenir la liste des langues valides, voir [https://prismjs.com](https://prismjs.com/#supported-languages). Si des langues sont manquantes, veuillez enregistrer un ticket jira.

### Numérotation des lignes dans les blocs de code

Ajouter `{line-numbers="true"}` après la langue pour activer la numérotation des lignes.

Exemple avec des numéros de ligne (&grave;&grave;&grave;`html {line-numbers="true"}`) :

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**Commencer la numérotation sur la ligne _**

Ajouter `start-number="n"` après la syntaxe du numéro de ligne pour commencer la numérotation sur un numéro autre que 1.

Exemple avec une nouvelle ligne de départ (&grave;&grave;&grave;`html {line-numbers="true" start-line="7"}`) :

```html {line-numbers="true" start-line="7"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```

### Mise en surbrillance des lignes dans les blocs de code

Ajouter `highlight="n"` après la syntaxe du numéro de ligne pour mettre en surbrillance les lignes dans un bloc de code. Spécification `11-13, 16` mettra en évidence les lignes 11 à 13 et 16.

Exemple avec mise en surbrillance de ligne (&grave;&grave;&grave;`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`) :

```html {line-numbers="true" start-line="7" highlight="11-13, 16"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```
