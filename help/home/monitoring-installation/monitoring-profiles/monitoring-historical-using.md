---
description: Utilisez le profil Historique des outils de données pour voir comment la configuration, le matériel et d’autres modifications affectent les performances, la stabilité et la capacité du serveur au fil du temps.
solution: Analytics
title: Espace de travail historique des outils de données
topic: Data workbench
uuid: 61c45cae-f255-4d20-bb6b-f318c8dd8214
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Espace de travail historique des outils de données{#data-workbench-historic-workspace}

Utilisez le profil Historique des outils de données pour voir comment la configuration, le matériel et d’autres modifications affectent les performances, la stabilité et la capacité du serveur au fil du temps.

Le profil Historique comprend un jeu de données Performances [du](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-184a86f9de054970bf68515bb9dea85d) profil basé sur le profil et un jeu de données Performances [du](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5dad5870384b40e094d50173fcd90a09) serveur basé sur le serveur sous l’ **[!UICONTROL Performance]** onglet. Il s’agit des jeux de données les plus fréquemment utilisés consultés pour une perspective antérieure des performances du serveur de l’outil de données. En outre, vous pouvez afficher les [composants](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) et le mode [de](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) traitement en sélectionnant l’ **[!UICONTROL Up Time]** onglet.

![](assets/Historic_Performance.png)

En outre, vous pouvez afficher les [composants](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) et le mode [de](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) traitement en sélectionnant l’ **[!UICONTROL Up Time]** onglet.

Pour plus d’informations de référence sur les dimensions utilisées dans le profil historique de l’outil de données, voir [Dimensions dans le profil historique d’Insight.](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)

## Espace de travail Performances du profil {#section-184a86f9de054970bf68515bb9dea85d}

Ce jeu de données comprend les mesures pertinentes suivantes pour la surveillance des outils de données.

* MégaOctets par minute d’entrée rapide : mesures affichant une entrée de données importante lors du traitement initial du journal.
* Fusion rapide MégaOctets par minute : mesures affichant la transformation.

![](assets/Historic_Profile_Performance.png)

>[!NOTE]
>
>Pour évaluer les performances réelles de votre profil, observez le taux plutôt que le temps calendaire écoulé. Le taux est mesuré comme les valeurs modifiées entre l’interrogation toutes les dix minutes.

## Espace de travail Performances du serveur {#section-5dad5870384b40e094d50173fcd90a09}

Ce jeu de données surveille les mesures de serveur au-delà de la portée des profils inclus et inclut les mesures de serveur appropriées suivantes pour la surveillance des outils de données.

* Estimation du nombre de minutes de balayage — Estimation du temps de résolution des requêtes.
* Latence du sondage en millisecondes — Indicateur de l&#39;activité des logiciels en mesurant le temps nécessaire pour passer par un cycle complet de maintenance de chaque composant.

![](assets/Historic_Server_Performance.png)

## Espace de travail Composants {#section-5be7223abb384784bafe7b37c764ea66}

Ce jeu de données se trouve sous l’onglet Heure de mise en service.

![](assets/Up_Time.png)

Le jeu de données Composants comprend deux aspects pour l’intégrité des composants :

* Mesure des communications — Le processus du serveur de l’outil de données a-t-il répondu ?
* Mesure Tous les composants — En haut de la page Etat détaillé se trouve la liste des composants que l’hôte traite au sein des processus du serveur de l’outil de données. Si un composant est à l’état d’erreur, il est répertorié sous Composants dans la table d’erreurs.

![](assets/Up_Time_components.png)

## Espace de travail Mode de traitement {#section-3e1dedb9474e4b4ba513240943e76817}

Cet espace de travail se trouve sous l’onglet Heure d’activation. Cet espace de travail vous permet d’observer le temps passé en mode d’entrée rapide, de fusion rapide et en temps réel.

![](assets/Up_Time_Processing_mode.png)

Ce jeu de données fournit d’importantes caractéristiques de charge du serveur, telles que l’identification de la charge de données pour

* Jour de la semaine (par exemple, un taux d&#39;entrée rapide le mardi et le mercredi),
* Heure du jour (quel pourcentage de la journée est-il en mode Entrée rapide ?)

