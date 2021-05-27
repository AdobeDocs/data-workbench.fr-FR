---
description: La barre latérale permet d’accéder aux fonctions fréquemment utilisées et préserve les visualisations lorsque vous vous déplacez entre les espaces de travail.
title: Configuration de la barre latérale
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
exl-id: 75ccc869-8ced-4beb-b3d7-ed7febe347f9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# Configuration de la barre latérale{#configure-the-sidebar}

La barre latérale permet d’accéder aux fonctions fréquemment utilisées et préserve les visualisations lorsque vous vous déplacez entre les espaces de travail.

Les administrateurs peuvent personnaliser une barre latérale pour la rendre adaptée aux différents groupes d’utilisateurs, puis déployer la barre latérale avec un profil.

La barre latérale est idéale pour vous aider à effectuer le suivi des filtres et des remplacements locaux. Si vous préférez ne pas utiliser la barre latérale, vous pouvez la masquer.

## Ajouter des visualisations à la barre latérale {#section-666f70a405db4f8d8eaffa567ffcac06}

1. Lancez Data Workbench.
1. Dans la barre latérale, cliquez sur **[!UICONTROL Add]** > *&lt;**[!UICONTROL item]***. Par exemple, [!DNL Selections Panel], [!DNL Filters Panel], ou [!DNL Table].

   Les panneaux latérale suivants sont disponibles dans l’installation standard de Data Workbench. D’autres éléments peuvent être disponibles dans votre profil spécifique :

   * **Panneau Sélections :** vous permet de comprendre les sélections principales dans l’espace de travail actuel. [!DNL Selections Panel] se met à jour chaque fois que vous effectuez une nouvelle sélection. Vous pouvez effacer les sélections en cliquant sur **[!UICONTROL x]**. Voir [Réalisation de sélections dans les visualisations](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746) pour plus d’informations sur la sélection des données.
   * **Panneau Filtres :** facilite le chargement et l’application de filtres enregistrés. Vous pouvez charger plusieurs filtres et les activer ou les désactiver indépendamment en cochant la case en regard de ceux-ci. Voir [Éditeurs de filtre](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **Panneau de remplacement local :** ce panneau affiche les mesures, dimensions et filtres présents dans le profil qui ont été modifiés dans votre copie personnelle du profil. Cela vous permet d’identifier les différences possibles entre l’affichage des données dans votre client et celui des autres utilisateurs. Lorsque vous enregistrez des modifications dans une mesure, une dimension ou un filtre sur le serveur, le remplacement est supprimé de la balise [!DNL Local Overrides panel]. Si vous cliquez sur un remplacement, puis sur **[!UICONTROL Revert to Server]**, le remplacement local est supprimé et l’élément revient à la version partagée.
   * **Légende des mesures :** ajoute une légende des mesures. [!DNL Metric legends] vous permettent d’afficher les mesures de base liées à votre profil et les statistiques liées au jeu de données (ou à la sélection en cours, le cas échéant). Voir [Légendes des mesures](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
   * **Légende en couleur :** ajoute une légende en couleur. Vous pouvez coder en couleur les visualisations par mesures, telles que Conversion et Rétention, et les utiliser dans presque toutes les [!DNL Workspace]. L’association de mesures d’entreprise à des couleurs permet de repérer facilement les anomalies, les exceptions et les tendances. Voir [Légendes en couleur](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).
   * **Annotation de texte :** ajoute un panneau de notes. [!DNL Text annotations] sont des fenêtres dans lesquelles vous pouvez saisir du texte arbitraire pour ajouter des informations ou des commentaires descriptifs à un  [!DNL Workspace]. Voir [Utilisation des annotations de texte](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * **Tableau :** ajoute un tableau. Un tableau peut afficher une ou plusieurs mesures sur une ou plusieurs dimensions de données. Voir [Tableaux](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).
   * **Ouvrir :** ouvre un fichier enregistré.

## Ouvrez un panneau latéral {#section-cbc8e57491854274a577d47a48c306b8}

Vous pouvez ouvrir un fichier de visualisation de barre latérale à partir d’un emplacement enregistré ou à partir du Presse-papiers.

1. Dans la barre latérale, cliquez sur **[!UICONTROL Add]** > **[!UICONTROL Open]**.
1. Cliquez sur **[!UICONTROL File]** pour localiser le fichier [!DNL .vw] du panneau à ajouter, ou cliquez sur **[!UICONTROL Last Closed Window]**, ce qui extrait la visualisation du Presse-papiers.

   Vous pouvez également cliquer sur **[!UICONTROL From Clipboard]** pour coller une visualisation qui a été copiée dans le Presse-papiers. Voir [Copie d’un panneau latéral](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1).

## Copie d’un panneau de la barre latérale {#section-720ae057632a4b8dbb94412e06a370b1}

1. Cliquez avec le bouton droit sur la bordure supérieure du panneau, puis cliquez sur **[!UICONTROL Copy]** > **[!UICONTROL Window]**.
1. Pour coller le panneau, cliquez sur **[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**.

## Enregistrement d’un panneau latéral {#section-fb19936b12704fb0a4c592abb579db1d}

Dans un panneau latéral, cliquez avec le bouton droit dans la barre de titre, puis cliquez sur **[!UICONTROL Save]**.

De même, vous pouvez ouvrir une visualisation de la barre latérale enregistrée. Data Workbench enregistre la visualisation sous la forme d’un fichier [!DNL .vw] à l’emplacement spécifié.

## Revenir à la barre latérale par défaut {#section-4d14b8771ad747bba799876267f24831}

Dans la barre latérale, cliquez sur **[!UICONTROL Options]** > **[!UICONTROL Revert]**.

Lorsque vous fermez Data Workbench, le système enregistre la configuration de la barre latérale actuelle dans le fichier [!DNL sidebar.vw] du profil utilisateur. Lorsque vous ouvrez Data Workbench, le système charge le fichier [!DNL sidebar.vw] à partir du profil utilisateur, plutôt qu’un profil parent.

Vous pouvez revenir à une barre latérale par défaut ou précédemment enregistrée, ce qui supprime la barre latérale du profil utilisateur et recharge la barre latérale du profil parent. Les administrateurs peuvent remplacer la barre latérale par défaut (parent) par une barre latérale locale en la chargeant à partir de la balise [!DNL Profile Manager].

## Personnalisation du fichier Plus de panneau d’état {#section-8d502f3b59cc4331966edec05e896ce1}

Les administrateurs système peuvent créer des formules dans la balise [!DNL More Status Panel.vw]. Cela place des mots contextuels autour des valeurs de mesure et de dimension et affiche les résultats dans la balise [!DNL More Status panel] de la barre latérale.

Pour afficher la balise [!DNL More Status panel] dans la barre latérale, cliquez sur les flèches affichées dans l’exemple suivant.

![](assets/more_status_panel_arrows.png)

La procédure suivante illustre un exemple simple de création d’un état personnalisé qui vous indique le nombre de jours dans un jeu de données :

1. Dans la balise [!DNL Profile Manager], cliquez sur **[!UICONTROL Sidebar\]**.

1. Dans la colonne [!DNL Base_5_3*], effectuez une copie locale du fichier [!DNL More Status Panel.vw].

   Pour ce faire, cliquez avec le bouton droit de la souris sur la coche du fichier et cliquez sur **[!UICONTROL Make Local]**.

1. Ouvrez le fichier [!DNL More Status Panel.vw] dans la balise [!DNL .vw] [!DNL Editor] ou dans le Bloc-notes.

   ![](assets/more_status_panel_file.png)

1. Renseignez les champs [!DNL Context] et [!DNL Items] dans la section [!DNL Editor]. Voir [Syntaxe du langage de requête](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f) pour obtenir des instructions sur la syntaxe.

1. Enregistrez le fichier.

   Les valeurs de l&#39;exemple précédent génèrent une formule de statut affichée comme suit :

   ![](assets/more_status_panel.png)
