---
description: Présente trois méthodes d’exportation des données et explique comment récupérer les exportations.
solution: Analytics
title: Exportation de données
topic: Data workbench
uuid: de37a60b-09db-4976-b427-f28b4697a8aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportation de données{#exporting-data}

Présente trois méthodes d’exportation des données et explique comment récupérer les exportations.

Les données peuvent être exportées à partir du tableau de bord de trois manières différentes.

Tout d’abord, vous pouvez exporter des données à partir d’une visualisation individuelle. Ensuite, vous pouvez exporter votre tableau de bord de travail actuel, y compris les configurations et les sélections que vous avez effectuées. Troisièmement, vous pouvez exporter un tableau de bord enregistré sans l&#39;ouvrir.

Les exportations sont effectuées à l’aide d’un processus en deux étapes. Tout d’abord, les exportations sont mises en file d’attente sur le serveur à l’aide de l’une des trois méthodes ci-dessus. L&#39;état de l&#39;exportation s&#39;affichera dans le **[!UICONTROL Exports]** menu au fur et à mesure de la préparation de l&#39;exportation. Ensuite, lorsque les exportations sont prêtes, vous pouvez télécharger les données au format CSV ou Excel.

Les exportations peuvent prendre plusieurs minutes, mais vous pouvez continuer à utiliser l’application pendant une exportation.

## Exportation de visualisations {#section-46b74b46c2eb44129c8b85a9eabd2304}

Pour exporter des données d’une visualisation, cliquez **[!UICONTROL Save]** dans le menu d’outils de la visualisation.

![](assets/export_visual.png)

Votre exportation sera lancée sur le serveur et un indicateur d&#39;exportation sera ajouté au menu Exportations.

![](assets/export_queued.png)

## Exportation de tableaux de bord {#section-27329f2a5fed44b49deb26dc5164531f}

Pour lancer une exportation de données à partir d’un tableau de bord de travail, sélectionnez **[!UICONTROL Export]** dans le **[!UICONTROL Dashboard]** menu.

![](assets/export_dashboard.png)

Votre exportation sera lancée sur le serveur et un indicateur d&#39;exportation sera ajouté au menu Exportations.

## Exportation de tableaux de bord enregistrés {#section-e989f7b16e25479ab77454f2c34471ba}

Pour lancer une exportation de données à partir d&#39;un tableau de bord enregistré, utilisez le navigateur de tableaux de bord. Dans le navigateur de tableaux de bord, accédez au tableau de bord de votre choix et sélectionnez-le pour que les détails du tableau de bord apparaissent. Dans le panneau des détails de droite, sous la **[!UICONTROL Operations]** section, sélectionnez **[!UICONTROL Export Data]**.

Votre exportation sera lancée sur le serveur et un indicateur d&#39;exportation sera ajouté au **[!UICONTROL Exports]** menu.

## Récupération des exportations {#section-0f03c5321c804867b7c72cf92f6f67d0}

Une fois l’exportation terminée, une notification contextuelle s’affiche pour vous informer que l’exportation est prête.

![](assets/export_ready.png)

Pour récupérer l’exportation, utilisez le **[!UICONTROL Exports]** menu. Cliquez sur la coche verte à droite de l’élément de l’exportation souhaité pour afficher un menu déroulant. Dans ce menu, sous le **[!UICONTROL Save Export As…]** sous-menu, sélectionnez l’option de menu appropriée pour télécharger l’exportation au format CSV ou Excel.

![](assets/export_save_as.png)

Le processus de téléchargement de fichiers de votre navigateur commence maintenant.

Les exportations ne sont pas supprimées automatiquement. Vous pouvez donc facilement télécharger l’exportation dans chaque format. Vous pouvez supprimer des exportations du **[!UICONTROL Exports]** menu du panneau de navigation de gauche. Sinon, elles seront automatiquement supprimées lorsque vous vous déconnectez.

Pour supprimer une exportation du **[!UICONTROL Export List]**, cochez la case à droite du titre de l’exportation et sélectionnez **[!UICONTROL Remove From List]**.

![](assets/export_remove_from_list.png)

