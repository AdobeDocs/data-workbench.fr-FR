---
description: Vous pouvez générer des rapports de manière dynamique pour les éléments de dimension que vous spécifiez dans un fichier de recherche ou pour un nombre particulier d’éléments de dimension, par exemple pour les utilisateurs dont le nombre de commandes est le plus élevé.
title: Génération dynamique de rapports
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
exl-id: c14d93cd-212d-44a1-aff9-652e5c4fbda0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 1%

---

# Génération dynamique de rapports{#dynamically-generating-reports}

Vous pouvez générer des rapports de manière dynamique pour les éléments de dimension que vous spécifiez dans un fichier de recherche ou pour un nombre particulier d’éléments de dimension, par exemple pour les utilisateurs dont le nombre de commandes est le plus élevé.

>[!NOTE]
>
>L’Adobe décourage la création de jeux de rapports dynamiques pour la génération quotidienne (ou plus fréquente) de rapports. La génération de rapports dynamique peut être gourmande en ressources si vous configurez des rapports avec des requêtes volumineuses ou complexes.

* [Rapports des éléments de la Dimension de fichiers de recherche](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [Rapports sur les principaux éléments de Dimension](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## Rapports des éléments de la Dimension de fichiers de recherche {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

Pour configurer un jeu de rapports afin qu’il génère et distribue dynamiquement (éventuellement) des rapports pour les éléments d’une dimension spécifiés dans un fichier de recherche, spécifiez les paramètres suivants dans le fichier [!DNL Report.cfg] :

* [!DNL Dimension Name]
* [!DNL Lookup File]

Pour des descriptions détaillées de ces paramètres, voir [Paramètres Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**Pour créer un jeu de rapports dynamique à l’aide d’un fichier de recherche**

1. Créez un fichier de recherche à deux colonnes pour une dimension donnée. Ce fichier doit contenir deux colonnes délimitées par des tabulations, sans rangée d’en-tête.

   * La colonne 1 doit contenir une liste d&#39;éléments de dimension.
   * La colonne 2 doit contenir les adresses électroniques des destinataires de rapports. Un rapport pour un élément donné de la colonne 1 est envoyé à l’adresse électronique de la même ligne de la colonne 2. Vous pouvez entrer plusieurs adresses électroniques en les séparant par des virgules (sans espace).

      >[!NOTE]
      >
      >
      >    
      >    
      >    * Si les rapports ne doivent pas être envoyés par courriel, la colonne 2 peut être vide mais doit exister.
      >    * Ce fichier peut contenir des lignes vides.




1. Facultatif. Pour activer l&#39;envoi par courriel des rapports, vous devez effectuer les opérations suivantes dans la section [!DNL Mail Report] du fichier [!DNL Report.cfg] pour ce jeu de rapports particulier :

   * Dans le paramètre Serveur SMTP, liste le serveur SMTP approprié à utiliser pour distribuer les rapports par courrier électronique.
   * Dans le paramètre Destinataire, liste au moins une adresse électronique pour permettre la distribution des rapports par courrier électronique. Les rapports ne sont pas envoyés par la poste à l’adresse indiquée. Vous définissez ce paramètre uniquement pour autoriser l’envoi des rapports par courriel. Il peut s’agir d’une adresse erronée, mais elle doit être au format autorisé (par exemple, [!DNL jsmith@company.com]).

1. Enregistrez le fichier de recherche dans le dossier du jeu de rapports.
1. Ouvrez le fichier [!DNL Report.cfg] pour le jeu de rapports.
1. Dans le paramètre Nom de la Dimension, tapez le nom de la dimension pour laquelle vous souhaitez générer dynamiquement un rapport.
1. Dans le paramètre Fichier de recherche, saisissez l’emplacement et le nom du fichier de recherche contenant les éléments de dimension que vous souhaitez voir figurer dans le rapport et les adresses électroniques du destinataire.
1. Répétez ces étapes pour d’autres jeux de rapports.

>[!NOTE]
>
>Les rapports dynamiques ne sont pas envoyés aux destinataires par courriel tant que le jeu de rapports complet n’est pas terminé.

## Rapports des principaux éléments de Dimension {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

Pour configurer un jeu de rapports afin de générer dynamiquement des rapports pour les principaux éléments de dimension, en les comptabilisant selon la mesure spécifiée, spécifiez les paramètres suivants dans le fichier [!DNL Report.cfg] :

* Nom de la dimension
* Mesure N supérieure
* N valeur supérieure
* (Facultatif) Filtre de Requête de préchargement

Pour des descriptions détaillées de ces paramètres, voir [Paramètres Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**Pour créer un jeu de rapports dynamique pour les principaux éléments**

1. Ouvrez le fichier [!DNL Report.cfg] du jeu de rapports.
1. Dans le paramètre Nom de la Dimension, tapez le nom de la dimension pour laquelle vous souhaitez générer dynamiquement un jeu de rapports.
1. Dans le paramètre Mesure N supérieure, tapez le nom de la mesure par laquelle vous souhaitez trier la dimension.
1. Dans le paramètre N valeur supérieure, entrez le nombre d’éléments de dimension que vous souhaitez inclure dans le jeu de rapports.
1. (Facultatif) Dans le paramètre Filtre de Requête de préchargement, entrez le nom du filtre de votre choix.
1. Répétez ces étapes pour d’autres jeux de rapports.
1. Pour plus d&#39;informations sur l&#39;utilisation d&#39;une visualisation dynamique des titres avec votre rapport, consultez le *Guide de l&#39;utilisateur Data Workbench*.
