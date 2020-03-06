---
description: Les visualisations des tableaux de latence sont des tableaux qui incluent une dimension de latence, qui est un type de dimension dérivée qui mesure le temps qui s’est écoulé depuis qu’un événement particulier s’est produit.
solution: Analytics
title: Tableaux de latence
topic: Data workbench
uuid: 8081540c-f96c-424e-802d-05d1be5a728d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tableaux de latence{#latency-tables}

Les visualisations des tableaux de latence sont des tableaux qui incluent une dimension de latence, qui est un type de dimension dérivée qui mesure le temps qui s’est écoulé depuis qu’un événement particulier s’est produit.

Pour définir l’événement, effectuez des sélections dans une ou plusieurs visualisations et définissez ces sélections comme événement à l’aide de l’option de menu contextuel Définir l’événement. Les tableaux de latence sont particulièrement utiles pour effectuer le suivi des activités liées à une campagne ou à un ordre de client particulier dans lequel vous recherchez une corrélation temporelle.

Dans [!DNL Site]les tableaux de latence, vous trouverez des informations sur les sessions du visiteur qui se sont produites jusqu’à sept jours avant ou après l’événement, mais vous pouvez configurer des tableaux de latence pour fournir des informations sur les différentes dimensions dénombrables et temporelles. Voir [Configuration des tableaux](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/c-config-ltcy-tbls.md#concept-7175c3defec64556994f0dfcccb7d15c)de latence.

Les éléments de la dimension parent, tels qu’une session, qui font partie de l’événement spécifique que vous avez sélectionné, présentent une latence de zéro. Tous les autres éléments se voient attribuer des latences qui reflètent la distance (dans la dimension temporelle appropriée) par rapport à l’événement.

L’exemple suivant illustre l’utilisation possible du tableau de latence.

**Identifier les événements de valeur par rapport à une campagne**

Supposons que vous souhaitiez suivre l’activité des clients au cours des sept jours précédant et suivant leur réponse à une campagne publicitaire particulière. Pour afficher la latence d’une campagne publicitaire particulière, définissez la campagne d’intérêt comme événement pour le tableau de latence.

La latence dans l’espace de travail ci-dessous est basée sur la sélection de la campagne 11566 (les sessions en réponse à cette campagne).

![](assets/vis_Latency.png)

Une latence de &quot;+0 jours&quot; identifie les sessions en réponse à la campagne 11566, ainsi que toutes les autres sessions pour les mêmes clients qui se sont produites le même jour.

Une latence de &quot;-2 jours&quot; identifie les sessions pour les mêmes clients qui se sont produites deux jours avant que les clients n’aient répondu à la campagne.

Une latence de &quot;+7 jours&quot; identifie les sessions pour les mêmes clients qui se sont produites sept jours après avoir répondu à la campagne.

Outre les procédures répertoriées dans les sections suivantes, vous pouvez exécuter toutes les mêmes tâches que celles que vous pouvez effectuer dans un tableau, telles que les éléments de tri, les éléments de masque, l’ajout d’une légende de série, l’exportation de données, etc. For more information, see [Tables](../../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).

## Création d’un tableau de latence {#section-31a03031d9854ef7acc2462d4f37678d}

Pour créer un tableau de latence, vous commencez par effectuer une sélection, puis vous définissez cette sélection comme l’événement pour lequel vous souhaitez effectuer le suivi de la latence.

1. Cliquez avec le bouton droit dans un espace de travail et ouvrez la ou les visualisations souhaitées, qui doivent être basées sur la dimension dénombrable utilisée pour configurer votre tableau de latence.

   Par exemple, dans [!DNL Site] les visualisations, il faudrait que les sessions soient basées sur les sessions.

1. Ouvrez un tableau de latence vide.
1. Effectuez une sélection dans votre espace de travail.
1. Cliquez avec le bouton droit de la souris dans le tableau de latence, puis cliquez sur **[!UICONTROL Set Event]**.

![](assets/vis_Latency_SetEvent.png)

>[!NOTE]
>
>Les événements que vous sélectionnez ne persistent pas, sauf si vous enregistrez les sélections sous forme de dimension de latence. Pour connaître les étapes, voir [Réutilisation d’une dimension](../../../home/c-get-started/c-analysis-vis/c-lat-tbls.md#section-29c6483bf9ba476fb1c24ad1df253f46)de latence.

## Réutilisation d’un tableau de latence {#section-05f741169d204213b6537dce553e4f73}

Si vous souhaitez réutiliser la même table de latence, vous pouvez enregistrer la table de latence localement ou si vous disposez des autorisations appropriées, vous pouvez l’enregistrer sur le serveur pour que tous les utilisateurs d’un profil donné y aient accès.

**Pour enregistrer le tableau de latence en vue de l’utiliser dans d’autres espaces de travail**

1. Cliquez avec le bouton droit sur la bordure supérieure de la visualisation et cliquez sur **[!UICONTROL Save]**. La [!DNL Save] fenêtre s&#39;affiche. L’emplacement d’enregistrement par défaut est le dossier Utilisateur\*nom du profil*\Travail.
1. Dans le [!DNL File name] champ, saisissez un nom descriptif pour la visualisation, puis cliquez sur **[!UICONTROL Save]**.

**Pour récupérer la table de latence enregistrée**

1. Cliquez avec le bouton droit de la souris dans l’espace de travail et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL File]**. La [!DNL Open Visualization] fenêtre s&#39;affiche.
1. Accédez au tableau de latence que vous avez enregistré.
1. Sélectionnez le fichier de visualisation du tableau de latence ( [!DNL *.vw]), puis cliquez sur **[!UICONTROL Open]**.

## Réutilisation d’une dimension de latence {#section-29c6483bf9ba476fb1c24ad1df253f46}

Si vous souhaitez réutiliser la même dimension de latence, vous pouvez enregistrer la dimension de latence localement ou, si vous disposez des autorisations appropriées, vous pouvez l’enregistrer sur le serveur pour que tous les utilisateurs d’un profil donné y aient accès.

Toutes les dimensions de latence que vous créez sont enregistrées dans le répertoire Dimensions du profil et sont disponibles dans la liste [!DNL Change Dimension] déroulante des Outils de données.

**Pour enregistrer la dimension de latence en vue de l’utiliser dans d’autres espaces de travail**

1. Cliquez avec le bouton droit de la souris sur le libellé de la [!DNL Latency] colonne ou sur l’un de ses éléments, puis cliquez sur **[!UICONTROL Save Dimension]**. La [!DNL Save Dimension As] fenêtre s&#39;affiche.
1. Sélectionnez ou créez le sous-répertoire approprié dans le répertoire Dimensions.
1. Dans le [!DNL File name] champ, tapez un nom descriptif pour la dimension (par exemple [!DNL Latency for Campaign 11565.dim]), puis cliquez sur **[!UICONTROL Save]**.

**Pour récupérer la dimension de latence enregistrée**

1. Cliquez avec le bouton droit de la souris dans l’espace de travail et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL File]**. La [!DNL Open Visualization] fenêtre s&#39;affiche.
1. Accédez à la visualisation de latence que vous avez enregistrée dans le dossier User\*profile name*\Dimensions.
1. Sélectionnez le fichier de dimension de latence ( [!DNL *.dim]), puis cliquez sur **[!UICONTROL Open]**.

## Exporter vers Microsoft Excel {#section-3dffa5c3aab14cdaa40c78b81b08fe53}

Pour plus d’informations sur l’exportation de fenêtres, voir [Exportation de données](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)de fenêtre.

## Exportation vers un fichier TSV {#section-fd921f351c994ed0a94f63d3bd5b5a87}

Pour plus d’informations sur l’exportation de fenêtres, voir [Exportation de données](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)de fenêtre.
