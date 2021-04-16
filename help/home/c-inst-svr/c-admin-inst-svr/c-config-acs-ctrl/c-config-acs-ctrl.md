---
description: Le fichier de configuration de Contrôle d'accès, Contrôle d'accès.cfg, définit les groupes de contrôles d'accès par lesquels Insight Server accorde des autorisations aux fichiers en fonction des attributs (OU, CN, etc.) du certificat de la connexion entrante.
title: Configuration du contrôle d’accès
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# Configuration du contrôle d’accès{#configuring-access-control}

Le fichier de configuration de Contrôle d&#39;accès, Contrôle d&#39;accès.cfg, définit les groupes de contrôles d&#39;accès par lesquels Insight Server accorde des autorisations aux fichiers en fonction des attributs (OU, CN, etc.) du certificat de la connexion entrante.

**Fréquence recommandée :** si nécessaire

[!DNL Insight Server] fournit des groupes de contrôles d&#39;accès configurables pour gérer la sécurité des connexions à  [!DNL Insight Server]. Les groupes de contrôles d&#39;accès identifient les utilisateurs autorisés à exécuter des fonctions administratives par [!DNL Insight].

Si vous devez fournir l&#39;accès à de nouveaux utilisateurs ou à de nouveaux ordinateurs, par exemple lors de l&#39;ajout d&#39;une machine à une grappe [!DNL Insight Server], il vous suffit de modifier le fichier de configuration du Contrôle d&#39;accès.
