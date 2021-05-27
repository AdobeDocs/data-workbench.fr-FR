---
description: Les visualisations des tableaux de latence sont des tableaux qui incluent une dimension de latence, qui est un type de dimension dérivée qui mesure le temps qui s’est écoulé depuis qu’un événement particulier s’est produit.
title: Tableaux de latence
uuid: 8081540c-f96c-424e-802d-05d1be5a728d
exl-id: 22f6d52f-e1c2-430a-9e69-3440be0ecdea
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 1%

---

# Tableaux de latence{#latency-tables}

Les visualisations des tableaux de latence sont des tableaux qui incluent une dimension de latence, qui est un type de dimension dérivée qui mesure le temps qui s’est écoulé depuis qu’un événement particulier s’est produit.

Vous définissez l’événement en effectuant des sélections dans une ou plusieurs visualisations et en définissant ces sélections comme événement à l’aide de l’option de menu contextuel Définir l’événement . Les tableaux de latence sont particulièrement utiles pour effectuer le suivi des activités liées à une campagne ou à une commande client spécifique dans laquelle vous recherchez une corrélation temporelle.

Dans [!DNL Site], les tableaux de latence fournissent des informations sur les sessions de visiteurs qui se sont produites jusqu’à sept jours avant ou après l’événement, mais vous pouvez configurer des tableaux de latence pour fournir des informations sur les différentes dimensions dénombrables et temporelles. Voir [Configuration des tableaux de latence](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/c-config-ltcy-tbls.md#concept-7175c3defec64556994f0dfcccb7d15c).

Les éléments de la dimension parent, tels qu’une session, qui font partie de l’événement spécifique que vous avez sélectionné, ont une latence de zéro. Tous les autres éléments se voient attribuer des latences qui reflètent la distance (dans la dimension temporelle appropriée) de l’événement.

L’exemple suivant illustre l’utilisation du tableau de latence.

**Identifier les événements de valeur par rapport à une campagne**

Supposons que vous souhaitiez effectuer le suivi de l’activité des clients au cours des sept jours précédant et suivant leur réponse à une campagne publicitaire spécifique. Pour afficher la latence d’une campagne publicitaire spécifique, définissez la campagne d’intérêt comme événement pour le tableau de latence.

La latence dans l’espace de travail ci-dessous est basée sur la sélection de Campaign 11566 (les sessions en réponse à cette campagne).

![](assets/vis_Latency.png)

Une latence de &quot;+0 jour&quot; identifie les sessions en réponse à Campaign 11566, ainsi que toutes les autres sessions pour les mêmes clients qui se sont produites le même jour.

Une latence de &quot;-2 jours&quot; identifie les sessions pour ces mêmes clients qui se sont produites deux jours avant la réponse des clients à la campagne.

Une latence de &quot;+7 jours&quot; identifie les sessions pour les mêmes clients qui se sont produits sept jours après avoir répondu à la campagne.

Outre les procédures répertoriées dans les sections suivantes, vous pouvez effectuer toutes les tâches que vous pouvez effectuer dans un tableau, telles que le tri, le masquage d’éléments, l’ajout d’une légende de série, l’export de données, etc. Pour plus d’informations, voir [Tableaux](../../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).

## Créer un tableau de latence {#section-31a03031d9854ef7acc2462d4f37678d}

Pour créer un tableau de latence, vous devez d’abord effectuer une sélection, puis définir cette sélection comme événement pour lequel vous souhaitez effectuer le suivi de la latence.

1. Cliquez avec le bouton droit dans un espace de travail et ouvrez la ou les visualisations souhaitées, qui doivent être basées sur la dimension dénombrable utilisée pour configurer votre tableau de latence.

   Par exemple, dans [!DNL Site], les visualisations doivent être basées sur les sessions.

1. Ouvrez un tableau de latence vide.
1. Effectuez une sélection dans votre espace de travail.
1. Cliquez avec le bouton droit dans le tableau de latence et cliquez sur **[!UICONTROL Set Event]**.

![](assets/vis_Latency_SetEvent.png)

>[!NOTE]
>
>Les événements que vous sélectionnez ne persistent pas, sauf si vous enregistrez les sélections en tant que dimension de latence. Pour connaître les étapes, voir [Réutilisation d’une Dimension de latence](../../../home/c-get-started/c-analysis-vis/c-lat-tbls.md#section-29c6483bf9ba476fb1c24ad1df253f46).

## Réutilisation d’une table de latence {#section-05f741169d204213b6537dce553e4f73}

Si vous souhaitez réutiliser la même table de latence, vous pouvez enregistrer la table de latence localement ou si vous disposez des autorisations adéquates, vous pouvez l’enregistrer sur le serveur pour que tous les utilisateurs d’un profil particulier puissent y accéder.

**Enregistrement du tableau de latence en vue de son utilisation dans d’autres espaces de travail**

1. Cliquez avec le bouton droit de la souris sur la bordure supérieure de la visualisation, puis cliquez sur **[!UICONTROL Save]**. La fenêtre [!DNL Save] s’affiche. L’emplacement d’enregistrement par défaut est le dossier User\*profile name*\Work.
1. Dans le champ [!DNL File name] , saisissez un nom descriptif pour la visualisation, puis cliquez sur **[!UICONTROL Save]**.

**Pour récupérer la table de latence enregistrée**

1. Cliquez avec le bouton droit dans l’espace de travail, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL File]**. La fenêtre [!DNL Open Visualization] s’affiche.
1. Accédez au tableau de latence que vous avez enregistré.
1. Sélectionnez le fichier de visualisation du tableau de latence ( [!DNL *.vw]) et cliquez sur **[!UICONTROL Open]**.

## Réutilisation d’une dimension de latence {#section-29c6483bf9ba476fb1c24ad1df253f46}

Si vous souhaitez réutiliser la même dimension de latence, vous pouvez enregistrer la dimension de latence localement ou si vous disposez des autorisations appropriées, vous pouvez l’enregistrer sur le serveur pour que tous les utilisateurs d’un profil particulier y aient accès.

Toutes les dimensions de latence que vous créez sont enregistrées dans le répertoire des Dimensions du profil et sont disponibles dans la liste déroulante [!DNL Change Dimension] de Data Workbench.

**Enregistrement de la dimension de latence en vue de son utilisation dans d’autres espaces de travail**

1. Cliquez avec le bouton droit sur le libellé de la colonne [!DNL Latency] ou sur l&#39;un de ses éléments et cliquez sur **[!UICONTROL Save Dimension]**. La fenêtre [!DNL Save Dimension As] s’affiche.
1. Sélectionnez ou créez le sous-répertoire approprié dans le répertoire Dimensions.
1. Dans le champ [!DNL File name] , saisissez un nom descriptif pour la dimension (par exemple, [!DNL Latency for Campaign 11565.dim]) et cliquez sur **[!UICONTROL Save]**.

**Pour récupérer la dimension de latence enregistrée**

1. Cliquez avec le bouton droit dans l’espace de travail, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL File]**. La fenêtre [!DNL Open Visualization] s’affiche.
1. Accédez à la visualisation de latence que vous avez enregistrée dans le dossier User\*profile name*\Dimensions .
1. Sélectionnez le fichier de dimension de latence ( [!DNL *.dim]) et cliquez sur **[!UICONTROL Open]**.

## Exporter vers Microsoft Excel {#section-3dffa5c3aab14cdaa40c78b81b08fe53}

Pour plus d’informations sur l’exportation de fenêtres, voir [Export de données de fenêtre](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).

## Exporter vers un fichier TSV {#section-fd921f351c994ed0a94f63d3bd5b5a87}

Pour plus d’informations sur l’exportation de fenêtres, voir [Export de données de fenêtre](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
