---
description: Il est recommandé de créer un tableau de bord même pour les besoins analytiques ponctuels à court terme.
title: Création d’un tableau de bord
uuid: 5b9e9db2-d7ac-4c97-8df0-74a9e5a0c496
exl-id: bd51d4c0-bcf2-4ba6-8b32-de06c74f359f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 1%

---

# Création d’un tableau de bord{#creating-a-dashboard}

Il est recommandé de créer un tableau de bord même pour les besoins analytiques ponctuels à court terme.

>[!NOTE]
>
>Les utilisateurs en lecture seule ne peuvent pas créer de tableaux de bord. Cette section s’applique uniquement aux utilisateurs réguliers et aux administrateurs.

Les utilisateurs peuvent décider de créer des tableaux de bord pour plusieurs raisons :

* Un nouveau tableau de bord peut être lancé de A à Z pour une analyse à la volée sans avoir l’intention de réutiliser ou de partager le tableau de bord.
* Un nouveau tableau de bord peut être créé dans le but d’effectuer votre propre analyse personnelle que vous souhaitez enregistrer et réutiliser, mais pas partager.
* Un nouveau tableau de bord peut être créé, enregistré et partagé pour vous et le reste de la population d’utilisateurs du tableau de bord à laquelle vous pouvez accéder. Quel que soit le cas, chaque scénario commence au même moment : un canevas de tableau de bord vierge.

>[!NOTE]
>
>Avant de commencer à créer votre tableau de bord, il est préférable de réduire votre pourcentage de requête à un niveau faible, comme 10 ou 25 %. Cela permet d’extraire des exemples de données de Data Workbench beaucoup plus rapidement qu’une requête complète. Puisque ces résultats échantillonnés sont renvoyés beaucoup plus rapidement, ils offrent une réactivité idéale tout en encadrant votre tableau de bord et votre analyse. Une fois que vous êtes prêt à exécuter des requêtes jusqu’à la fin, vous pouvez mettre à jour le paramètre query-to à 100 %. Pour ajuster la fin de la requête, voir le [Paramètre de requête](../../../home/c-adobe-data-workbench-dashboard/c-dashboards/c-query-to-parameter.md#concept-33db106e28bc4108bca9e8d0a440d323).

Pour créer un tableau de bord, sélectionnez **[!UICONTROL New]** dans le menu Tableau de bord .

![](assets/new_dashboard.png)

Un canevas de tableau de bord vierge, prêt à ajouter et à configurer des visualisations en fonction de vos besoins d’analyse, s’affiche. Pendant que vous travaillez, rien ne sera mis à jour sur le serveur tant que vous n’aurez pas enregistré.

Déterminez ensuite le type de données à afficher et la manière dont vous souhaitez l’afficher. Il est généralement utile de commencer par des visualisations de tableau pour voir les données brutes, puis de créer d’autres graphiques en fonction. Pour plus d’informations sur l’ajout et la configuration des visualisations, voir [Création de visualisations](../../../home/c-adobe-data-workbench-dashboard/c-visualizations/t-creating-visualizations.md#task-c6f1d20fa2484aeeb9a8487625054ecf). Après avoir ajouté et configuré les visualisations pour créer le tableau de bord, vous obtiendrez les éléments suivants :

![](assets/after_configure.png)

À partir de là, vous pouvez simplement analyser le tableau de bord et le supprimer, ou vous pouvez choisir d’enregistrer le tableau de bord sur le serveur pour le réutiliser et/ou le partager. Pour plus d’informations sur la façon d’interagir avec un tableau de bord afin d’effectuer une analyse, consultez la section [Réalisation de sélections dans le tableau de bord](../../../home/c-adobe-data-workbench-dashboard/c-making-selections-within-the-dashboard/c-making-selections-within-the-dashboard.md#concept-0989862de0044cc4bbfd7f4441275fc4).
