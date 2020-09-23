---
description: Informations sur l'évaluation et la surveillance du chargement de l'espace d'adressage.
solution: Analytics
title: Surveillance de l’utilisation de la mémoire
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 2%

---


# Surveillance de l’utilisation de la mémoire{#monitoring-memory-usage}

Informations sur l&#39;évaluation et la surveillance du chargement de l&#39;espace d&#39;adressage.

**Surveillance du chargement de l&#39;espace d&#39;adressage**

**Fréquence recommandée :** Quotidien

La charge de l&#39;espace d&#39;adressage est une mesure de la fraction de l&#39;espace d&#39;adressage maximum qu&#39;un [!DNL Insight Server] utilisateur correctement configuré utilise. Même si les paramètres de configuration sont modifiés pour réduire l&#39;utilisation de la mémoire, ils ne diminuent généralement pas tant que le [!DNL Insight Server] service n&#39;est pas redémarré.

Une marge de sécurité est intégrée dans la charge maximale de l&#39;espace d&#39;adressage pour tenir compte des augmentations inattendues de l&#39;utilisation de l&#39;espace d&#39;adressage. Vous ne devriez jamais sciemment réduire cette marge de sécurité. Il existe pour les situations d&#39;urgence et non pour la prise en charge des fonctionnalités ajoutées à votre application d&#39;Adobe.

>[!NOTE]
>
>Pour libérer plus d&#39;espace d&#39;adressage et éviter les erreurs d&#39;épuisement de la mémoire, assurez-vous que le commutateur /3GB est activé sur votre système d&#39;exploitation et que le tas de faible fragmentation fonctionne.

Les erreurs consignées dans le journal de données du [!DNL Insight Server] événement peuvent fournir un indice indiquant que des problèmes se développent avec votre chargement d&#39;espace d&#39;adressage :

* Les erreurs &quot;Le bloc d’octets X demandé est trop volumineux&quot; indiquent qu’un problème peut avoir un impact excessif sur la charge, les performances et la bande passante du réseau de l’espace d’adressage. De tels blocs peuvent grandement contribuer à l&#39;utilisation de l&#39;espace d&#39;adressage, à la fois en utilisant beaucoup de mémoire et en exigeant de grands blocs contigus d&#39;espace d&#39;adressage.

   Pour résoudre ce problème, vous pouvez réduire la cardinalité de vos plus grandes dimensions, ce qui augmente la charge de votre espace d&#39;adressage. Si vous ne pouvez pas réduire la cardinalité des dimensions, vous devez essayer de maintenir la charge de l&#39;espace d&#39;adressage suffisamment petite pour que vous puissiez gérer une augmentation inattendue.
* Les erreurs &quot;Budget mémoire dépassé&quot; indiquent que vous devrez peut-être augmenter la limite de mémoire de Requête. La mémoire utilisée par les requêtes est proportionnelle à la cardinalité des dimensions et, dans certains cas, à la longueur des noms d’éléments. Si vous augmentez la limite de mémoire de Requête, vous augmentez la charge totale de l&#39;espace d&#39;adressage et réduisez les dimensions importantes.

>[!NOTE]
>
>Par défaut, l’utilisation de pages volumineuses est autorisée et la recherche mappée sur la mémoire est désactivée. Dans DWB 6.7 et les versions ultérieures, il est possible de modifier cette configuration dans le jeu de données. Toute modification nécessite un redémarrage du serveur.

**Pour évaluer la charge d&#39;espace d&#39;adressage**

Pour évaluer précisément la charge de l&#39;espace d&#39;adressage pour votre système, l&#39;Adobe recommande de retraiter le jeu de données, d&#39;exécuter certaines requêtes normales sans redémarrer ultérieurement [!DNL Insight Server], puis d&#39;afficher la charge mesurée de l&#39;espace d&#39;adressage en procédant comme suit.

Si un [!DNL Insight Server] objet n&#39;a pas été retraité et interrogé de manière significative depuis son dernier redémarrage, vous ne devriez pas tirer de conclusions à partir de la charge d&#39;espace d&#39;adressage.

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Servers Manager.
1. Cliquez avec le bouton droit de la souris sur l’icône de la [!DNL Insight Server] fenêtre à configurer, puis cliquez sur **[!UICONTROL Detailed Status]**.
1. Dans l’interface Statut détaillé, cliquez sur **[!UICONTROL Memory Status]** pour en vue le contenu. Dans le paramètre Charge de l&#39;espace d&#39;adressage, vous pouvez voir la charge de l&#39;espace d&#39;adressage exprimée en pourcentage et une description entre parenthèses indiquant l&#39;état.

   Le tableau suivant présente les plages et l’état du chargement de l’espace d’adressage. Une action recommandée est répertoriée pour chaque plage.

   | Chargement de l&#39;espace d&#39;adressage (%) | État | Action recommandée |
   |---|---|---|
   | 0-15 | maigre et moyenne | Aucun. |
   | 15-33 | light | Aucun. |
   | 33-66 | modéré | Aucun. |
   | 66-100 | lourd | Pour éviter les échecs d’épuisement de la mémoire, n’ajoutez pas de fonctionnalités supplémentaires importantes ou tentez de traiter davantage de données. |
   | 100-125 | fiabilité compromise | Ajustez la configuration de votre jeu de données pour réduire la charge de l&#39;espace d&#39;adressage. |
   | 125 ou plus | échec imminent | Ajustez la configuration de votre jeu de données pour réduire la charge de l&#39;espace d&#39;adressage. Il se peut que vous ne voyiez pas l&#39;état imminent de l&#39;échec avant que l&#39;échec ne se produise. |

   Si vous voyez une charge d&#39;espace d&#39;adressage supérieure à 100 %, vous devez modifier la configuration dès que possible afin de réduire l&#39;utilisation de l&#39;espace d&#39;adressage.

