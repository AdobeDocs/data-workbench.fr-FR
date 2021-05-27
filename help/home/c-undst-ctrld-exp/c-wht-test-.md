---
description: Les résultats des tests doivent être clairs et significatifs afin que vous puissiez vous sentir confiant dans la prise de décisions importantes basées sur ces résultats.
solution: Analytics,Analytics
title: Que dois-je tester ?
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
exl-id: 0f06ff0f-b385-4614-8007-afdb85191a85
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---

# Que dois-je tester ?{#what-should-i-test}

Les résultats des tests doivent être clairs et significatifs afin que vous puissiez vous sentir confiant dans la prise de décisions importantes basées sur ces résultats.

Bien que vous puissiez tester différentes mises en page avec [!DNL Sensor] et Site, Adobe vous suggère de vous concentrer sur le test d’initiatives commerciales stratégiques à forte valeur ajoutée ou sur la nouvelle ou reconception de fonctionnalités de site web qui répondent aux objectifs que vous avez définis pour votre site web et votre entreprise. Vous pouvez tester des problèmes tels que les meilleures garanties de prix, les fonctionnalités de personnalisation, les offres de marché (par exemple, les packages ou les lots), la conception créative et les processus d’application.

Les concepts suivants sont les plus importants lors du développement de votre expérience contrôlée :

* **Découvrez les modifications à apporter.** Cela nécessite des recherches sur le fonctionnement de votre site web et les processus métier sous-jacents du site web front-end. Vous souhaitez apporter des modifications qui ont le plus d’impact et qui peuvent être testées facilement.
* **De petits changements peuvent avoir un impact significatif.** Toutes les modifications que vous testez ne doivent pas être drastiques pour avoir un impact significatif sur votre entreprise. Soyez toujours ouvert à des changements petits mais très importants.

## Méthodologies prises en charge {#section-1071adaf54c64ba9bc5ef228c4a23635}

De nombreux types d’expériences avec de nombreux objectifs différents peuvent être effectués à l’aide de Site. La liste suivante fournit quelques exemples :

* Modifier les processus des pages, du contenu et du site web afin d’améliorer les taux de conversion.
* Modification des campagnes marketing, des promotions, des ventes croisées et des ventes incitatives pour augmenter les recettes.
* Variation du temps de chargement des pages pour comprendre la qualité du service client et la valeur réelle des performances de l’infrastructure.

Pour atteindre ces objectifs, Site prend en charge les types de méthodologies suivants pour l’expérimentation et le test contrôlés :

* **Remplacement de page :** remplacez l’URL statique X par l’URL statique Y. Cette méthodologie est d’une utilité limitée dans un environnement dynamique.
* **Remplacement URI dynamique :**  il s’agit d’une variante de remplacement de page qui remplace la page statique X par la page dynamique Y pour effectuer le rendu du contenu dynamique.
* **Remplacement d’objet :** remplacez l’objet fixe X par l’objet fixe Y.
* **Remplacement de contenu :** remplacez le jeu de contenu X (plusieurs objets, pages, tableau, etc.) par le jeu de contenu Y.
* **Remplacement de variable d’expérience :** remplacez l’objet JavaScript /writeCookie_X.js par l’objet JavaScript /writeCookie_Y.js pour écrire un cookie qui peut être utilisé par un système principal pour diffuser du contenu particulier.

>[!NOTE]
>
>Les expériences contrôlées sont basées sur le remplacement d’URI, et non sur le remplacement de chaînes de requête. L’URI d’une URL spécifique est surligné dans l’exemple suivant :
>
>`http://www.omniture.com/index.asp?id=1`
>
>Par exemple, dans votre expérience contrôlée, vous pouvez spécifier que l’URI de la population témoin [!DNL index.asp] soit remplacé par l’URI du groupe de test [!DNL index2.asp] pour déterminer quelle conception de page entraînerait une plus grande valeur.
