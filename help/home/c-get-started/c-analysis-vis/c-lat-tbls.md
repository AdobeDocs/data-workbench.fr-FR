---
description: Les visualisations des tableaux de latence sont des tableaux qui incluent une dimension de latence, qui est un type de dimension dérivée qui mesure le temps qui s’est écoulé depuis qu’un événement particulier s’est produit.
title: Tableaux de latence
uuid: 8081540c-f96c-424e-802d-05d1be5a728d
exl-id: 22f6d52f-e1c2-430a-9e69-3440be0ecdea
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 1%

---

# Tableaux de latence{#latency-tables}

Les visualisations des tableaux de latence sont des tableaux qui incluent une dimension de latence, qui est un type de dimension dérivée qui mesure le temps qui s’est écoulé depuis qu’un événement particulier s’est produit.

Pour définir le événement, effectuez des sélections dans une ou plusieurs visualisations et définissez ces sélections comme événement à l’aide de l’option de menu contextuel Définir le Événement. Les tableaux de latence sont particulièrement utiles pour suivre l’activité liée à une campagne ou à un ordre de client particulier dans lequel vous recherchez une corrélation temporelle.

Dans [!DNL Site], les tableaux de latence fournissent des informations sur les sessions de visiteur qui se sont déroulées jusqu&#39;à sept jours avant ou après le événement, mais vous pouvez configurer des tableaux de latence pour fournir des informations sur les différentes dimensions de compteur et de temps. Voir [Configuration des tables de latence](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/c-config-ltcy-tbls.md#concept-7175c3defec64556994f0dfcccb7d15c).

Les éléments de la dimension parent, tels qu’une session, qui font partie du événement spécifique sélectionné, présentent une latence de zéro. Tous les autres éléments sont affectés à des latences qui reflètent la distance (dans la dimension de temps appropriée) par rapport au événement.

L’exemple suivant illustre comment utiliser le tableau de latence.

**Identifier les événements de valeur par rapport à une campagne**

Supposons que vous souhaitiez effectuer le suivi de l’activité des clients au cours des sept jours précédant et suivant leur réponse à une campagne publicitaire particulière. Pour vue la latence d’une campagne publicitaire particulière, définissez la campagne d’intérêt comme événement de la table de latence.

La latence dans l’espace de travail ci-dessous est basée sur la sélection de Campaign 11566 (sessions en réponse à cette campagne).

![](assets/vis_Latency.png)

Une latence de &quot;+0 jour&quot; identifie les sessions en réponse à Campaign 11566, ainsi que toutes les autres sessions pour les mêmes clients qui se sont déroulées le même jour.

Une latence de &quot;-2 jours&quot; identifie les sessions pour ces mêmes clients qui se sont produites deux jours avant la réponse des clients à la campagne.

Une latence de &quot;+7 jours&quot; identifie les sessions pour ces mêmes clients qui se sont produites sept jours après leur réponse à la campagne.

Outre les procédures répertoriées dans les sections suivantes, vous pouvez exécuter toutes les tâches que vous pouvez effectuer dans un tableau, telles que les éléments de tri, les éléments de masque, l’ajout d’une légende de série, l’exportation de données, etc. Pour plus d’informations, voir [Tableaux](../../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).

## Créer un tableau de latence {#section-31a03031d9854ef7acc2462d4f37678d}

Pour créer un tableau de latence, vous commencez par effectuer une sélection, puis vous définissez cette sélection comme événement pour lequel vous souhaitez effectuer le suivi de la latence.

1. Cliquez avec le bouton droit dans un espace de travail et ouvrez la ou les visualisations souhaitées, qui doivent être basées sur la dimension dénombrable utilisée pour configurer votre tableau de latence.

   Par exemple, dans [!DNL Site], les visualisations doivent être basées sur les sessions.

1. Ouvrez un tableau de latence vide.
1. Effectuez une sélection dans votre espace de travail.
1. Cliquez avec le bouton droit de la souris dans le tableau de latence et cliquez sur **[!UICONTROL Set Event]**.

![](assets/vis_Latency_SetEvent.png)

>[!NOTE]
>
>Les événements que vous sélectionnez ne sont pas conservés, sauf si vous enregistrez les sélections sous forme de dimension de latence. Pour connaître les étapes, voir [Réutilisation d’une Dimension de latence](../../../home/c-get-started/c-analysis-vis/c-lat-tbls.md#section-29c6483bf9ba476fb1c24ad1df253f46).

## Réutilisation d’une table de latence {#section-05f741169d204213b6537dce553e4f73}

Si vous souhaitez réutiliser la même table de latence, vous pouvez enregistrer la table de latence localement ou si vous disposez des autorisations appropriées, vous pouvez l’enregistrer sur le serveur pour que tous les utilisateurs d’un profil donné puissent y accéder.

**Pour enregistrer la table de latence en vue de l’utiliser dans d’autres espaces de travail**

1. Cliquez avec le bouton droit sur la bordure supérieure de la visualisation et cliquez sur **[!UICONTROL Save]**. La fenêtre [!DNL Save] s&#39;affiche. L’emplacement d’enregistrement par défaut est le dossier Utilisateur\*nom du profil*\Travail.
1. Dans le champ [!DNL File name], tapez un nom descriptif pour la visualisation et cliquez sur **[!UICONTROL Save]**.

**Pour récupérer la table de latence enregistrée**

1. Cliquez avec le bouton droit de la souris dans l&#39;espace de travail et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL File]**. La fenêtre [!DNL Open Visualization] s&#39;affiche.
1. Accédez à la table de latence que vous avez enregistrée.
1. Sélectionnez le fichier de visualisation du tableau de latence ( [!DNL *.vw]) et cliquez sur **[!UICONTROL Open]**.

## Réutilisation d’une dimension de latence {#section-29c6483bf9ba476fb1c24ad1df253f46}

Si vous souhaitez réutiliser la même dimension de latence, vous pouvez enregistrer la dimension de latence localement ou si vous disposez des autorisations appropriées, vous pouvez l’enregistrer sur le serveur pour que tous les utilisateurs d’un profil donné puissent y accéder.

Toutes les dimensions de latence que vous créez sont enregistrées dans le répertoire des Dimensions du profil et sont disponibles dans la liste déroulante [!DNL Change Dimension] du Data Workbench.

**Pour enregistrer la dimension de latence en vue de l’utiliser dans d’autres espaces de travail**

1. Cliquez avec le bouton droit sur l&#39;étiquette de colonne [!DNL Latency] ou sur l&#39;un de ses éléments, puis cliquez sur **[!UICONTROL Save Dimension]**. La fenêtre [!DNL Save Dimension As] s&#39;affiche.
1. Sélectionnez ou créez le sous-répertoire approprié dans le répertoire Dimensions.
1. Dans le champ [!DNL File name], tapez un nom descriptif pour la dimension (par exemple, [!DNL Latency for Campaign 11565.dim]) et cliquez sur **[!UICONTROL Save]**.

**Pour récupérer la dimension de latence enregistrée**

1. Cliquez avec le bouton droit de la souris dans l&#39;espace de travail et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL File]**. La fenêtre [!DNL Open Visualization] s&#39;affiche.
1. Accédez à la visualisation de latence que vous avez enregistrée dans le dossier User\*profil name*\Dimensions.
1. Sélectionnez le fichier de dimension de latence ( [!DNL *.dim]) et cliquez sur **[!UICONTROL Open]**.

## Exporter vers Microsoft Excel {#section-3dffa5c3aab14cdaa40c78b81b08fe53}

Pour plus d’informations sur l’exportation de fenêtres, voir [Exportation de données de fenêtre](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).

## Exporter vers un fichier TSV {#section-fd921f351c994ed0a94f63d3bd5b5a87}

Pour plus d’informations sur l’exportation de fenêtres, voir [Exportation de données de fenêtre](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
