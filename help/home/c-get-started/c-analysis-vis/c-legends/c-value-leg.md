---
description: Une légende de valeur affiche les événements de valeur définis.
title: Légendes de valeur
uuid: 7779f442-2f45-4bf8-a62a-585aaceaeb3a
exl-id: b28ba604-93ef-4081-ae55-937fb537c068
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 2%

---

# Légendes de valeur{#value-legends}

{{eol}}

Une légende de valeur affiche les événements de valeur définis.

La légende des valeurs n’est configurée que dans l’HBX et [!DNL Site] , mais elles peuvent être configurées pour d’autres applications. Pour plus d’informations, contactez les Services de conseil Adobe.

Dans HBX et [!DNL Site], un événement value est défini comme une session qui a généré une valeur commerciale. Par exemple, les enregistrements de données d’événement associés à des pages vues spécifiques (par exemple, une page de remerciement pour une commande ou une page de fin d’application) peuvent représenter des événements de valeur pour une entreprise.

Avec les événements de valeur, vous pouvez mesurer et suivre la quantité de valeur générée par le site web. Vous pouvez évaluer la valeur commerciale en dollars pour chaque événement et répondre à des questions telles que :

* Quel est le chemin le plus rentable à travers le site web ?
* Quel référent ou campagne a généré le plus de valeur ?

Pour chaque événement, la légende affiche la valeur unitaire de l’événement (valeur par événement) et la valeur totale générée par l’événement. Vous utilisez la légende pour définir et modifier des événements de valeur et leur attribuer des valeurs unitaires.

Le tableau suivant répertorie les mesures liées aux événements de valeur.

| Mesure | Description |
|---|---|
| Conversion | Pourcentage de sessions qui ont généré de la valeur commerciale |
| Valeur | Valeur commerciale totale générée, en dollars |
| Temps moyen Valeur | Valeur commerciale moyenne générée, en dollars, par session |

Vous pouvez facilement définir tout ce que les visiteurs font sur le site Web comme un événement de valeur : publication d’une demande du service client, exécution d’une application, affichage d’un élément de contenu ou réalisation d’un achat. Chaque événement de valeur correspond à un utilisateur accédant à une page ou à un ensemble de pages spécifique du site web et est associé à une valeur commerciale en dollars. Par exemple, vous pouvez supposer que chaque utilisateur qui accède à la page &quot;Merci d’avoir acheté&quot; génère une marge de contribution de 20 $ en moyenne. Vous pouvez définir un événement de valeur pour cette page dont la valeur est de 20 $.

## Définition de nouveaux événements de valeur {#section-2ea4d168336e4d2e98b22b636ed43853}

**Pour définir un nouvel événement de valeur dans HBX ou[!DNL Site]**

Lorsque vous créez un événement de valeur, vous faites glisser des pages de site Web qui représentent une valeur d’une visualisation vers une légende de valeur.

1. Ouvrez une légende de valeur.

   ![](assets/lgd_ValueLegend.png)

1. Ajoutez des événements de valeur à la légende à partir des mappages de processus, des tables de pages URI ou des vues de hiérarchie de pages :

   * À partir d’une cartographie des processus, faites glisser les noeuds de la cartographie des processus vers la légende.
   * Dans un tableau de page URI, appuyez sur Ctrl+Alt et faites glisser une page du tableau vers la légende.
   * Dans une vue hiérarchique de page, cliquez à gauche d’un noeud (dossier, page ou groupe) et faites-le glisser sur la légende.

   ![](assets/client-leg.png)

   Le pointeur de la souris affiche le mot &quot;Non&quot; jusqu’à ce que la souris atteigne la légende.

1. Dans la légende des valeurs, attribuez une valeur d’entreprise à chaque session pour laquelle l’événement se produit :

   1. Dans le [!DNL Value per Event] , cliquez sur la cellule correspondant à la page que vous avez ajoutée en tant qu’événement de valeur.
   1. Saisissez le montant en dollars à affecter à la valeur de cet événement et appuyez sur Entrée.

   ![](assets/lgd_ValueLegend_Value.png)

   Par défaut, l’URL de la page que vous avez définie comme événement de valeur apparaît dans la légende des valeurs. Si vous le souhaitez, vous pouvez double-cliquer sur cette URL dans la légende pour passer en mode d’édition et renommer l’événement. Vous pouvez également modifier la valeur d’un événement particulier à tout moment. Le serveur de Data Workbench recalcule automatiquement les mesures basées sur les événements de valeur, telles que la valeur moyenne et la conversion.

Une fois que vous avez défini au moins un événement de valeur, la dimension Segment de valeur devient disponible. Cette dimension représente la valeur totale générée par un visiteur dans toutes les sessions.

## Supprimer des événements de valeur {#section-25cd90a859384ca183c0fc0998f888cf}

* Cliquez avec le bouton droit de la souris sur l’événement souhaité, puis cliquez sur **[!UICONTROL Delete Event]**.

   ![](assets/lgd_ValueLegend_deleteEvent.png)

>[!NOTE]
>
>Le serveur de Data Workbench calcule les mesures sur l’ensemble des données accessibles au profil que vous utilisez. Par défaut, la variable [!DNL Data Workbench Server] calcule des mesures telles que Valeur, Événements de valeur, Valeur moyenne et Conversion sur toutes les données du jeu de données d’analyse, même si les données ne proviennent pas de la même source logique.

## Exporter vers Microsoft Excel {#section-feaa7a8eb8124fafbc74169bebaed6d8}

Pour plus d’informations sur l’exportation de fenêtres, voir [Exportation des données de fenêtre](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
