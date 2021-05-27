---
description: Cinq groupes de contrôle d’accès prédéfinis sont disponibles, mais vous pouvez créer et gérer des groupes supplémentaires, selon vos besoins.
title: Compréhension des groupes de contrôle d’accès
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
exl-id: 35353b0a-7f08-4215-8a2c-ee1e26d9f5db
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---

# Compréhension des groupes de contrôle d’accès{#understanding-access-control-groups}

Cinq groupes de contrôle d’accès prédéfinis sont disponibles, mais vous pouvez créer et gérer des groupes supplémentaires, selon vos besoins.

Vous pouvez définir les membres de chaque groupe de contrôle d’accès, ainsi que les répertoires auxquels chaque groupe a accès en lecture seule ou en lecture-écriture.

Les groupes prédéfinis sont définis comme suit :

| Groupe | Description |
|---|---|
| Administrateurs | Permet d’accéder à tous les répertoires et fichiers. L’adresse IP par défaut est 127.0.0.1 (hôte local). |
| Capteurs | Permet d’accéder uniquement aux fichiers utilisés par [!DNL Sensor] pour transmettre des données. |
| Utilisateurs | Permet un accès en lecture seule aux éléments requis pour qu’un utilisateur [!DNL Insight] effectue des tâches d’analyse de base. |
| Utilisateurs experts | Permet un accès en lecture seule aux éléments requis pour qu’un utilisateur [!DNL Insight] effectue des tâches d’analyse de base, ainsi qu’un accès en lecture et écriture au dossier [!DNL Profiles] pour la modification des profils. |
| Serveurs de grappe | Permet d’accéder à [!DNL Insight Servers] qui sont désignées comme des serveurs de cluster. |
| Serveurs de rapports | Permet d’accéder aux machines [!DNL Report] qui se connectent à [!DNL Insight Server]. |

Les membres d’une population témoin d’accès sont définis à l’aide de leurs adresses IP ou des informations de certificat SSL.

Si aucun certificat SSL n’est disponible, une adresse IP peut être utilisée pour définir un membre du groupe. L’installation type de [!DNL Insight] comprend un certificat SSL, tandis que l’utilisation de certificats pour [!DNL Sensor(s)] est facultative. Pour [!DNL Insight Server], les serveurs de cluster sont définis à l’aide d’adresses IP au lieu de certificats SSL.

Les codes suivants peuvent être utilisés pour définir les membres du groupe :

| Code des types d’accès | Définition |
|---|---|
| O | Organisation |
| CN | Nom commun |
| L | Localité |
| ST | Etat ou province |
| C  | Pays |
| OU | Unité organisationnelle |
| Courriel  | Adresse électronique |
