---
description: Procédure de modification de la visualisation par défaut.
title: Configuration de l’interface du schéma du jeu de données
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 4%

---

# Configuration de l’interface du schéma du jeu de données{#configure-the-dataset-schema-interface}

{{eol}}

Procédure de modification de la visualisation par défaut.

Vous pouvez contrôler le type de visualisation qui s’affiche lorsque vous cliquez sur le nom d’une dimension dans une [!DNL Dataset Schema Interface] en ajoutant des fichiers au dossier Profils\*nom du profil*\Context\Dimension Légende du dossier d’installation du serveur de Data Workbench. Le [!DNL Default.1d] dans ce dossier contrôle le type de visualisation par défaut pour toutes les dimensions. En ajoutant une *nom de la dimension* fichier .1d (par exemple, [!DNL Hour.1d]) de ce dossier, vous pouvez contrôler la visualisation par défaut pour cette dimension particulière.

Pour plus d’informations sur [!DNL Dataset Schema Interfaces], voir [Interface du schéma du jeu de données](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**Pour modifier la visualisation par défaut**

1. Dans n’importe quel espace de travail, créez une visualisation contenant les données que vous souhaitez afficher dans la nouvelle visualisation par défaut.

   Par exemple, si vous souhaitez que la dimension s’affiche dans un graphique à barres, créez une visualisation de graphique à barres présentant la mesure et la dimension souhaitées.

1. Cliquez avec le bouton droit sur la bordure supérieure de la fenêtre de légende, puis cliquez sur **[!UICONTROL Save]**.
1. Dans le [!DNL Save] fenêtre, cliquez sur ![](assets/btn_folder_up.png), double-cliquez sur **[!UICONTROL Context]**, puis double-cliquez sur **[!UICONTROL Dimension Legend]**.
1. Dans le [!DNL File Name] , saisissez le nom de la dimension.

   Nom de la variable [!DNL .1d] doit correspondre exactement au nom de la dimension. Par exemple : [!DNL Hour.1d].

1. Remplacez l’extension de fichier par &quot;1d&quot; et cliquez sur **[!UICONTROL Save]**.

   Le fichier est enregistré dans le dossier User\*working profile name*\Context\Dimension Legend .

   La prochaine fois que vous cliquerez sur cette dimension dans une [!DNL Dataset Schema Interface], la visualisation que vous avez spécifiée s’affiche.

1. (Facultatif) Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail :

   1. Dans le [!DNL Profile Manager], cliquez sur **[!UICONTROL Context]**, puis cliquez sur **[!UICONTROL Dimension Legend]**.

   1. Cliquez avec le bouton droit de la souris sur la coche située en regard du nom de fichier de la nouvelle légende dans le [!DNL User] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
