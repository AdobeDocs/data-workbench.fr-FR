---
description: Vous pouvez générer dynamiquement des rapports pour les éléments de dimension que vous indiquez dans un fichier de recherche ou pour un nombre spécifique d’éléments de dimension, par exemple pour les utilisateurs qui ont les 10 valeurs de commande les plus élevées.
title: Génération dynamique de rapports
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
exl-id: c14d93cd-212d-44a1-aff9-652e5c4fbda0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 1%

---

# Génération dynamique de rapports{#dynamically-generating-reports}

Vous pouvez générer dynamiquement des rapports pour les éléments de dimension que vous indiquez dans un fichier de recherche ou pour un nombre spécifique d’éléments de dimension, par exemple pour les utilisateurs qui ont les 10 valeurs de commande les plus élevées.

>[!NOTE]
>
>L’Adobe décourage la création de jeux de rapports dynamiques pour la génération quotidienne (ou plus fréquente) de rapports. La génération de rapports dynamique peut nécessiter de nombreuses ressources si vous configurez des rapports avec des requêtes volumineuses ou complexes.

* [Rapports d’éléments de Dimension de fichiers de recherche](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [Rapports sur les éléments de Dimension principaux](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## Rapports d’éléments de Dimension de fichier de recherche {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

Pour configurer un jeu de rapports afin de générer dynamiquement et (éventuellement) distribuer des rapports pour les éléments d’une dimension spécifiés dans un fichier de recherche, spécifiez les paramètres suivants dans le fichier [!DNL Report.cfg] :

* [!DNL Dimension Name]
* [!DNL Lookup File]

Pour obtenir des descriptions détaillées de ces paramètres, voir [Paramètres Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**Pour créer un jeu de rapports dynamique à l’aide d’un fichier de recherche**

1. Créez un fichier de recherche à deux colonnes pour une dimension donnée. Ce fichier doit contenir deux colonnes délimitées par des tabulations, sans ligne d’en-tête.

   * La colonne 1 doit contenir une liste d’éléments de dimension.
   * La colonne 2 doit contenir les adresses email des destinataires du rapport. Un rapport pour un élément donné de la colonne 1 est envoyé à la ou aux adresses email de la même ligne de la colonne 2. Vous pouvez saisir plusieurs adresses électroniques en les séparant par des virgules (sans espaces).

      >[!NOTE]
      >
      >
      >    
      >    
      >    * Si les rapports ne doivent pas être envoyés par courriel, la colonne 2 peut être vide, mais doit exister.
      >    * Ce fichier peut contenir des lignes vierges.




1. Facultatif. Pour activer l’envoi de rapports par courrier électronique, vous devez effectuer les opérations suivantes dans la section [!DNL Mail Report] du fichier [!DNL Report.cfg] correspondant à ce jeu de rapports spécifique :

   * Dans le paramètre Serveur SMTP , indiquez le serveur SMTP approprié à utiliser pour distribuer les rapports par email.
   * Dans le paramètre Destinataires , indiquez au moins une adresse email pour permettre la distribution des rapports par email. Les rapports ne sont pas envoyés par courrier électronique à l’adresse répertoriée. Vous définissez ce paramètre uniquement pour autoriser l’envoi des rapports par courrier électronique. Il peut s’agir d’une adresse erronée, mais elle doit être dans un format autorisé (par exemple, [!DNL jsmith@company.com]).

1. Enregistrez le fichier de recherche dans le dossier du jeu de rapports.
1. Ouvrez le fichier [!DNL Report.cfg] pour le jeu de rapports.
1. Dans le paramètre Nom de la Dimension , saisissez le nom de la dimension pour laquelle vous souhaitez générer dynamiquement un rapport.
1. Dans le paramètre Fichier de recherche , saisissez l’emplacement et le nom du fichier de recherche contenant les éléments de dimension souhaités dans le rapport et les adresses électroniques des destinataires.
1. Répétez ces étapes pour d’autres jeux de rapports.

>[!NOTE]
>
>Les rapports dynamiques ne sont pas envoyés aux destinataires par courrier électronique tant que le jeu de rapports complet n’est pas terminé.

## Rapports des éléments de Dimension supérieure {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

Pour configurer un jeu de rapports afin de générer dynamiquement des rapports pour les principaux éléments de dimension, en comptant par la mesure spécifiée, spécifiez les paramètres suivants dans le fichier [!DNL Report.cfg] :

* Nom de la dimension
* Mesure N supérieure
* Valeur N supérieure
* (Facultatif) Précharger le filtre de requête

Pour obtenir des descriptions détaillées de ces paramètres, voir [Paramètres Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**Pour créer un jeu de rapports dynamique pour les éléments principaux**

1. Ouvrez le fichier [!DNL Report.cfg] du jeu de rapports.
1. Dans le paramètre Nom de la Dimension , saisissez le nom de la dimension pour laquelle vous souhaitez générer dynamiquement un jeu de rapports.
1. Dans le paramètre Mesure N supérieure , saisissez le nom de la mesure selon laquelle vous souhaitez trier la dimension.
1. Dans le paramètre Top N Value , saisissez le nombre d’éléments de dimension souhaité dans le jeu de rapports.
1. (Facultatif) Dans le paramètre Filtre de requête de préchargement , saisissez le nom du filtre souhaité.
1. Répétez ces étapes pour d’autres jeux de rapports.
1. Pour plus d’informations sur l’utilisation d’une visualisation de titre dynamique avec votre rapport, consultez le *Guide de l’utilisateur du Data Workbench*.
