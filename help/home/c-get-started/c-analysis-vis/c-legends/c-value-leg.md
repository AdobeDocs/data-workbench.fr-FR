---
description: Une légende de valeur affiche les événements de valeur définis.
title: Légendes de valeur
uuid: 7779f442-2f45-4bf8-a62a-585aaceaeb3a
exl-id: b28ba604-93ef-4081-ae55-937fb537c068
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 2%

---

# Légendes de valeur{#value-legends}

Une légende de valeur affiche les événements de valeur définis.

La légende de valeur est configurée uniquement dans les applications HBX et [!DNL Site], mais elle peut être configurée pour d&#39;autres applications. Pour plus d&#39;informations, contactez les Services de conseil en Adobe.

Dans HBX et [!DNL Site], un événement de valeur est défini comme une session qui a généré de la valeur commerciale. Par exemple, les enregistrements de données de événement associés à des vues de page particulières (par exemple, une page de remerciement pour une commande ou une page de fin de demande) peuvent représenter des événements de valeur pour une entreprise.

Avec les événements de valeur, vous pouvez mesurer et suivre la quantité de valeur générée par le site Web. Vous pouvez évaluer la valeur commerciale en dollars pour chaque événement et répondre à des questions telles que :

* Quel est le chemin le plus rentable à travers le site web ?
* Quel parrain ou quelle campagne a généré le plus de valeur ?

Pour chaque événement, la légende affiche la valeur unitaire du événement (valeur par événement) et la valeur totale générée par le événement. La légende permet de définir et de modifier des événements de valeur et de leur attribuer des valeurs unitaires.

Le tableau suivant liste les mesures liées aux événements de valeurs.

| Mesure | Description |
|---|---|
| Conversion | Pourcentage de sessions générant une valeur commerciale |
| Valeur | Valeur commerciale totale générée, en dollars |
| Temps moyen Valeur | Valeur commerciale moyenne générée, en dollars, par session |

Vous pouvez facilement définir tout ce que les visiteurs font sur le site Web comme un événement de valeur : publication d’une demande de service à la clientèle, achèvement d’une demande, affichage d’un élément de contenu ou exécution d’un achat. Chaque événement de valeur correspond à un utilisateur accédant à une page ou à un ensemble de pages spécifique du site Web et est associé à une valeur commerciale en dollars. Par exemple, vous pouvez supposer que chaque utilisateur qui accède à la page &quot;Merci d’avoir acheté&quot; génère une marge de contribution de 20 USD en moyenne. Vous pouvez définir un événement de valeur pour cette page dont la valeur est de 20 euros.

## Définir de nouveaux événements de valeur {#section-2ea4d168336e4d2e98b22b636ed43853}

**Pour définir un nouveau événement de valeur dans HBX ou[!DNL Site]**

Lorsque vous créez un événement de valeur, vous faites glisser des pages de site Web qui représentent une valeur d’une visualisation vers une légende de valeur.

1. Ouvrez une légende de valeur.

   ![](assets/lgd_ValueLegend.png)

1. Ajoutez des événements de valeur à la légende à partir des mappages de processus, des tables de page URI ou des vues de hiérarchie de page :

   * A partir d’une carte de processus, faites glisser les noeuds de la carte de processus vers la légende.
   * Dans un tableau de page URI, appuyez sur Ctrl+Alt et faites glisser une page du tableau vers la légende.
   * Dans une vue de hiérarchie de page, cliquez à gauche d’un noeud (dossier, page ou groupe) et faites-le glisser sur la légende.

   ![](assets/client-leg.png)

   Le pointeur de la souris affiche le mot &quot;Non&quot; jusqu’à ce que votre souris atteigne la légende.

1. Dans la légende de la valeur, attribuez une valeur commerciale à chaque session pour laquelle le événement se produit :

   1. Dans la colonne [!DNL Value per Event], cliquez sur la cellule qui correspond à la page que vous avez ajoutée en tant que événement de valeur.
   1. Saisissez le montant en dollars à affecter à la valeur de ce événement et appuyez sur Entrée.

   ![](assets/lgd_ValueLegend_Value.png)

   Par défaut, l’URL de la page que vous avez définie comme événement de valeur apparaît dans la légende de valeur. Si vous le souhaitez, vous pouvez cliquer sur cette URL en doublon dans la légende pour passer en mode d’édition et renommer le événement. Vous pouvez également modifier la valeur d’un événement particulier à tout moment. Le serveur de Data Workbench recalcule automatiquement les mesures basées sur les événements de valeurs, telles que la valeur moyenne et la conversion.

Une fois que vous avez défini au moins un événement de valeurs, la dimension Segment de valeur devient disponible pour utilisation. Cette dimension représente la valeur totale générée par un visiteur dans toutes les sessions.

## Supprimer des événements de valeur {#section-25cd90a859384ca183c0fc0998f888cf}

* Cliquez avec le bouton droit de la souris sur le événement souhaité, puis cliquez sur **[!UICONTROL Delete Event]**.

   ![](assets/lgd_ValueLegend_deleteEvent.png)

>[!NOTE]
>
>Le serveur de Data Workbench calcule les mesures sur l’ensemble des données accessibles au profil que vous utilisez. Par défaut, [!DNL Data Workbench Server] calcule des mesures telles que Valeur, Événements de valeurs, Valeur moyenne et Conversion pour toutes les données du jeu de données d’analyse, même si les données ne proviennent pas de la même source logique.

## Exporter vers Microsoft Excel {#section-feaa7a8eb8124fafbc74169bebaed6d8}

Pour plus d’informations sur l’exportation de fenêtres, voir [Exportation de données de fenêtre](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
