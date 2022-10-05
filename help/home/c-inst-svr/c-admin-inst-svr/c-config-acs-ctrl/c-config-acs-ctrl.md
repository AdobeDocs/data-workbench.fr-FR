---
description: Le fichier de configuration du contrôle d’accès, Access Control.cfg, définit les groupes de contrôle d’accès par lesquels Insight Server accorde des autorisations aux fichiers en fonction des attributs (OU, CN, etc.) du certificat de la connexion entrante.
title: Configuration du contrôle d’accès
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# Configuration du contrôle d’accès{#configuring-access-control}

{{eol}}

Le fichier de configuration du contrôle d’accès, Access Control.cfg, définit les groupes de contrôle d’accès par lesquels Insight Server accorde des autorisations aux fichiers en fonction des attributs (OU, CN, etc.) du certificat de la connexion entrante.

**Fréquence recommandée :** Selon les besoins

[!DNL Insight Server] fournit des groupes de contrôle d’accès configurables pour gérer la sécurité des connexions à [!DNL Insight Server]. Les groupes de contrôle d’accès identifient les utilisateurs autorisés à exécuter des fonctions administratives par le biais de [!DNL Insight].

Si vous devez donner accès à de nouveaux utilisateurs ou à de nouvelles machines, par exemple lors de l’ajout d’une machine à un [!DNL Insight Server] , il vous suffit de modifier le fichier de configuration du contrôle d’accès .
