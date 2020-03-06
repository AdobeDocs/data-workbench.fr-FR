---
description: Une légende de valeur affiche les événements de valeur définis.
solution: Analytics
title: Légendes de valeur
topic: Data workbench
uuid: 7779f442-2f45-4bf8-a62a-585aaceaeb3a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Légendes de valeur{#value-legends}

Une légende de valeur affiche les événements de valeur définis.

La légende de valeur est configurée uniquement dans HBX et dans les applications [!DNL Site] , mais elles peuvent être configurées pour d’autres applications. Pour plus d’informations, contactez les services de conseil Adobe.

Dans HBX et [!DNL Site], un événement de valeur est défini comme une session qui a généré de la valeur commerciale. Par exemple, les enregistrements de données d’événement associés à des pages vues particulières (par exemple, une page de remerciement de commande ou une page de fin de demande) peuvent représenter des événements de valeur pour une entreprise.

Avec les événements de valeur, vous pouvez mesurer et suivre la quantité de valeur générée par le site Web. Vous pouvez évaluer la valeur commerciale en dollars pour chaque événement et répondre à des questions telles que :

* Quel est le chemin le plus rentable à travers le site web ?
* Quel référent ou quelle campagne a généré le plus de valeur ?

Pour chaque événement, la légende affiche la valeur unitaire de l’événement (valeur par événement) et la valeur totale générée par l’événement. Vous utilisez la légende pour définir et modifier des événements de valeur et leur affecter des valeurs unitaires.

Le tableau suivant répertorie les mesures liées aux événements de valeur.

| Mesure | Description |
|---|---|
| Conversion | Pourcentage de sessions qui ont généré une valeur commerciale |
| Valeur | Valeur totale de l&#39;entreprise générée, en dollars |
| Note de qualité Valeur | Valeur commerciale moyenne générée, en dollars, par session |

Vous pouvez facilement définir tout ce que les visiteurs font sur le site Web comme un événement de valeur : publication d’une demande de service à la clientèle, achèvement d’une demande, affichage d’un élément de contenu ou exécution d’un achat. Chaque événement de valeur correspond à un utilisateur accédant à une page ou à un ensemble de pages spécifique du site Web et est associé à une valeur commerciale en dollars. Par exemple, vous pouvez supposer que chaque utilisateur qui accède à la page &quot;Merci d’avoir acheté&quot; génère une marge de contribution de 20 USD en moyenne. Vous pouvez définir un événement de valeur pour cette page dont la valeur est de 20 euros.

## Définir de nouveaux événements de valeur {#section-2ea4d168336e4d2e98b22b636ed43853}

**Pour définir un nouvel événement de valeur dans HBX ou[!DNL Site]**

Lorsque vous créez un événement de valeur, vous faites glisser des pages de site Web représentant une valeur d’une visualisation vers une légende de valeur.

1. Ouvrez une légende de valeur.

   ![](assets/lgd_ValueLegend.png)

1. Ajoutez des événements de valeur à la légende à partir des mappages de processus, des tableaux de pages URI ou des vues de hiérarchie de pages :

   * A partir d’une carte de processus, faites glisser les noeuds de la carte de processus vers la légende.
   * Dans un tableau de page URI, appuyez sur Ctrl+Alt et faites glisser une page du tableau vers la légende.
   * Dans une vue de hiérarchie de page, cliquez à gauche d’un noeud (dossier, page ou groupe) et faites-le glisser sur la légende.
   ![](assets/client-leg.png)

   Le pointeur de la souris affiche le mot &quot;Non&quot; jusqu’à ce que votre souris atteigne la légende.

1. Dans la légende de la valeur, affectez une valeur professionnelle à chaque session pour laquelle l’événement se produit :

   1. Dans la [!DNL Value per Event] colonne, cliquez sur la cellule qui correspond à la page que vous avez ajoutée en tant qu’événement de valeur.
   1. Tapez le montant en euros à affecter à la valeur de cet événement et appuyez sur Entrée.
   ![](assets/lgd_ValueLegend_Value.png)

   Par défaut, l’URL de la page que vous avez définie comme événement de valeur apparaît dans la légende de valeur. Si vous le souhaitez, vous pouvez double-cliquer sur cette URL dans la légende pour passer en mode d’édition et renommer l’événement. Vous pouvez également modifier la valeur d’un événement particulier à tout moment. Le serveur Outils de données recalcule automatiquement les mesures basées sur les événements de valeur, telles que la valeur moyenne et la conversion.

Une fois que vous avez défini au moins un événement de valeur, la dimension Segment de valeur devient disponible pour utilisation. Cette dimension représente la valeur totale générée par un visiteur dans toutes les sessions.

## Supprimer des événements de valeur {#section-25cd90a859384ca183c0fc0998f888cf}

* Cliquez avec le bouton droit de la souris sur l’événement souhaité, puis cliquez sur **[!UICONTROL Delete Event]**.

   ![](assets/lgd_ValueLegend_deleteEvent.png)

>[!NOTE]
>
>Le serveur Outils de données calcule les mesures sur l’ensemble des données accessibles au profil que vous utilisez. Par défaut, le [!DNL Data Workbench Server] calcule des mesures telles que Valeur, Evénements de valeur, Valeur moyenne et Conversion sur toutes les données du jeu de données d’analyse, même si les données ne proviennent pas de la même source logique.

## Exporter vers Microsoft Excel {#section-feaa7a8eb8124fafbc74169bebaed6d8}

Pour plus d’informations sur l’exportation de fenêtres, voir [Exportation de données](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)de fenêtre.
