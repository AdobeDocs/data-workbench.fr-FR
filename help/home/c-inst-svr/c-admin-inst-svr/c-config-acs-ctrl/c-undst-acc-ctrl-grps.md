---
description: Cinq groupes de contrôle d’accès prédéfinis sont disponibles, mais vous pouvez créer et gérer d’autres groupes selon vos besoins.
solution: Insight
title: Présentation des groupes de contrôle d'accès
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Présentation des groupes de contrôle d&#39;accès{#understanding-access-control-groups}

Cinq groupes de contrôle d’accès prédéfinis sont disponibles, mais vous pouvez créer et gérer d’autres groupes selon vos besoins.

Vous pouvez définir les membres de chaque groupe de contrôle d’accès, ainsi que les répertoires auxquels chaque groupe a accès en lecture seule ou en lecture-écriture.

Les groupes prédéfinis sont définis comme suit :

| Groupe | Description |
|---|---|
| Administrateurs | Permet d’accéder à tous les répertoires et fichiers. L’adresse IP par défaut est 127.0.0.1 (hôte local). |
| Capteurs | Permet d’accéder uniquement aux fichiers utilisés par [!DNL Sensor] la transmission de données. |
| Utilisateurs | Permet un accès en lecture seule aux éléments requis pour qu’un [!DNL Insight] utilisateur puisse effectuer des tâches d’analyse de base. |
| Utilisateurs puissants | Permet l’accès en lecture seule aux éléments requis pour qu’un [!DNL Insight] utilisateur effectue des tâches d’analyse de base, ainsi que l’accès en lecture et en écriture au [!DNL Profiles] dossier pour la modification des profils. |
| Serveurs de cluster | Permet d’accéder à [!DNL Insight Servers] des serveurs désignés comme serveurs de cluster. |
| Serveurs de rapports | Permet d&#39;accéder aux [!DNL Report] ordinateurs qui se connectent au [!DNL Insight Server]. |

Les membres d’un groupe de contrôle d’accès sont définis à l’aide de leurs adresses IP ou des informations de certificat SSL.

Si aucun certificat SSL n’est disponible, une adresse IP peut être utilisée pour définir un membre du groupe. L’installation type de [!DNL Insight] inclut un certificat SSL, tandis que l’utilisation de certificats [!DNL Sensor(s)] est facultative. Par exemple, [!DNL Insight Server]les serveurs de cluster sont définis à l’aide d’adresses IP plutôt que de certificats SSL.

Les codes suivants peuvent être utilisés pour définir les membres du groupe :

| Code Types d’accès | Définition |
|---|---|
| O | Organisation |
| CN | Nom commun |
| L | Localité |
| ST | Etat ou province |
| C | Pays |
| OU | Groupe de l&#39;organisation |
| Courriel | Adresse électronique |

