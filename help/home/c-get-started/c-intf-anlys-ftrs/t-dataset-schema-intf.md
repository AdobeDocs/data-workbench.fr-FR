---
description: Procédure de modification de la visualisation par défaut.
title: Configuration de l’interface du schéma du jeu de données
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 4%

---

# Configuration de l’interface du schéma du jeu de données{#configure-the-dataset-schema-interface}

Procédure de modification de la visualisation par défaut.

Vous pouvez contrôler le type de visualisation qui s’affiche lorsque vous cliquez sur un nom de dimension dans [!DNL Dataset Schema Interface] en ajoutant des fichiers aux Profils\*nom du profil*\Context\Dimension Legend folder of the Data Workbench server installation folder. Le fichier [!DNL Default.1d] de ce dossier contrôle le type de visualisation par défaut pour toutes les dimensions. En ajoutant un fichier *nom de dimension*.1d (tel que [!DNL Hour.1d]) à ce dossier, vous pouvez contrôler la visualisation par défaut pour cette dimension particulière.

Pour plus d&#39;informations sur [!DNL Dataset Schema Interfaces], voir [L&#39;interface de Schéma des ensembles de données](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**Pour modifier la visualisation par défaut**

1. Dans n’importe quel espace de travail, créez une visualisation contenant les données que vous souhaitez voir apparaître dans la nouvelle visualisation par défaut.

   Par exemple, si vous souhaitez que la dimension s’affiche dans un graphique à barres, créez une visualisation du graphique à barres présentant la mesure et la dimension souhaitées.

1. Cliquez avec le bouton droit sur la bordure supérieure de la fenêtre de légende et cliquez sur **[!UICONTROL Save]**.
1. Dans la fenêtre [!DNL Save], cliquez sur ![](assets/btn_folder_up.png), doublon-clic **[!UICONTROL Context]**, puis doublon-clic **[!UICONTROL Dimension Legend]**.
1. Dans le champ [!DNL File Name], saisissez le nom de la dimension.

   Le nom du fichier [!DNL .1d] doit correspondre exactement au nom de la dimension. Par exemple : [!DNL Hour.1d].

1. Modifiez l&#39;extension de fichier en &quot;1d&quot; et cliquez sur **[!UICONTROL Save]**.

   Le fichier est enregistré dans le dossier Utilisateur\*nom du profil de travail*\Context\Dimension Legend folder.

   La prochaine fois que vous cliquerez sur cette dimension dans un [!DNL Dataset Schema Interface], la visualisation que vous avez spécifiée s’affichera.

1. (Facultatif) Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail :

   1. Dans le [!DNL Profile Manager], cliquez sur **[!UICONTROL Context]**, puis sur **[!UICONTROL Dimension Legend]**.

   1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom de fichier de la nouvelle légende dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
