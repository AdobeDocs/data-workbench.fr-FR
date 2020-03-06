---
description: Les résultats des tests doivent être clairs et significatifs afin que vous puissiez vous sentir confiant dans la prise de décisions importantes en fonction de ces résultats.
solution: Insight,Analytics
title: Que Dois-Je Tester ?
topic: Data workbench
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# What Should I Test?{#what-should-i-test}

Les résultats des tests doivent être clairs et significatifs afin que vous puissiez vous sentir confiant dans la prise de décisions importantes en fonction de ces résultats.

Bien que vous puissiez tester diverses mises en page avec [!DNL Sensor] et le site, Adobe vous conseille de vous concentrer sur le test d’initiatives commerciales stratégiques de grande valeur ou sur la fonctionnalité de site Web nouvelle ou repensée qui répond aux objectifs que vous avez définis pour votre site Web ainsi que pour votre entreprise. Vous pouvez tester des problèmes tels que les meilleures garanties de prix, la fonctionnalité de personnalisation, les offres de marché (par exemple, les packs ou les lots), la conception créative et les processus d’application.

Les concepts suivants sont les plus importants lors du développement de votre expérience contrôlée :

* **Comprenez les bonnes modifications à apporter.** Pour ce faire, vous devez effectuer des recherches sur le fonctionnement de votre site Web et sur les processus opérationnels qui sous-tendent le site Web principal. Vous souhaitez apporter des modifications qui produisent le plus d’impact et qui peuvent être testées facilement.
* **De petits changements peuvent avoir un impact significatif.** Toutes les modifications que vous testez ne doivent pas nécessairement être drastiques pour avoir un impact significatif sur votre activité. Soyez toujours ouvert à des changements petits, mais très importants.

## Méthodologies prises en charge {#section-1071adaf54c64ba9bc5ef228c4a23635}

De nombreux types d&#39;expériences avec de nombreux objectifs différents peuvent être effectuées à l&#39;aide du site. Voici quelques exemples :

* Modification des processus des pages, du contenu et du site Web pour améliorer les taux de conversion.
* Modification des campagnes marketing, des promotions, des ventes croisées et des ventes consécutives afin d’augmenter les recettes.
* Variation du temps de chargement des pages pour comprendre la qualité du service client et la valeur réelle des performances de l’infrastructure.

Pour atteindre ces objectifs, le site prend en charge les types de méthodologies suivants pour l’expérimentation et les tests contrôlés :

* **Remplacement de page :** Remplacez l’URL statique X par l’URL statique Y. Cette méthodologie est d&#39;une utilité limitée dans un environnement dynamique.
* **Remplacement dynamique des URI :** Il s’agit d’une variante de Remplacement de page qui remplace la page statique X par la page dynamique Y pour rendre le contenu dynamique.
* **Remplacement d’objet :** Remplacez l’objet fixe X par l’objet fixe Y.
* **Remplacement de contenu :** Remplacez le jeu de contenu X (plusieurs objets, pages, tableau, etc.) par le jeu de contenu Y.
* **Remplacement de la variable d’expérience :** Remplacez l’objet JavaScript /writeCookie_X.js par l’objet JavaScript /writeCookie_Y.js pour créer un cookie qui peut être utilisé par un système principal pour diffuser un contenu particulier.

>[!NOTE]
>
>Les expériences contrôlées sont basées sur le remplacement d&#39;URI, et non sur le remplacement de chaînes de requête. L’URI d’une URL spécifique est surligné dans l’exemple suivant :
>
>`http://www.omniture.com/index.asp?id=1`
>
>Par exemple, dans votre expérience contrôlée, vous pouvez spécifier que l’URI du groupe de contrôle [!DNL index.asp] soit remplacé par l’URI du groupe de test [!DNL index2.asp] afin de déterminer quelle conception de page générerait plus de valeur.
