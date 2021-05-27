---
description: Les notes de mise à jour de Data Workbench 6.1 comprennent les nouvelles fonctionnalités, les exigences de mise à niveau, les correctifs de bogues et les problèmes connus.
title: Notes de mise à jour Data Workbench 6.1
uuid: 5bfb558a-ce85-4b4a-95dc-ccef337c4d1b
exl-id: ed37a00f-b4cd-428e-abb7-7c52d5cfd2f9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 2%

---

# Notes de mise à jour Data Workbench 6.1{#data-workbench-release-notes}

Les notes de mise à jour de Data Workbench 6.1 comprennent les nouvelles fonctionnalités, les exigences de mise à niveau, les correctifs de bogues et les problèmes connus.

## Nouvelles fonctionnalités {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.1 comprend les nouvelles fonctionnalités suivantes :

| Fonctionnalités  | Description |
|--- |--- |
| Mise à niveau Windows 64 bits | Les composants serveur Data Workbench, serveur de rapports et client sont mis à niveau pour s’exécuter uniquement sur les systèmes d’exploitation Windows 64 bits. |
| Score de propension | La notation de votre audience vous permet d’identifier la fidélité de vos clients et de percevoir statistiquement qui est susceptible de convertir une vente ou d’interagir avec un article ou une campagne. Le score de propension inclut désormais ces visualisations pour afficher les modèles et afficher la corrélation modifiée des mesures sélectionnées.<ul><li>La visionneuse de modèles examine un modèle de régression logistique généré avec un score de propension, indiquant le poids du coefficient de chaque variable d’entrée (y compris le terme constant) et leur plage d’erreurs statistiques. </li><li>Les graphiques Effet élévateur et Gain sont utilisés pour évaluer l’augmentation potentielle d’un modèle de données notées.</li><li>La matrice de confusion donne quatre chiffres en fonction de la combinaison de l’option Réel positif (AP), Négatif réel (AN), Positif prédit (PP) et Négatif prédit (PN).</li> <li>À partir de la version 6.1, vous disposez désormais d’une option Enregistrer pour enregistrer les scores de propension en fonction de deux types : dimensions ou dimensions et mesures.</li><li>Vous pouvez maintenant cliquer sur Ctrl+Alt et faire glisser et déposer pour ajouter des éléments dans le score de propension et le créateur de cluster. Avant d’ajouter des éléments de tableau, vous deviez les faire glisser du tableau vers la zone Eléments.</li></ul> |
| Outils de données en chinois | Data Workbench prend désormais en charge le chinois simplifié pour l’application cliente. Data Workbench prend également en charge l’éditeur de méthode d’entrée (IME) en tant que processus de saisie de texte secondaire pour les langues internationales. |
| Fonctions mathématiques | Vous pouvez désormais ajouter des fonctions mathématiques aux mesures, aux transformations mathématiques et aux cellules de feuille de calcul afin de calculer davantage les jeux de données. |
| Légendes statistiques | Les tableaux offrent désormais un appel d’expiration de résumé des statistiques pour les colonnes de mesures. L’appel sortant peut afficher la moyenne, l’écart type, les valeurs minimale et maximale, la variance et le nombre total pour la colonne. Il peut être pris en compte dans toute sélection et évaluation. |
| Filtre Matrice de corrélation | La matrice de corrélation a été mise à jour avec un filtre binaire afin de vous permettre de limiter les valeurs pour l’une des mesures corrélées ou pour les deux, ce qui vous permet de mieux cibler votre comparaison. En outre, vous pouvez désormais ajouter des éléments de Dimension à partir d’un tableau de Dimension en cliquant sur Ctrl + Alt et en faisant glisser les éléments vers la colonne ou la ligne de matrice à évaluer. |
| Masquage du libellé Abandon dans la visualisation entonnoir | Basculez entre l’affichage et le masquage des libellés d’abandon dans une visualisation Entonnoir en cliquant avec le bouton droit sur le titre et en sélectionnant Masquer les abandons. |

## Tri des colonnes du tableau{#sorting-table-columns}

Triez les colonnes du tableau par ordre alphabétique ou par ordre ordinal.

Pour mieux sélectionner les éléments d&#39;une table de Dimension, vous pouvez classer la première colonne par ordre alphabétique ou par ordre ordinal en sélectionnant l&#39;option de menu **[!UICONTROL Sort]**.

Le caractère # s’affiche lorsqu’une colonne est triée par ordinaux (valeur par défaut).

**Sélectionner l’option de tri**

Pour modifier les options de tri entre l’ordinal et l’alphabet, cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Sort]**. Cliquez sur la flèche pour inverser l’ordre.

![](assets/sort_table_alpha.png)

>[!NOTE]
>
>Vous pouvez trier les autres colonnes par ordonnée en cliquant sur le nom de la colonne.

## Masquage des étiquettes d’abandons dans l’entonnoir

Permet d’ouvrir les libellés d’abandon dans une visualisation Entonnoir.

La visualisation Entonnoir identifie le moment où un client abandonne une campagne marketing ou se détourne d’un chemin de conversion défini lors de l’interaction avec votre site web ou votre campagne cross-canal. Le côté gauche de la visualisation Entonnoir affiche les résultats d’une visite ou de visiteurs, tandis que le côté droit affiche les &quot;Abandons&quot; de ceux qui abandonnent un chemin spécifié.

![](assets/c_funnel_hide_fallout.png)

Dans une visualisation **[!UICONTROL Funnel]**, vous pouvez cliquer avec le bouton droit sur le titre et sélectionner **[!UICONTROL Hide Fallout]** dans le menu pour masquer les libellés des abandons.

## Problèmes connus {#section-ff2180c6871c413480e15fa915c253b9}

* Lors de l&#39;import d&#39;un espace de travail, un message d&#39;erreur s&#39;affiche même si l&#39;import a réussi.

   Solution : Cliquez sur OK pour ignorer l’erreur. L&#39;espace de travail a bien été importé.

**Problèmes de localisation en chinois simplifié**

* Le titre et le message de la boîte de dialogue qui s’affichent après avoir cliqué sur &quot;Envoyer&quot; lors de la définition de la cible dans la visualisation Notation sont illisibles.

   Solution : Aucun.
* Lors de l’utilisation du retour automatique à la ligne dans la visualisation de feuille de calcul, les mots localisés ne sont pas correctement encapsulés. Des caractères indésirables supplémentaires sont ajoutés à la chaîne.

   Solution : Aucun
* Impossible de lancer [!DNL Insight.exe] si le répertoire d’installation est nommé avec des caractères non anglais.

   Solution : Conservez les noms par défaut ou renommez en utilisant uniquement des caractères anglais dans le chemin du dossier pour lancer les exécutables.
