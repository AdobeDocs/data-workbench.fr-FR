---
description: Informations sur l'évaluation et la surveillance du chargement de l'espace d'adressage.
solution: Insight
title: Surveillance de l’utilisation de la mémoire
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Surveillance de l’utilisation de la mémoire{#monitoring-memory-usage}

Informations sur l&#39;évaluation et la surveillance du chargement de l&#39;espace d&#39;adressage.

**Surveillance du chargement de l&#39;espace d&#39;adressage**

**Fréquence recommandée :** Quotidien

La charge de l&#39;espace d&#39;adressage est une mesure de la fraction de l&#39;espace d&#39;adressage maximum qu&#39;un [!DNL Insight Server] utilisateur correctement configuré utilise. Même si les paramètres de configuration sont modifiés pour réduire l’utilisation de la mémoire, il ne diminue généralement pas tant que le [!DNL Insight Server] service n’est pas redémarré.

Une marge de sécurité est intégrée dans la charge maximale de l&#39;espace d&#39;adressage pour tenir compte des augmentations inattendues de l&#39;utilisation de l&#39;espace d&#39;adressage. Vous ne devriez jamais sciemment réduire cette marge de sécurité. Il existe pour les situations d’urgence et non pour la prise en charge des fonctionnalités ajoutées à votre application Adobe.

>[!NOTE]
>
>Pour libérer plus d&#39;espace d&#39;adressage et éviter les erreurs d&#39;épuisement de mémoire, assurez-vous que le commutateur /3GB est activé sur votre système d&#39;exploitation et que le tas de faible fragmentation fonctionne.

Les erreurs consignées dans le journal des données [!DNL Insight Server] d’événement peuvent fournir un indice indiquant que des problèmes se développent avec votre chargement d’espace d’adressage :

* Les erreurs &quot;Le bloc d’octets X demandé est trop volumineux&quot; indiquent qu’un problème peut avoir un impact excessif sur la charge, les performances et la bande passante réseau de l’espace d’adressage. De tels blocs importants peuvent grandement contribuer à l&#39;utilisation de l&#39;espace d&#39;adressage, à la fois en utilisant beaucoup de mémoire et en exigeant de grands blocs contigus d&#39;espace d&#39;adressage.

   Pour résoudre ce problème, vous pouvez réduire la cardinalité de vos plus grandes dimensions, ce qui augmente la charge de votre espace d&#39;adressage. Si vous ne parvenez pas à réduire la cardinalité des dimensions, vous devez tenter de maintenir la charge de l&#39;espace d&#39;adressage suffisamment petite pour pouvoir gérer une augmentation inattendue.
* Les erreurs &quot;Budget mémoire dépassé&quot; indiquent que vous devrez peut-être augmenter la limite de mémoire de requête. La mémoire utilisée par les requêtes est proportionnelle à la cardinalité des dimensions et, dans certains cas, à la longueur des noms d’élément. Si vous augmentez la limite de mémoire de requête, vous augmentez la charge totale de l&#39;espace d&#39;adressage et réduisez les grandes dimensions.

>[!NOTE]
>
>Par défaut, l’utilisation de pages volumineuses est autorisée et la recherche mappée en mémoire est désactivée. Dans DWB 6.7 et les versions ultérieures, il est possible de modifier la configuration des jeux de données. Toute modification nécessite un redémarrage du serveur.

**Pour évaluer la charge de l’espace d’adressage**

Pour évaluer précisément la charge de l’espace d’adressage pour votre système, Adobe recommande de retraiter le jeu de données, d’exécuter certaines requêtes normales sans redémarrer ultérieurement [!DNL Insight Server], puis d’afficher la charge mesurée de l’espace d’adressage en procédant comme suit.

Si un [!DNL Insight Server] objet n’a pas été retraité et interrogé de manière significative depuis son dernier redémarrage, vous ne devez pas tirer de conclusions à partir de la charge de l’espace d’adressage.

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** vignette pour ouvrir l’espace de travail Gestionnaire de serveurs.
1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] fichier à configurer, puis cliquez sur **[!UICONTROL Detailed Status]**.
1. Dans l’interface Etat détaillé, cliquez sur **[!UICONTROL Memory Status]** pour en afficher le contenu. Dans le paramètre Chargement de l&#39;espace d&#39;adressage, vous pouvez voir la charge de l&#39;espace d&#39;adressage exprimée sous forme de pourcentage et d&#39;une description entre parenthèses indiquant l&#39;état.

   Le tableau suivant présente les plages et l’état de la charge de l’espace d’adressage. Une action recommandée est répertoriée pour chaque plage.

   | Chargement de l&#39;espace d&#39;adressage (%) | État | Action recommandée |
   |---|---|---|
   | 0-15 | maigre et moyenne | Aucun. |
   | 15-33 | lumière | Aucun. |
   | 33-66 | modéré | Aucun. |
   | 66-100 | lourd | Pour éviter les échecs d’épuisement de la mémoire, n’ajoutez pas de fonctionnalités supplémentaires importantes ou tentez de traiter davantage de données. |
   | 100-125 | fiabilité compromise | Ajustez la configuration de votre jeu de données pour réduire la charge de l’espace d’adressage. |
   | 125 ou plus | échec imminent | Ajustez la configuration de votre jeu de données pour réduire la charge de l’espace d’adressage. Il se peut que vous ne voyiez pas l’état imminent de l’échec avant qu’il ne se produise. |

   Si la charge de l&#39;espace d&#39;adressage est supérieure à 100 %, vous devez modifier la configuration le plus tôt possible afin de réduire l&#39;utilisation de l&#39;espace d&#39;adressage.

