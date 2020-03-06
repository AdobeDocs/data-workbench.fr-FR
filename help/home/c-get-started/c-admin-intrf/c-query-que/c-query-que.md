---
description: Normalement, le serveur Outils de données répond aux requêtes des utilisateurs entrants dès leur réception et continue à fournir des résultats et des mises à jour en temps réel jusqu’à ce que l’utilisateur ne les demande plus.
solution: Analytics
title: File d'attente de requête
topic: Data workbench
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# File d&#39;attente de requête{#query-queue}

Normalement, le serveur Outils de données répond aux requêtes des utilisateurs entrants dès leur réception et continue à fournir des résultats et des mises à jour en temps réel jusqu’à ce que l’utilisateur ne les demande plus.

Parfois, en particulier sur les systèmes avec de nombreux utilisateurs des outils de données, le nombre de requêtes actives nécessite plus de ressources système que celles disponibles sur le serveur. [!DNL Query Queue] permet au serveur de suspendre temporairement certaines requêtes jusqu&#39;à ce que les ressources nécessaires pour fournir des réponses deviennent disponibles. La [!DNL Query Queue] section fournit également des fonctionnalités pour classer les requêtes par priorité en fonction de divers paramètres, de sorte que, en cas de conflit de ressources, les requêtes de priorité plus élevée reçoivent une réponse en premier.

Les requêtes d’un client ou d’un serveur de rapports unique sont placées dans un groupe et planifiées comme une unité. Vous pouvez configurer des moniteurs de ressources pour limiter la quantité de certaines ressources système utilisées par les requêtes. Lorsque les ressources surveillées permettent la planification d&#39;un autre groupe de requêtes, le groupe de priorités les plus élevées est planifié. Les utilisateurs dont les requêtes ne sont pas encore planifiées, en raison des limites de ressources, ne reçoivent pas d’erreur, mais sont avertis que leurs requêtes sont mises en file d’attente et que l’utilisateur peut continuer à travailler sur l’exemple local.

La configuration par défaut comprend une configuration simple pour le [!DNL Query Queue], mais la désactive. Les administrateurs peuvent activer ou désactiver [!DNL Query Queue], configurer des moniteurs de ressources afin de déterminer la quantité de ressources utilisées pour l’interrogation et configurer des stratégies de hiérarchisation complexes pour différents utilisateurs.

**Pour configurer le fichier Server.cfg pour[!DNL Query Queuing]**

1. Ouvrez [!DNL Server.cfg] en cliquant sur **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**.
1. Cliquez avec le bouton droit **[!UICONTROL Server.cfg]** et rendez-le local pour le modifier.
1. Développer [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Configurez les paramètres suivants :

   * **Groupes d’utilisateurs :** Permet de configurer les stratégies, les utilisateurs et la priorité de la file d’attente. Voir Groupes [d’utilisateurs de la file d’attente de](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) requêtes pour obtenir des définitions.

   * **Actif :** (Vectorisation) Active ou désactive la [!DNL Query Queue]. Les valeurs valides sont true ou false. Le paramètre par défaut est false.

   * **Groupe d’utilisateurs par défaut :** (Chaîne) Entrez le nom du groupe d’utilisateurs auquel les utilisateurs sont ajoutés, s’ils ne sont répertoriés dans aucun groupe d’utilisateurs.
   * **Moniteurs de ressources :** (Vector) Cliquez avec le bouton droit de la souris pour ajouter un moniteur de ressources. Vous pouvez indiquer si le moniteur [!DNL Query Queue] surveille la mémoire ou le nombre de requêtes. Cliquez avec le bouton droit **[!UICONTROL Resource Monitor]** pour sélectionner Moniteur du budget de la mémoire ou Moniteur du nombre de requêtes. Voir Moniteurs [de ressources de file d’attente de](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) requêtes pour plus d’informations.

   * **Priorité intouchable :** (Int) Indique que les lots dont la priorité est supérieure ou égale à cette valeur ne sont jamais prévenus de la planification des lots de priorité supérieure. Utilisé conjointement avec la [!DNL Memory Budget Monitor] description du tableau [Paramètres du groupe d’](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)utilisateurs.

