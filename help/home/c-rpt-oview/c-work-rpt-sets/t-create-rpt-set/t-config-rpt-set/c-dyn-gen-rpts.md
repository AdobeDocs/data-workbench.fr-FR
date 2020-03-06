---
description: Vous pouvez générer des rapports de manière dynamique pour les éléments de dimension que vous spécifiez dans un fichier de recherche ou pour un nombre particulier d’éléments de dimension, par exemple pour les utilisateurs dont le nombre de commandes est le plus élevé.
solution: Analytics
title: Génération Dynamique De Rapports
topic: Data workbench
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Génération Dynamique De Rapports{#dynamically-generating-reports}

Vous pouvez générer des rapports de manière dynamique pour les éléments de dimension que vous spécifiez dans un fichier de recherche ou pour un nombre particulier d’éléments de dimension, par exemple pour les utilisateurs dont le nombre de commandes est le plus élevé.

>[!NOTE]
>
>Adobe décourage la création de jeux de rapports dynamiques pour la génération quotidienne (ou plus fréquente) de rapports. La génération de rapports dynamique peut être gourmande en ressources si vous configurez des rapports avec des requêtes volumineuses ou complexes.

* [Rapports d’éléments de dimension de fichier de recherche](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [Principaux rapports sur les éléments de dimension](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## Rapports d’éléments de dimension de fichier de recherche {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

Pour configurer un jeu de rapports de manière à générer et (éventuellement) distribuer des rapports de manière dynamique pour les éléments d’une dimension spécifiés dans un fichier de recherche, spécifiez les paramètres suivants dans le [!DNL Report.cfg] fichier :

* [!DNL Dimension Name]
* [!DNL Lookup File]

Pour des descriptions détaillées de ces paramètres, voir Paramètres [](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.

**Pour créer un jeu de rapports dynamique à l’aide d’un fichier de recherche**

1. Créez un fichier de recherche à deux colonnes pour une dimension donnée. Ce fichier doit contenir deux colonnes délimitées par des tabulations, sans ligne d’en-tête.

   * La colonne 1 doit contenir une liste d’éléments de dimension.
   * La colonne 2 doit contenir les adresses électroniques des destinataires du rapport. Un rapport pour un élément donné de la colonne 1 est envoyé à l’adresse(s) électronique(s) de la même ligne dans la colonne 2. Vous pouvez entrer plusieurs adresses électroniques en les séparant par des virgules (sans espace).

      >[!NOTE]
      >
      >
      >    
      >    
      >    * Si les rapports ne doivent pas être envoyés par courriel, la colonne 2 peut être vide, mais elle doit exister.
      >    * Ce fichier peut contenir des lignes vierges.




1. Facultatif. Pour activer l’envoi par courriel des rapports, vous devez effectuer les opérations suivantes dans la [!DNL Mail Report] section du [!DNL Report.cfg] fichier pour ce jeu de rapports particulier :

   * Dans le paramètre Serveur SMTP, indiquez le serveur SMTP approprié à utiliser pour distribuer les rapports par courrier électronique.
   * Dans le paramètre Destinataires, indiquez au moins une adresse électronique pour permettre la distribution des rapports par courrier électronique. Les rapports ne sont pas envoyés par courrier électronique à l’adresse répertoriée. Vous définissez ce paramètre uniquement pour autoriser l’envoi des rapports par courrier électronique. Il peut s’agir d’une adresse erronée, mais elle doit être dans un format autorisé (par exemple, [!DNL jsmith@company.com]).

1. Enregistrez le fichier de recherche dans le dossier du jeu de rapports.
1. Ouvrez le [!DNL Report.cfg] fichier du jeu de rapports.
1. Dans le paramètre Nom de dimension, saisissez le nom de la dimension pour laquelle vous souhaitez générer dynamiquement un rapport.
1. Dans le paramètre Fichier de recherche, saisissez l’emplacement et le nom du fichier de recherche contenant les éléments de dimension que vous souhaitez voir figurer dans le rapport et les adresses électroniques des destinataires.
1. Répétez ces étapes pour d’autres jeux de rapports.

>[!NOTE]
>
>Les rapports dynamiques ne sont pas envoyés aux destinataires par courrier électronique tant que le jeu de rapports complet n’est pas terminé.

## Principaux rapports sur les éléments de dimension {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

Pour configurer un jeu de rapports afin qu’il génère des rapports de manière dynamique pour les principaux éléments de dimension, en comptant par la mesure spécifiée, spécifiez les paramètres suivants dans le [!DNL Report.cfg] fichier :

* Nom de la dimension
* Mesure N supérieure
* N valeur supérieure
* (Facultatif) Précharger le filtre de requête

Pour des descriptions détaillées de ces paramètres, voir Paramètres [](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.

**Pour créer un jeu de rapports dynamique pour les principaux éléments**

1. Ouvrez le [!DNL Report.cfg] fichier du jeu de rapports.
1. Dans le paramètre Nom de dimension, saisissez le nom de la dimension pour laquelle vous souhaitez générer dynamiquement un jeu de rapports.
1. Dans le paramètre Mesure N supérieure, saisissez le nom de la mesure par laquelle vous souhaitez trier la dimension.
1. Dans le paramètre Valeur N supérieure, entrez le nombre d’éléments de dimension que vous souhaitez dans le jeu de rapports.
1. (Facultatif) Dans le paramètre Filtre de requête de préchargement, saisissez le nom du filtre souhaité.
1. Répétez ces étapes pour d’autres jeux de rapports.
1. Pour plus d’informations sur l’utilisation d’une visualisation dynamique des titres avec votre rapport, consultez le Guide *de l’utilisateur des outils de* données.

