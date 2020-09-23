---
description: Le fichier de configuration de Contrôle d'accès, Contrôle d'accès.cfg, définit les groupes de contrôles d'accès par lesquels Insight Server accorde des autorisations aux fichiers en fonction des attributs (OU, CN, etc.) du certificat de la connexion entrante.
solution: Analytics
title: Configuration du contrôle d’accès
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---


# Configuration du contrôle d’accès{#configuring-access-control}

Le fichier de configuration de Contrôle d&#39;accès, Contrôle d&#39;accès.cfg, définit les groupes de contrôles d&#39;accès par lesquels Insight Server accorde des autorisations aux fichiers en fonction des attributs (OU, CN, etc.) du certificat de la connexion entrante.

**Fréquence recommandée :** Si nécessaire

[!DNL Insight Server] fournit des groupes de contrôles d&#39;accès configurables pour gérer la sécurité des connexions à [!DNL Insight Server]. Les groupes de contrôles d&#39;accès identifient les utilisateurs qui sont autorisés à exécuter des fonctions administratives par [!DNL Insight].

Si vous devez fournir l’accès à de nouveaux utilisateurs ou à de nouveaux ordinateurs, par exemple lors de l’ajout d’une machine à une [!DNL Insight Server] grappe, il vous suffit de modifier le fichier de configuration du Contrôle d&#39;accès.
