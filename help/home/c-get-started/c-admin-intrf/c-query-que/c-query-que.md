---
description: Normalement, le serveur de Data Workbench répond aux requêtes d’utilisateur entrantes dès leur réception et continue à fournir des résultats et des mises à jour en temps réel jusqu’à ce que l’utilisateur ne les demande plus.
title: File d’attente de la requête
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
exl-id: 5d9b20bf-9396-4016-beed-cee8f533f3ea
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 1%

---

# File d’attente de la requête{#query-queue}

Normalement, le serveur de Data Workbench répond aux requêtes d’utilisateur entrantes dès leur réception et continue à fournir des résultats et des mises à jour en temps réel jusqu’à ce que l’utilisateur ne les demande plus.

Par moments, en particulier sur les systèmes avec de nombreux utilisateurs Data Workbench, le nombre de requêtes principales nécessite plus de ressources système que celles disponibles sur le serveur. [!DNL Query Queue] permet au serveur de suspendre temporairement certaines requêtes jusqu&#39;à ce que les ressources nécessaires pour fournir des réponses deviennent disponibles. [!DNL Query Queue] fournit également des fonctionnalités permettant de classer les requêtes par priorité en fonction de divers paramètres, de sorte que, en cas de conflit de ressources, les requêtes de priorité supérieure reçoivent la première réponse.

Les requêtes d’un client ou d’un serveur de rapports unique sont placées dans un groupe et planifiées comme une unité. Vous pouvez configurer des moniteurs de ressources pour limiter la quantité de certaines ressources système utilisées par les requêtes. Lorsque les ressources surveillées permettent la planification d&#39;un autre groupe de requêtes, le groupe de priorité la plus élevée est planifié. Les utilisateurs dont les requêtes ne sont pas encore planifiées, en raison de limitations de ressources, ne reçoivent pas d’erreur mais sont avertis que leurs requêtes sont mises en file d’attente et que l’utilisateur peut continuer à travailler sur l’échantillon local.

La configuration par défaut comprend une configuration simple pour [!DNL Query Queue], mais la désactive. Les administrateurs peuvent activer ou désactiver [!DNL Query Queue], configurer des moniteurs de ressources pour déterminer la quantité de ressources utilisées pour l&#39;interrogation et configurer des stratégies de hiérarchisation complexes pour différents utilisateurs.

**Pour configurer le fichier Server.cfg pour[!DNL Query Queuing]**

1. Ouvrez [!DNL Server.cfg] en cliquant sur **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**.
1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL Server.cfg]** et rendez-le local pour modification.
1. Développer [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Configurez les paramètres suivants :

   * **Groupes d’utilisateurs : vous** permet de configurer les stratégies, les utilisateurs et la priorité de la file d’attente. Voir [Groupes d’utilisateurs de la file d’attente de Requête](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) pour les définitions.

   * **Principal:** (Vector) Active ou désactive la  [!DNL Query Queue]variable. Les valeurs valides sont true ou false. Le paramètre par défaut est false.

   * **Groupe d’utilisateurs par défaut :**  (chaîne) Entrez le nom du groupe d’utilisateurs auquel les utilisateurs sont ajoutés, s’ils ne sont répertoriés dans aucun groupe d’utilisateurs.
   * **Moniteurs de ressources :** (vectoriel) cliquez avec le bouton droit de la souris pour ajouter un moniteur de ressources. Vous pouvez spécifier si [!DNL Query Queue] surveille la mémoire ou le nombre de requêtes. Cliquez avec le bouton droit de la souris sur **[!UICONTROL Resource Monitor]** pour sélectionner Moniteur du budget mémoire ou Moniteur du nombre de Requêtes. Voir [Requête Queue Resource Monitors](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) pour plus d&#39;informations.

   * **Priorité intouchable :**  (Int) indique que les lots dont la priorité est supérieure ou égale à cette valeur ne sont jamais prévenus de la planification des lots de priorité supérieure. Utilisé conjointement avec la [!DNL Memory Budget Monitor] décrite dans la [table Paramètres du groupe d’utilisateurs](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1).
