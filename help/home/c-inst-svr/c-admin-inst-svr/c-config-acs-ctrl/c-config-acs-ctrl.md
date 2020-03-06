---
description: Le fichier de configuration du contrôle d’accès, Access Control.cfg, définit les groupes de contrôle d’accès par lesquels Insight Server accorde des autorisations aux fichiers en fonction des attributs (OU, CN, etc.) du certificat de la connexion entrante.
solution: Insight
title: Configuration du contrôle d'accès
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration du contrôle d&#39;accès{#configuring-access-control}

Le fichier de configuration du contrôle d’accès, Access Control.cfg, définit les groupes de contrôle d’accès par lesquels Insight Server accorde des autorisations aux fichiers en fonction des attributs (OU, CN, etc.) du certificat de la connexion entrante.

**Fréquence recommandée :** Au besoin

[!DNL Insight Server] fournit des groupes de contrôle d&#39;accès configurables pour gérer la sécurité des connexions à [!DNL Insight Server]. Les groupes de contrôle d&#39;accès identifient les utilisateurs autorisés à exercer des fonctions administratives par le biais [!DNL Insight].

Si vous devez fournir l&#39;accès à de nouveaux utilisateurs ou à de nouveaux ordinateurs, comme lors de l&#39;ajout d&#39;une machine à une [!DNL Insight Server] grappe, il vous suffit de modifier le fichier de configuration du contrôle d&#39;accès.
