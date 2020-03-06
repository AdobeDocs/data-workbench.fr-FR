---
description: Les notes de mise à jour des outils de données version 6.1 comprennent les nouvelles fonctionnalités, les exigences de mise à niveau, les correctifs de bogues et les problèmes connus.
solution: Analytics
title: Notes de mise à jour des outils de données version 6.1
topic: Data workbench
uuid: 5bfb558a-ce85-4b4a-95dc-ccef337c4d1b
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.1 Release Notes{#data-workbench-release-notes}

Les notes de mise à jour des outils de données version 6.1 comprennent les nouvelles fonctionnalités, les exigences de mise à niveau, les correctifs de bogues et les problèmes connus.

## Nouvelles fonctionnalités {#section-1225066ea8f44cf68e42e019d0bca816}

Les outils de données version 6.1 comprennent les nouvelles fonctionnalités suivantes :

| Fonctionnalités  | Description |
|--- |--- |
| Mise à niveau Windows 64 bits | Les composants du serveur de outils de données, du serveur de rapports et du client sont mis à niveau pour fonctionner uniquement sur les systèmes d’exploitation Windows 64 bits. |
| Score de propension | Le score de votre audience permet d’identifier la fidélité de la clientèle et de percevoir statistiquement qui est susceptible de convertir une vente ou d’interagir avec un article ou une campagne. Le score de propension inclut désormais ces visualisations pour afficher les modèles et afficher la corrélation changeante des mesures sélectionnées.<ul><li>La visionneuse de modèles examine un modèle de régression logistique généré avec le score de propension, montrant les pondérations de coefficient de chaque variable d’entrée (y compris le terme constant) et leur plage d’erreurs statistiques. </li><li>Les graphiques Effet élévateur et Gain sont utilisés pour évaluer l’augmentation potentielle d’un modèle de données notées.</li><li>La matrice de confusion donne quatre valeurs en fonction de la combinaison des valeurs Positif réel (AP), Négatif réel (AN), Positif prédit (PP) et Négatif prédit (PN).</li> <li>A partir de la version 6.1, vous disposez désormais d’une option Enregistrer pour enregistrer les scores de propension en fonction de deux types : dimensions ou dimensions et mesures.</li><li>Vous pouvez désormais cliquer sur Ctrl-Alt et faire glisser et déposer pour ajouter des éléments dans le score de propension et le créateur de grappes. Avant d’ajouter des éléments de tableau, vous deviez les faire glisser du tableau vers la zone Eléments.</li></ul> |
| Outils de données en chinois | Les outils de données prennent désormais en charge le chinois simplifié pour l’application cliente. Les outils de données prennent également en charge l’éditeur de méthode d’entrée (IME) comme processus secondaire de saisie de texte pour les langues internationales. |
| Fonctions mathématiques | Vous pouvez désormais ajouter des fonctions mathématiques aux mesures, aux transformations mathématiques et aux cellules de feuille de calcul pour calculer davantage les jeux de données. |
| Légendes statistiques | Les tableaux proposent désormais un appel à l’expiration du résumé des statistiques pour les colonnes de mesures. L’appel peut afficher la moyenne, l’écart type, les valeurs minimale et maximale, la variance et le nombre total de la colonne. Il peut être pris en compte dans toute sélection et évaluation. |
| Filtre Matrice de corrélation | La matrice de corrélation a été mise à jour avec un filtre binaire afin de vous permettre de limiter les valeurs d’une ou des deux mesures corrélées, ce qui vous permet de mieux cibler votre comparaison. Vous pouvez également maintenant ajouter des éléments de dimension à partir d’un tableau Dimension en cliquant sur Ctrl + Alt et en faisant glisser les éléments vers la colonne ou la ligne de la matrice à évaluer. |
| Masquer l’étiquette Abandon dans la visualisation de l’entonnoir | Basculez entre l’affichage et le masquage des libellés d’abandon dans une visualisation Entonnoir en cliquant avec le bouton droit sur le titre et en sélectionnant Masquer les abandons. |

## Tri des colonnes du tableau{#sorting-table-columns}

Triez les colonnes du tableau par ordre alphabétique ou par ordinaux.

Pour mieux sélectionner les éléments d’un tableau Dimension, vous pouvez classer la première colonne par ordre alphabétique ou par ordinaux en sélectionnant l’option de **[!UICONTROL Sort]** menu.

Le caractère # s’affiche lorsqu’une colonne est triée par ordinaux (valeur par défaut).

**Sélectionner l’option de tri**

Pour modifier les options de tri entre ordinal et alphabet, cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Sort]**. Cliquez sur la flèche pour inverser l’ordre.

![](assets/sort_table_alpha.png)

>[!NOTE]
>
>Vous pouvez trier les autres colonnes par ordinal en cliquant sur le nom de la colonne.

## Masquer les étiquettes d&#39;abandons dans l&#39;entonnoir

Active/désactive l’ouverture des libellés d’abandon dans une visualisation Entonnoir.

La visualisation Entonnoir identifie où un client abandonne une campagne marketing ou s’éloigne d’un chemin de conversion défini lors de l’interaction avec votre site Web ou votre campagne cross-canal. Le côté gauche de la visualisation Entonnoir affiche les résultats d’une visite ou de visiteurs, tandis que le côté droit affiche les abandons de ceux qui abandonnent un chemin spécifié.

![](assets/c_funnel_hide_fallout.png)

Lors d’une **[!UICONTROL Funnel]** visualisation, vous pouvez cliquer avec le bouton droit sur le titre et sélectionner **[!UICONTROL Hide Fallout]** dans le menu pour masquer les étiquettes d’abandon.

## Problèmes connus {#section-ff2180c6871c413480e15fa915c253b9}

* Lors de l’importation d’un espace de travail, un message d’erreur s’affiche même si l’importation a réussi.

   Solution : Cliquez sur OK pour ignorer l’erreur. L&#39;importation de l&#39;espace de travail a réussi.

**Problèmes de localisation en chinois simplifié**

* Le titre et le message de la boîte de dialogue affichés après avoir cliqué sur &quot;Envoyer&quot; lors de la définition de la cible dans la visualisation Scoring sont illisibles.

   Solution : Aucun.
* Lors de l’utilisation de l’encapsulation de mot dans la visualisation Feuille de calcul, les mots localisés ne sont pas correctement encapsulés. Des caractères indésirables supplémentaires sont ajoutés à la chaîne.

   Solution : Aucun
* Impossible de lancer [!DNL Insight.exe] si le répertoire d’installation porte un nom avec des caractères non anglais.

   Solution : Conservez les noms par défaut ou renommez en utilisant uniquement des caractères anglais dans le chemin du dossier pour lancer les exécutables.
