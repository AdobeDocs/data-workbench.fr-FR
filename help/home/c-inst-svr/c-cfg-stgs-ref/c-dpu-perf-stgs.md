---
description: Instructions pour optimiser les performances du DPU.
title: Paramètres des performances DPU
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
exl-id: 738c3a76-f8b4-4d84-86ee-ce9b99f50dae
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 6%

---

# Paramètres des performances DPU{#dpu-performance-settings}

Instructions pour optimiser les performances du DPU.

Renseignez les paramètres suivants dans le fichier * [!DNL Insight Server] répertoire d’installation*\Components\DPU.cfg .

| Paramètre | Description |
|---|---|
| Nombre de lots d’exécution | Il s’agit d’un paramètre de réglage. La valeur par défaut est 65536. Vous pouvez spécifier des nombres de lots d’exécution arbitrairement petits. Veuillez contacter Adobe avant d’apporter des modifications à cette valeur. |
| Lots d’exécution | Il s’agit d’un paramètre de réglage. La valeur par défaut est 128. Veuillez contacter Adobe avant d’apporter des modifications à cette valeur. |
| Heure d’exécution | Il s’agit d’un paramètre de réglage. La valeur par défaut est 0,100. Contactez l’Adobe avant d’apporter des modifications à cette valeur. |
| Saut de champ en cas d’erreur | Ce paramètre peut être défini sur true ou false. Si la valeur est définie sur true, [!DNL Insight Server] crée un fichier nommé [!DNL Field Dump number.txt] dans son répertoire Trace chaque fois que des erreurs se produisent dans le moteur d’exécution. [!DNL Field Dump] &lt; [!DNL number] [!DNL .txt] est utile pour la résolution des problèmes. |
| Chemin du profil | Emplacement dans lequel stocker les fichiers pour tous les profils. L’emplacement par défaut est Profils\. |
| Limite de mémoire de requête | Quantité de mémoire (en octets) que [!DNL Insight Server] réserve pour stocker les résultats de la requête. La valeur par défaut est 100000000 (100 Mo). Si davantage d’espace est nécessaire pour les résultats de la requête (par exemple, pour permettre plus d’utilisateurs simultanés), le paramètre peut être augmenté, mais vous devez continuer à vérifier la charge de mémoire [!DNL Insight Server’s]. |
| Chemin de l’état | Emplacement des fichiers d’état système. L’emplacement par défaut est State\. |
| Threads | Paramètre d’optimisation des performances pour les machines [!DNL Insight Server] avec plusieurs processeurs. En règle générale, pour tout système n-core, cette valeur doit être définie sur n. La valeur par défaut est 1. |
| Chemin d’accès utilisateur | Emplacement des fichiers d’utilisateurs autorisés. L’emplacement par défaut est Utilisateurs\. |
