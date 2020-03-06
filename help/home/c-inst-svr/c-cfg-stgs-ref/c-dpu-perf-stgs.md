---
description: Instructions pour régler les performances du processeur de données.
solution: Insight
title: Paramètres de performances DPU
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Paramètres de performances DPU{#dpu-performance-settings}

Instructions pour régler les performances du processeur de données.

Renseignez les paramètres suivants dans le fichier * [!DNL Insight Server] installation directory*\Components\DPU.cfg.

| Paramètre | Description |
|---|---|
| Nombre de lots d&#39;exécution | Il s’agit d’un paramètre de réglage. La valeur par défaut est 65536. Vous pouvez spécifier arbitrairement de petits nombres de lots d’exécution. Veuillez contacter Adobe avant d’apporter des modifications à cette valeur. |
| Lots d’exécution | Il s’agit d’un paramètre de réglage. La valeur par défaut est 128. Veuillez contacter Adobe avant d’apporter des modifications à cette valeur. |
| Heure d’exécution | Il s’agit d’un paramètre de réglage. La valeur par défaut est 0,100. Veuillez contacter Adobe avant d’apporter des modifications à cette valeur. |
| Saut de champ en cas d&#39;erreur | Ce paramètre peut être défini sur true ou false. Si ce paramètre est défini sur true, [!DNL Insight Server] crée un fichier nommé [!DNL Field Dump number.txt] dans son répertoire Trace chaque fois que des erreurs du moteur d’exécution se produisent. Le [!DNL Field Dump] &lt; [!DNL number]> [!DNL .txt] est utile pour le dépannage. |
| Chemin du profil | Emplacement dans lequel stocker les fichiers pour tous les profils. L’emplacement par défaut est Profils\. |
| Limite de mémoire de requête | Quantité de mémoire (en octets) qui [!DNL Insight Server] se réserve pour stocker les résultats de la requête. La valeur par défaut est 100000000 (100 Mo). Si davantage d’espace est nécessaire pour les résultats de la requête (par exemple, pour permettre plus d’utilisateurs simultanés), le paramètre peut être augmenté, mais vous devez continuer à vérifier la charge de la [!DNL Insight Server’s] mémoire. |
| Chemin d’accès à l’état | Emplacement des fichiers d’état système. L’emplacement par défaut est Etat\. |
| Threads | Paramètre de réglage des performances pour [!DNL Insight Server] les machines avec plusieurs processeurs. En général, pour tout système n-core, cette valeur doit être définie sur n. La valeur par défaut est 1. |
| Chemin d’accès utilisateur | Emplacement des fichiers des utilisateurs autorisés. L’emplacement par défaut est Utilisateurs\. |

