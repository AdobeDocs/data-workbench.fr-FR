---
description: Cinq groupes de contrôles d'accès précréés sont disponibles, mais vous pouvez créer et gérer des groupes supplémentaires si nécessaire.
solution: Analytics
title: Compréhension des groupes de contrôle d’accès
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---


# Compréhension des groupes de contrôle d’accès{#understanding-access-control-groups}

Cinq groupes de contrôles d&#39;accès précréés sont disponibles, mais vous pouvez créer et gérer des groupes supplémentaires si nécessaire.

Vous pouvez définir les membres de chaque groupe de contrôles d&#39;accès, ainsi que les répertoires auxquels chaque groupe est accessible en lecture seule ou en lecture-écriture.

Les groupes prédéfinis sont définis comme suit :

| Groupe | Description |
|---|---|
| Administrateurs | Permet d’accéder à tous les répertoires et fichiers. L’adresse IP par défaut est 127.0.0.1 (hôte local). |
| Capteurs | Permet d’accéder uniquement aux fichiers utilisés par [!DNL Sensor] la transmission de données. |
| Utilisateurs | Permet l’accès en lecture seule aux éléments requis pour qu’un [!DNL Insight] utilisateur puisse effectuer des tâches d’analyse de base. |
| Utilisateurs Power | Permet l’accès en lecture seule aux éléments requis pour qu’un [!DNL Insight] utilisateur puisse effectuer des tâches d’analyse de base, ainsi que l’accès en lecture et en écriture au [!DNL Profiles] dossier pour la modification des profils. |
| Serveurs de cluster | Permet d’accéder à [!DNL Insight Servers] des serveurs désignés comme serveurs de cluster. |
| Serveurs de rapports | Permet d&#39;accéder aux [!DNL Report] machines qui se connectent au [!DNL Insight Server]. |

Les membres d’un groupe de contrôles d&#39;accès sont définis à l’aide de leurs adresses IP ou de leurs informations de certificat SSL.

Si un certificat SSL n’est pas disponible, une adresse IP peut être utilisée pour définir un membre du groupe. L’installation type de [!DNL Insight] comprend un certificat SSL, tandis que l’utilisation de certificats [!DNL Sensor(s)] est facultative. Par exemple, [!DNL Insight Server]les serveurs de cluster sont définis à l’aide d’adresses IP plutôt que de certificats SSL.

Les codes suivants peuvent être utilisés pour définir les membres du groupe :

| Code de types d’accès | Définition |
|---|---|
| O | Organisation |
| CN | Nom commun |
| L | Localité |
| ST | Etat ou province |
| C | Pays |
| OU | Unité organisationnelle |
| Courriel | Adresse électronique |

