---
description: Instructions pour régler les performances de l'unité de traitement des données.
title: Paramètres des performances DPU
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
exl-id: 738c3a76-f8b4-4d84-86ee-ce9b99f50dae
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 6%

---

# Paramètres des performances DPU{#dpu-performance-settings}

Instructions pour régler les performances de l&#39;unité de traitement des données.

Renseignez les paramètres suivants dans le fichier * [!DNL Insight Server] répertoire d’installation*\Components\DPU.cfg.

| Paramètre | Description |
|---|---|
| Nombre de lots d&#39;exécution | Il s’agit d’un paramètre de réglage. La valeur par défaut est 65536. Vous pouvez spécifier arbitrairement de petits nombres de lots d’exécution. Veuillez contacter l&#39;Adobe avant d&#39;apporter des modifications à cette valeur. |
| Lots d&#39;exécution | Il s’agit d’un paramètre de réglage. La valeur par défaut est 128. Veuillez contacter l&#39;Adobe avant d&#39;apporter des modifications à cette valeur. |
| Heure d&#39;exécution | Il s’agit d’un paramètre de réglage. La valeur par défaut est 0,100. Contactez l&#39;Adobe avant d&#39;apporter des modifications à cette valeur. |
| Vider le champ en cas d&#39;erreur | Ce paramètre peut être défini sur true ou false. Si ce paramètre est défini sur true, [!DNL Insight Server] crée un fichier nommé [!DNL Field Dump number.txt] dans son répertoire Trace chaque fois que des erreurs du moteur d’exécution se produisent. Le [!DNL Field Dump] &lt; [!DNL number] [!DNL .txt] est utile pour le dépannage. |
| Chemin d’accès au profil | Emplacement dans lequel stocker les fichiers pour tous les profils. L’emplacement par défaut est Profils\. |
| Limite de mémoire de requête | Quantité de mémoire (en octets) que [!DNL Insight Server] réserve pour stocker les résultats de la requête. La valeur par défaut est 100000000 (100 Mo). Si vous avez besoin de plus d’espace pour les résultats de la requête (par exemple, pour permettre plus d’utilisateurs simultanés), le paramètre peut être augmenté, mais vous devez continuer à vérifier la charge de mémoire [!DNL Insight Server’s]. |
| Chemin d&#39;état | Emplacement des fichiers d&#39;état système. L’emplacement par défaut est Etat\. |
| Threads | Paramètre de réglage des performances pour les machines [!DNL Insight Server] dotées de plusieurs processeurs. En général, pour tout système n-core, cette valeur doit être définie sur n. La valeur par défaut est 1. |
| Chemin d’accès utilisateur | Emplacement des fichiers des utilisateurs autorisés. L’emplacement par défaut est Utilisateurs\. |
