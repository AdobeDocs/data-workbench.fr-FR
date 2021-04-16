---
description: Les résultats des tests doivent être clairs et significatifs afin que vous puissiez vous sentir confiant dans la prise de décisions importantes en fonction de ces résultats.
solution: Analytics,Analytics
title: Que dois-je tester ?
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
exl-id: 0f06ff0f-b385-4614-8007-afdb85191a85
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---

# Que dois-je tester ?{#what-should-i-test}

Les résultats des tests doivent être clairs et significatifs afin que vous puissiez vous sentir confiant dans la prise de décisions importantes en fonction de ces résultats.

Bien que vous puissiez tester différentes mises en page avec [!DNL Sensor] et le site, l&#39;Adobe vous suggère de vous concentrer sur les tests d&#39;initiatives stratégiques à forte valeur ajoutée ou sur la mise en page de fonctionnalités de site Web nouvelles ou remaniées qui répondent aux objectifs que vous avez définis pour votre site Web et votre entreprise. Vous pouvez tester des problèmes tels que les meilleures garanties de prix, la fonctionnalité de personnalisation, les offres du marché (par exemple, les packs ou les lots), la conception créative et les processus d’application.

Les concepts suivants sont les plus importants lors du développement de votre expérience contrôlée :

* **Comprenez les modifications à apporter.** Pour ce faire, vous devez effectuer des recherches sur le fonctionnement de votre site Web et sur les processus d’entreprise sous-jacents au site Web principal. Vous souhaitez apporter des modifications qui produisent le plus d&#39;impact et qui peuvent être testées facilement.
* **De petits changements peuvent avoir un impact significatif.** Toutes les modifications que vous testez ne doivent pas nécessairement être drastiques pour avoir un impact significatif sur votre activité. Soyez toujours ouvert à des changements petits mais très importants.

## Méthodologies prises en charge {#section-1071adaf54c64ba9bc5ef228c4a23635}

De nombreux types d&#39;expériences avec de nombreux objectifs différents peuvent être effectuées à l&#39;aide du site. La liste suivante fournit quelques exemples :

* Modification des processus des pages, du contenu et du site Web pour améliorer les taux de conversion.
* Modification des campagnes marketing, des promotions, des ventes croisées et des ventes consécutives afin d’augmenter les recettes.
* Variation du temps de chargement des pages pour comprendre la qualité du service client et la valeur réelle des performances de l’infrastructure.

Pour atteindre ces objectifs, Site prend en charge les types suivants de méthodologies d&#39;expérimentation et de test contrôlés :

* **Remplacement de page :** remplacez l’URL statique X par l’URL statique Y. Cette méthodologie est d’une utilité limitée dans un environnement dynamique.
* **Remplacement d’URI dynamique :** il s’agit d’une variante de Remplacement de page qui remplace la page statique X par la page dynamique Y pour générer du contenu dynamique.
* **Remplacement d’objet :** remplacez l’objet fixe X par l’objet fixe Y.
* **Remplacement du contenu :** remplacez le jeu de contenu X (plusieurs objets, pages, tableau, etc.) par le jeu de contenu Y.
* **Remplacement des variables d’expérience :** remplacez l’objet JavaScript /writeCookie_X.js par l’objet JavaScript /writeCookie_Y.js pour écrire un cookie qui peut être utilisé par un système principal pour diffuser un contenu particulier.

>[!NOTE]
>
>Les expériences contrôlées sont basées sur le remplacement d&#39;URI, et non sur le remplacement de chaînes de requête. L’URI d’une URL particulière est surligné dans l’exemple suivant :
>
>`http://www.omniture.com/index.asp?id=1`
>
>Par exemple, dans votre expérience contrôlée, vous pouvez spécifier que l&#39;URI de Population témoin [!DNL index.asp] soit remplacé par l&#39;URI de groupe de tests [!DNL index2.asp] pour déterminer quelle conception de page donnerait plus de valeur.
