---
description: La barre latérale permet d’accéder aux fonctions régulièrement utilisées et conserve les visualisations lorsque vous passez d’un espace de travail à un autre.
solution: Analytics
title: Configuration de la barre latérale
topic: Data workbench
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration de la barre latérale{#configure-the-sidebar}

La barre latérale permet d’accéder aux fonctions régulièrement utilisées et conserve les visualisations lorsque vous passez d’un espace de travail à un autre.

Les administrateurs peuvent personnaliser une barre latérale pour la rendre adaptée aux différents groupes d’utilisateurs, puis déployer la barre latérale avec un profil.

La barre latérale est idéale pour vous aider à surveiller les filtres et les remplacements locaux. Si vous préférez ne pas utiliser la barre latérale, vous pouvez la masquer.

## Ajout de visualisations à la barre latérale {#section-666f70a405db4f8d8eaffa567ffcac06}

1. Lancez Outils de données.
1. Dans la barre latérale, cliquez sur **[!UICONTROL Add]** > *&lt;**[!UICONTROL item]**>*. For example, [!DNL Selections Panel], [!DNL Filters Panel], or [!DNL Table].

   Les panneaux latéraux suivants sont disponibles dans l’installation standard des outils de données. D’autres éléments peuvent être disponibles dans votre profil spécifique :

   * **Panneau Sélections :** Vous permet de comprendre les sélections actives dans l’espace de travail actuel. Les [!DNL Selections Panel] mises à jour se produisent chaque fois que vous effectuez une nouvelle sélection. Vous pouvez effacer les sélections en cliquant sur **[!UICONTROL x]**. Voir [Sélection dans les visualisations](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746) pour en savoir plus sur la manière de sélectionner des données.
   * **Panneau Filtres :** Facilite le chargement et l’application de filtres enregistrés. Vous pouvez charger plusieurs filtres et activer ou désactiver chacun d’eux indépendamment en cochant la case en regard de celui-ci. Voir [Filtrage des éditeurs](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **Panneau de remplacement local :** Ce panneau affiche les mesures, dimensions et filtres présents dans le profil qui ont été modifiés dans votre copie personnelle du profil. Cela vous permet d’identifier les différences possibles entre la manière dont les données apparaissent dans votre client et celle des autres utilisateurs. Lorsque vous enregistrez des modifications dans une mesure, une dimension ou un filtre sur le serveur, le remplacement est supprimé du [!DNL Local Overrides panel]. Si vous cliquez sur un remplacement, puis cliquez sur **[!UICONTROL Revert to Server]**, le remplacement local est supprimé et l’élément revient à la version partagée.
   * **Légende de la mesure :** Ajoute une légende de mesure. [!DNL Metric legends] vous permet d’afficher les mesures de base liées à votre profil et les statistiques liées au jeu de données (ou à la sélection actuelle, le cas échéant). Voir Légendes [mesures](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
   * **Légende des couleurs :** Ajoute une légende de couleur. Vous pouvez coder en couleur les visualisations par mesures, telles que Conversion et Rétention, et les utiliser dans presque toutes les [!DNL Workspace]. Le lien entre les mesures de l’entreprise et la couleur facilite la détection des anomalies, des exceptions et des tendances. Voir Légendes [](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)couleur.
   * **Annotation de texte :** Ajoute un panneau de notes. [!DNL Text annotations] sont des fenêtres dans lesquelles vous pouvez entrer du texte arbitraire pour ajouter des informations descriptives ou des commentaires à une [!DNL Workspace]. Voir [Utilisation des annotations](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777)de texte.
   * **Tableau :** Ajoute un tableau. Un tableau peut afficher une ou plusieurs mesures sur une ou plusieurs dimensions de données. Voir [Tableaux](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).
   * **Ouvrir :** Ouvre un fichier enregistré.

## Ouverture d’un panneau latéral {#section-cbc8e57491854274a577d47a48c306b8}

Vous pouvez ouvrir un fichier de visualisation de l’encadré à partir d’un emplacement enregistré ou du Presse-papiers.

1. Dans la barre latérale, cliquez sur **[!UICONTROL Add]** > **[!UICONTROL Open]**.
1. Cliquez sur **[!UICONTROL File]** pour localiser le [!DNL .vw] fichier du panneau à ajouter ou cliquez sur **[!UICONTROL Last Closed Window]**, ce qui extrait la visualisation du Presse-papiers.

   De plus, vous pouvez cliquer **[!UICONTROL From Clipboard]** pour coller une visualisation copiée dans le Presse-papiers. Voir [Copie d’un panneau](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1)de zone latérale.

## Copie d’un panneau de zone latérale {#section-720ae057632a4b8dbb94412e06a370b1}

1. Cliquez avec le bouton droit sur la bordure supérieure du panneau, puis cliquez sur **[!UICONTROL Copy]** > **[!UICONTROL Window]**.
1. Pour coller le panneau, cliquez sur **[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**.

## Enregistrement d’un panneau latéral {#section-fb19936b12704fb0a4c592abb579db1d}

Sur un panneau latéral, cliquez avec le bouton droit dans la barre de titre et cliquez sur **[!UICONTROL Save]**.

De même, vous pouvez ouvrir une visualisation de l’encadré enregistrée. Les outils de données enregistrent la visualisation sous forme de [!DNL .vw] fichier à l’emplacement spécifié.

## Revenir à la barre latérale par défaut {#section-4d14b8771ad747bba799876267f24831}

Dans la barre latérale, cliquez sur **[!UICONTROL Options]** > **[!UICONTROL Revert]**.

Lorsque vous fermez Outils de données, le système enregistre la configuration actuelle de la barre latérale dans le [!DNL sidebar.vw] fichier du profil utilisateur. Lorsque vous ouvrez Outils de données, le système charge le [!DNL sidebar.vw] fichier à partir du profil utilisateur, plutôt qu’à partir d’un profil parent.

Vous pouvez rétablir une barre latérale par défaut ou enregistrée précédemment, ce qui supprime la barre latérale du profil utilisateur et la recharge du profil parent. Les administrateurs peuvent remplacer la barre latérale par défaut (parent) par une barre latérale locale en la téléchargeant depuis la [!DNL Profile Manager].

## Personnalisation du fichier Plus de panneau d’état {#section-8d502f3b59cc4331966edec05e896ce1}

Les administrateurs système peuvent créer des formules dans la [!DNL More Status Panel.vw]section. Les mots contextuels sont alors placés autour des valeurs de mesure et de dimension, et les résultats s’affichent dans la [!DNL More Status panel] barre latérale.

Pour afficher la [!DNL More Status panel] barre latérale, cliquez sur les flèches affichées dans l’exemple suivant.

![](assets/more_status_panel_arrows.png)

La procédure suivante illustre un exemple simple de création d’un état personnalisé qui vous indique le nombre de jours d’un jeu de données :

1. Dans la [!DNL Profile Manager], cliquez sur **[!barre latérale UICONTROL\]**.

1. Dans la [!DNL Base_5_3*] colonne, effectuez une copie locale du [!DNL More Status Panel.vw] fichier.

   Pour ce faire, cliquez avec le bouton droit de la souris sur la coche du fichier, puis cliquez sur **[!UICONTROL Make Local]**.

1. Ouvrez le [!DNL More Status Panel.vw] fichier dans le [!DNL .vw] [!DNL Editor] Bloc-notes ou dans le Bloc-notes.

   ![](assets/more_status_panel_file.png)

1. Renseignez les champs [!DNL Context] et [!DNL Items] dans le [!DNL Editor]. Voir Syntaxe [du langage de](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f) requête pour obtenir des instructions sur la syntaxe.

1. Enregistrez le fichier.

   Les valeurs de l’exemple précédent génèrent une formule d’état affichée comme suit :

   ![](assets/more_status_panel.png)

