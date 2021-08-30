---
description: Cette section explique comment créer des mesures dans Data Workbench.
title: Configuration des mesures
uuid: 57c1410b-c09c-4a59-b3a1-575323e1b8e3
exl-id: a60c08d3-f708-43be-a14f-8b7f129f3ee5
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 3%

---

# Configuration des mesures{#metrics-setup}

Cette section explique comment créer des mesures dans Data Workbench.

## Présentation des mesures {#section-f0412e851fcb4ac9886dca4003d42cec}

Les mesures sont des informations quantitatives sur l’activité des clients, telles que les affichages, les commandes, le nombre d’appels effectués et les recettes. Les mesures représentent la base des rapports et vous aident à visualiser et comprendre les relations entre les données.

La Dimension de mesures vous permet de regrouper les mesures selon un niveau spécifique. Il vous permet également de regrouper les mesures selon un niveau spécifique.

## Création de mesures {#section-60a413899d1b4707965e06fb5ef7fc4e}

Pour créer une mesure, procédez comme suit :

1. Cliquez sur **Outil** > **Éditeur de mesures**.

1. Dans l’éditeur de mesures, saisissez le nouveau nom et la nouvelle formule de mesure. ![](assets/dwb_impl_metrics1.png)

1. Enregistrez-la dans le dossier Mesures . ![](assets/dwb_impl_metrics2.png)

## Création et modification de mesures dérivées {#section-ebdcd3ec652f485e90e001d694eab6d0}

Utilisez un éditeur de mesures pour définir une nouvelle mesure par nom, formule et format, qui est enregistrée dans le dossier [!DNL User\profile_name\Metrics] en vue d’une utilisation ultérieure.

1. Ouvrez un nouvel éditeur de mesures à l’aide de l’option de menu **Admin > Profil** ou en cliquant avec le bouton droit sur la colonne Utilisateur du dossier dans lequel vous souhaitez créer la mesure, puis en cliquant sur **Créer > Nouvelle mesure**. Un éditeur de mesures s’affiche.

1. Dans le paramètre *Name* , saisissez le nom de la nouvelle mesure.

   >[!NOTE]
   >
   >Notez que les espaces ( ) sont autorisés, contrairement aux traits de soulignement (_). En outre, vous ne pouvez pas utiliser les symboles suivants : + - * /

   ![](assets/dwb_impl_metrics3.png)

1. Dans le paramètre *Formule*, saisissez une expression pour la nouvelle mesure.

   >[!NOTE]
   Les filtres doivent être définis entre crochets [ ] dans l’expression . Pour obtenir des règles de syntaxe d’expression de mesure supplémentaires, voir [Syntaxe des expressions de mesure.](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

   Ce tableau fournit des exemples d’expressions pour les mesures étendues. ![](assets/dwb_impl_metrics4.png)

   >[!NOTE]
   Lorsqu’une expression appropriée est saisie, la ligne d’aperçu affiche la valeur de la nouvelle mesure. En cas d’erreur dans l’expression, la ligne d’aperçu affiche un message d’erreur.

1. Cliquez avec le bouton droit et sélectionnez **Enregistrer**. Lorsque vous enregistrez la mesure, un fichier représentant la nouvelle mesure est créé sur votre ordinateur dans le dossier DWB *Répertoire d’installation \User\profile name\Metrics*.

## Modification de mesures dérivées existantes {#section-4b5b7baf885b45cc8b358d1bd774e925}

1. Dans le Gestionnaire de profils ou le Gestionnaire de mesures, dans la colonne du nom du profil, cliquez avec le bouton droit de la souris sur la coche du fichier de mesures à modifier, puis cliquez sur **Rendre local**.
1. Cliquez avec le bouton droit de la souris sur la coche du fichier de mesure dans la colonne Utilisateur et cliquez sur **Ouvrir** dans l’Workbench.

   >[!NOTE]
   Vous pouvez également ouvrir un éditeur de mesures en cliquant avec le bouton droit de la souris sur une zone liée aux mesures dans une visualisation pour afficher le menu des mesures.

1. Dans l’ **éditeur de mesures**, modifiez et enregistrez la définition de mesure selon les besoins à l’aide des étapes 2 à 4 de la section *Création de mesures dérivées*.

   Si vous souhaitez que tous les utilisateurs du profil utilisent la mesure que vous avez modifiée, vous devez la publier dans le profil de travail à l’aide du Gestionnaire de profils.

Reportez-vous à la documentation pour obtenir de l’aide :

[Syntaxe des expressions de mesure](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

[Création et modification de mesures dérivées](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/profile-mgr/c-drvd-mtrcs.html)
