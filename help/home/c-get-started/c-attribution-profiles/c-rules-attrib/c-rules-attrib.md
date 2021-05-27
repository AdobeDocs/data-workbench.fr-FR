---
description: Grâce au nouveau profil d’attribution basé sur des règles dans Data Workbench, vous pouvez rapidement analyser les événements d’attribution et attribuer des responsabilités en vue d’une conversion réussie définie par vous. Le profil d’attribution contient les informations nécessaires à votre architecte de données pour configurer et étendre ses fonctionnalités. Il comprend également des espaces de travail préconfigurés permettant à votre analyste d’intervenir directement et de commencer à analyser.
title: Profil d’attribution
uuid: 500e9e86-cffc-4f0d-a397-6521b493bf9a
exl-id: 29946f22-1d39-44ca-9474-13dbe228751c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---

# Profil d’attribution{#attribution-profile}

Grâce au nouveau profil d’attribution basé sur des règles dans Data Workbench, vous pouvez rapidement analyser les événements d’attribution et attribuer des responsabilités en vue d’une conversion réussie définie par vous. Le profil d’attribution contient les informations nécessaires à votre architecte de données pour configurer et étendre ses fonctionnalités. Il comprend également des espaces de travail préconfigurés permettant à votre analyste d’intervenir directement et de commencer à analyser.

Le profil d’attribution vous permet d’acquérir une nouvelle perspective sur les relations entre vos efforts marketing et une génération de prospects client réussie ou une conversion de ventes. Le profil d’attribution vous aide à qualifier les interactions qui doivent recevoir une attribution de crédit pour les recettes réalisées ou la participation en aval dans le parcours client. Elle permet d’identifier l’impact de vos efforts et coûts marketing en vous permettant d’analyser rapidement les événements d’attribution, puis d’attribuer la responsabilité des premières ou dernières touches ou d’autres événements menant à une vente réussie.

<!-- <a id="section_648A288E4CA84D579884BC161085C4D5"></a> -->

>[!IMPORTANT]
>
>Le profil Attribution est configuré pour une utilisation immédiate par les utilisateurs qui ont mis en oeuvre le profil SC d’Adobe qui utilise le flux de données Analytics (SC/Insight). Par défaut, les événements Marketing et Conversion sont utilisés comme types d’interactions par défaut évalués dans les modèles basés sur des règles fournis.

Voir [Déploiement du profil d’attribution](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-profile-deploy.md#concept-fbcb5800cd6a40cc901e61f3882988c0) et [Modèles d’attribution](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-models.md#concept-e209c7e86a5c4008ad6d78fdf4ea032d) pour plus d’informations.

## Espaces de travail de l’architecture et des analyses {#section-27c6aff70ba147cca6e11451e127afb4}

Dans le profil d’attribution, les espaces de travail Architecte et Analyste sont définis sur des onglets distincts dans le Workbench.

![](assets/attribution_profile_tabs.png)

**Espaces de travail d’architecture**

Dans l’onglet **Attribution**, cliquez sur l’onglet **[!UICONTROL Architect Workspace]** pour ouvrir les espaces de travail spécialement conçus pour configurer vos fichiers de configuration pour la modélisation d’attribution de base.

![](assets/attribution_profile_arch.png)

L’onglet Architecture comprend des espaces de travail pour parcourir chacun des fichiers de configuration dans le dossier du jeu de données de profil. Par exemple, **[!UICONTROL Attribution Configuration - Step 1]** vous permet d’identifier les valeurs d’attribution dans la section Transformation du fichier [!DNL profile.cfg].

![](assets/attribution_profile_arch_step1.png)

**Espaces de** travail d’analyste Cliquez sur l’ **[!UICONTROL Analyst]** **[!UICONTROL Workspaces]** onglet pour ouvrir l’analyse prédéfinie des espaces de travail à l’aide des dimensions et des mesures fournies avec le profil d’attribution.

Ces espaces de travail sont organisés en quatre catégories :

1. **Les** rapports de base présentent un modèle unique dans un espace de travail.
1. **Les** rapports comparatifs ont étendu les analyses en présentant plusieurs modèles dans une seule vue.
1. **Les** rapports d’enquête étendent les modèles de rapport pour présenter les modèles d’attribution dans différents formats. Cette section présente également et expose les ratios de pondération basés sur la position.
1. **Les** rapports de cheminement offrent une visibilité sur le parcours marketing du client avec plusieurs visualisations de cheminement afin d’explorer et d’exprimer pleinement les flux de processus et les chemins d’interaction.

![](assets/attribution_profile_analyst.png)

L’onglet Analyste comprend des espaces de travail préconfigurés avec des rapports. Par exemple, **[!UICONTROL First Attribution]** vous permet de sélectionner dans le tableau **[!UICONTROL Campaign]** l’attribution **[!UICONTROL Revenue]** en fonction de **[!UICONTROL Time]**.

![](assets/attribution_profile_analyst_step1.png)
