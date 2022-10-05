---
description: Informations sur l’évaluation et la surveillance du chargement de l’espace-adresse.
title: Surveillance de l’utilisation de la mémoire
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
exl-id: b8c0b33b-dbec-4947-911b-11c8a83bbc9c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 2%

---

# Surveillance de l’utilisation de la mémoire{#monitoring-memory-usage}

{{eol}}

Informations sur l’évaluation et la surveillance du chargement de l’espace-adresse.

**Surveillance du chargement de l’espace d’adresse**

**Fréquence recommandée :** Quotidien

La charge de l’espace d’adresse est une mesure de la fraction de l’espace d’adresse maximum configuré correctement. [!DNL Insight Server] utilise . Même si les paramètres de configuration sont modifiés pour réduire l’utilisation de la mémoire, il ne diminue généralement pas avant que la fonction [!DNL Insight Server] Le service est redémarré.

Une marge de sécurité est incluse dans le maximum de charge de l’espace d’adresse afin de tenir compte des augmentations inattendues de l’utilisation de l’espace d’adresse. Vous ne devriez jamais sciemment réduire cette marge de sécurité. Il existe pour les situations d’urgence et non pour la prise en charge des fonctionnalités ajoutées à votre application d’Adobe.

>[!NOTE]
>
>Pour rendre plus d’espace d’adresse disponible et éviter les erreurs d’épuisement de la mémoire, vérifiez que le commutateur /3GB est activé sur votre système d’exploitation et que le segment de faible fragmentation fonctionne.

Erreurs consignées dans la variable [!DNL Insight Server] Le journal des données d’événement peut fournir un indice indiquant que les problèmes se développent avec votre charge d’espace d’adresse :

* Les erreurs &quot;Le bloc d’octets X demandé est trop volumineux&quot; indiquent qu’un problème peut avoir un impact excessif sur la charge de l’espace d’adresse, les performances et la bande passante du réseau. De tels blocs de grande taille peuvent contribuer grandement à l’utilisation de l’espace réservé, à la fois en utilisant beaucoup de mémoire et en nécessitant de grands blocs contigus d’espace réservé.

   Pour résoudre ce problème, vous pouvez réduire la cardinalité de vos plus grandes dimensions, ce qui augmente la charge de votre espace d’adresse. Si vous ne pouvez pas réduire la cardinalité des dimensions, vous devez essayer de maintenir la charge de l’espace d’adresse suffisamment petite pour pouvoir gérer une augmentation inattendue.
* Les erreurs &quot;budget mémoire dépassé&quot; indiquent que vous devrez peut-être augmenter la limite de mémoire de la requête. La mémoire utilisée par les requêtes est proportionnelle à la cardinalité des dimensions et, dans certains cas, à la longueur des noms des éléments. Si vous augmentez la limite de mémoire de requête, vous augmentez la charge totale de l’espace d’adresse et réduisez les grandes dimensions.

>[!NOTE]
>
>Par défaut, l’utilisation de pages volumineuses est autorisée et la recherche mappée en mémoire est désactivée. Dans DWB 6.7 et versions ultérieures, cela peut être modifié dans la configuration des jeux de données. Toute modification nécessite un redémarrage du serveur.

**Évaluation de la charge de l’espace des adresses**

Pour évaluer précisément la charge d’espace d’adresse de votre système, Adobe recommande de retraiter le jeu de données, en effectuant certaines requêtes normales sans redémarrer par la suite. [!DNL Insight Server], puis visualisez la charge mesurée de l’espace d’adresse en procédant comme suit.

Si [!DNL Insight Server] n’a pas été retraité et interrogé de manière significative depuis son dernier redémarrage, vous ne devez pas tirer de conclusions à partir de la charge d’espace d’adresse.

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .
1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] vous souhaitez configurer et cliquer sur **[!UICONTROL Detailed Status]**.
1. Dans l’interface de statut détaillé, cliquez sur **[!UICONTROL Memory Status]** pour afficher son contenu. Dans le paramètre Chargement de l’espace d’adresse , vous pouvez voir le chargement de l’espace d’adresse exprimé en pourcentage et une description entre parenthèses indiquant l’état.

   Le tableau suivant présente les plages et l’état du chargement de l’espace d’adresse. Une action recommandée est répertoriée pour chaque plage.

   | Chargement de l’espace d’adresse (%) | État | Action recommandée |
   |---|---|---|
   | 0 à 15 | lean and mean | Aucun. |
   | 15-33 | light | Aucun. |
   | 33-66 | modérer | Aucun. |
   | 66-100 | lourd | Pour éviter les échecs d’épuisement de la mémoire, n’ajoutez pas de fonctionnalités supplémentaires importantes ou ne tentez pas de traiter plus de données. |
   | 100-125 | fiabilité compromise | Ajustez la configuration de votre jeu de données pour réduire la charge de l’espace d’adresse. |
   | 125 ou plus | échec imminent | Ajustez la configuration de votre jeu de données pour réduire la charge de l’espace d’adresse. Il se peut que vous ne voyiez pas l’état imminent d’échec avant l’échec. |

   Si vous voyez une charge d’espace d’adresse supérieure à 100 %, vous devez modifier la configuration dès que possible afin de réduire l’utilisation de l’espace d’adresse.
