---
description: Cette section décrit la procédure à suivre pour modifier la visualisation par défaut.
solution: Analytics
title: Configuration de l’interface de schéma de jeu de données
topic: Data workbench
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Configuration de l’interface de schéma de jeu de données{#configure-the-dataset-schema-interface}

Cette section décrit la procédure à suivre pour modifier la visualisation par défaut.

Vous pouvez contrôler le type de visualisation qui s’affiche lorsque vous cliquez sur le nom d’une dimension dans une [!DNL Dataset Schema Interface] en ajoutant des fichiers au profil \*nom du profil*\Context\Dimension Legend folder of the Data Workbench server installation folder. Le [!DNL Default.1d] fichier de ce dossier contrôle le type de visualisation par défaut pour toutes les dimensions. En ajoutant un fichier *de nom* de dimension.1d (par exemple [!DNL Hour.1d]) à ce dossier, vous pouvez contrôler la visualisation par défaut pour cette dimension particulière.

Pour plus d’informations sur [!DNL Dataset Schema Interfaces]l’interface [de schéma des jeux de données, voir](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)The Dataset Schema Interface (en anglais).

**Pour modifier la visualisation par défaut**

1. Dans n’importe quel espace de travail, créez une visualisation contenant les données que vous souhaitez voir apparaître dans la nouvelle visualisation par défaut.

   Par exemple, si vous souhaitez que la dimension s’affiche dans un graphique à barres, créez une visualisation en graphique à barres présentant la mesure et la dimension souhaitées.

1. Cliquez avec le bouton droit sur la bordure supérieure de la fenêtre de légende, puis cliquez sur **[!UICONTROL Save]**.
1. Dans la [!DNL Save] fenêtre, cliquez ![](assets/btn_folder_up.png), double-cliquez **[!UICONTROL Context]**, puis double-cliquez **[!UICONTROL Dimension Legend]**.
1. Dans le [!DNL File Name] champ, saisissez le nom de la dimension.

   The name of the [!DNL .1d] file must match the name of the dimension exactly. Par exemple : [!DNL Hour.1d].

1. Remplacez l’extension de fichier par &quot;1d&quot; et cliquez sur **[!UICONTROL Save]**.

   Le fichier est enregistré sous le nom de profil utilisateur\*\Context\Dimension Legend folder.

   La prochaine fois que vous cliquerez sur cette dimension dans une [!DNL Dataset Schema Interface], la visualisation que vous avez spécifiée s’affichera.

1. (Facultatif) Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail :

   1. Dans la [!DNL Profile Manager], cliquez sur **[!UICONTROL Context]**, puis sur **[!UICONTROL Dimension Legend]**.

   1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom de fichier de la nouvelle légende dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

