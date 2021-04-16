---
description: Utilisez le profil historique des outils de données pour déterminer comment la configuration, le matériel et d’autres modifications affectent les performances, la stabilité et la capacité du serveur au fil du temps.
title: Espace de travail de l’historique de Data Workbench
uuid: 61c45cae-f255-4d20-bb6b-f318c8dd8214
exl-id: e6d7e924-641e-468c-a828-16ebe1c8724f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 2%

---

# Espace de travail de l’historique de Data Workbench{#data-workbench-historic-workspace}

Utilisez le profil historique des outils de données pour déterminer comment la configuration, le matériel et d’autres modifications affectent les performances, la stabilité et la capacité du serveur au fil du temps.

Le profil historique comprend un jeu de données [Performances du Profil](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-184a86f9de054970bf68515bb9dea85d) basé sur le profil et un jeu de données [Performances du serveur](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5dad5870384b40e094d50173fcd90a09) basé sur le serveur sous l&#39;onglet **[!UICONTROL Performance]**. Il s’agit des jeux de données les plus couramment utilisés, consultés pour une perspective antérieure des performances du serveur de l’outil de données. En outre, vous pouvez vue les [Composants](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) et [Mode de traitement](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) en sélectionnant l&#39;onglet **[!UICONTROL Up Time]**.

![](assets/Historic_Performance.png)

En outre, vous pouvez vue les [Composants](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) et [Mode de traitement](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) en sélectionnant l&#39;onglet **[!UICONTROL Up Time]**.

Pour obtenir des informations de référence supplémentaires sur les dimensions utilisées dans le profil historique de l&#39;outil de données, voir [Dimensions dans le profil historique d&#39;Insight.](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)

## Espace de travail Performances du profil {#section-184a86f9de054970bf68515bb9dea85d}

Ce jeu de données comprend les mesures pertinentes suivantes pour la surveillance des outils de données.

* MégaBytes d’entrée rapide par minute : mesures affichant une entrée importante de données lors du traitement initial du journal.
* Fusion rapide MégaBytes par minute : mesures affichant la transformation.

![](assets/Historic_Profile_Performance.png)

>[!NOTE]
>
>Pour évaluer les performances réelles de votre profil, observez le taux plutôt que le temps calendaire écoulé. Le taux est mesuré comme les valeurs modifiées entre l’interrogation toutes les dix minutes.

## Espace de travail Performances du serveur {#section-5dad5870384b40e094d50173fcd90a09}

Ce jeu de données surveille les mesures de serveur au-delà de la portée des profils inclus et inclut les mesures de serveur appropriées suivantes pour la surveillance des outils de données.

* Estimation du nombre de minutes de balayage — Estimation du temps de résolution des requêtes.
* Latence du sondage Millisecondes — Indicateur de la charge de travail des logiciels en mesurant le temps nécessaire pour passer à travers un cycle complet de maintenance de chaque composant.

![](assets/Historic_Server_Performance.png)

## Espace de travail Composants {#section-5be7223abb384784bafe7b37c764ea66}

Ce jeu de données se trouve sous l’onglet Heure de mise en service.

![](assets/Up_Time.png)

Le jeu de données Composants comprend deux aspects pour l’intégrité des composants :

* Mesure des communications : le processus du serveur de l’outil de données a-t-il répondu ?
* Mesure Tous les composants : en haut de la page État détaillé se trouve la liste des composants que l&#39;hôte traite dans les processus du serveur de l&#39;outil de données. Si un composant est à l’état d’erreur, il est répertorié sous la table Composants dans le tableau Erreur.

![](assets/Up_Time_components.png)

## Espace de travail Mode de traitement {#section-3e1dedb9474e4b4ba513240943e76817}

Cet espace de travail se trouve sous l’onglet Heure de fonctionnement. Cet espace de travail vous permet d’observer le temps passé en mode d’entrée rapide, de fusion rapide et de fusion en temps réel.

![](assets/Up_Time_Processing_mode.png)

Ce jeu de données fournit d&#39;importantes caractéristiques de charge de serveur, telles que l&#39;identification de la charge de données pour

* Jour de la semaine (par exemple, un taux d&#39;entrée rapide le mardi et le mercredi),
* Heure du jour (quel pourcentage de la journée est-il en mode Entrée rapide ?)
