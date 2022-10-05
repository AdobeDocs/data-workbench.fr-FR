---
description: Instructions pour optimiser les performances du DPU.
title: Paramètres des performances DPU
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
exl-id: 738c3a76-f8b4-4d84-86ee-ce9b99f50dae
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 7%

---

# Paramètres des performances DPU{#dpu-performance-settings}

{{eol}}

Instructions pour optimiser les performances du DPU.

Renseignez les paramètres suivants dans le * [!DNL Insight Server] répertoire d’installation*\Components\fichier DPU.cfg.

| Paramètre | Description |
|---|---|
| Nombre de lots d’exécution | Il s’agit d’un paramètre de réglage. La valeur par défaut est 65536. Vous pouvez spécifier des nombres de lots d’exécution arbitrairement petits. Veuillez contacter Adobe avant d’apporter des modifications à cette valeur. |
| Lots d’exécution | Il s’agit d’un paramètre de réglage. La valeur par défaut est 128. Veuillez contacter Adobe avant d’apporter des modifications à cette valeur. |
| Heure d’exécution | Il s’agit d’un paramètre de réglage. La valeur par défaut est 0,100. Contactez l’Adobe avant d’apporter des modifications à cette valeur. |
| Saut de champ en cas d’erreur | Ce paramètre peut être défini sur true ou false. Si elle est définie sur true, [!DNL Insight Server] crée un fichier nommé [!DNL Field Dump number.txt] dans son répertoire Trace chaque fois que des erreurs du moteur d’exécution se produisent. Le [!DNL Field Dump] &lt; [!DNL number]> [!DNL .txt] est utile pour le dépannage. |
| Chemin du profil | Emplacement dans lequel stocker les fichiers pour tous les profils. L’emplacement par défaut est Profils\. |
| Limite de mémoire de requête | Quantité de mémoire (en octets) qui [!DNL Insight Server] réserve pour stocker les résultats des requêtes. La valeur par défaut est 100000000 (100 Mo). Si davantage d’espace est nécessaire pour les résultats de la requête (par exemple, pour permettre plus d’utilisateurs simultanés), le paramètre peut être augmenté, mais vous devez continuer à vérifier la variable [!DNL Insight Server’s] charge mémoire. |
| Chemin de l’état | Emplacement des fichiers d’état système. L’emplacement par défaut est State\. |
| Threads | Un paramètre d’optimisation des performances pour [!DNL Insight Server] machines avec plusieurs processeurs. En règle générale, pour tout système n-core, cette valeur doit être définie sur n. La valeur par défaut est 1. |
| Chemin d’accès utilisateur | Emplacement des fichiers d’utilisateurs autorisés. L’emplacement par défaut est Utilisateurs\. |
