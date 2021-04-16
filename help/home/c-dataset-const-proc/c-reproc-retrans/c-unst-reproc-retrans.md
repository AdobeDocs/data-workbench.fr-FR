---
description: Au cours du retraitement, le serveur de l’outil de données reconstruit votre jeu de données comme vous l’avez indiqué dans les fichiers de traitement des journaux et de configuration des jeux de données de transformation.
title: Comprendre le retraitement et la retransformation
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# Comprendre le retraitement et la retransformation{#understanding-reprocessing-and-retransformation}

Au cours du retraitement, le serveur de l’outil de données reconstruit votre jeu de données comme vous l’avez indiqué dans les fichiers de traitement des journaux et de configuration des jeux de données de transformation.

Pour ce faire, le serveur de l&#39;outil de données (InsightServer64.exe) doit terminer à la fois la phase de traitement du journal et la phase de transformation de la construction du jeu de données. Lorsque le traitement du journal est terminé, il déclenche automatiquement la transformation, mais cette dernière peut également se produire indépendamment du traitement du journal.

Au cours de la phase de traitement du journal, les utilisateurs des outils de données n’ont pas accès aux données du jeu de données. Au cours de la phase de transformation, les utilisateurs des outils de données ont accès à des données à jour, mais les données sont échantillonnées au lieu d’être complètes. L&#39;analyse des données peut se poursuivre pendant la transformation, mais les requêtes ne se termineront que aussi vite que la transformation se produira.

## Retraitement {#section-92f1e46bf1534b3dba39e9493190b8ab}

Chaque fois que vous effectuez l&#39;une des tâches suivantes, le traitement des journaux et, par conséquent, la transformation, se produit automatiquement pour reconstruire votre jeu de données comme vous l&#39;avez spécifié dans les fichiers de configuration du jeu de données :

* Ajoutez une nouvelle source de données.
* Ajoutez un nouveau serveur d’outils de données sur votre grappe dans le fichier [!DNL Profile.cfg].
* Modifiez le fichier [!DNL Cluster.cfg].
* Modifiez le fichier [!DNL Log Processing.cfg] ou un fichier [!DNL Log Processing Dataset Include], y compris, mais sans s&#39;y limiter, les éléments suivants :

   * Ajouter un nouveau paramètre
   * Modification d’une transformation
   * Modification des paramètres Heure de Début ou Heure de fin

* Mettez à niveau votre fichier [!DNL Insight Server.exe].

Vous pouvez également lancer le retraitement à tout moment en saisissant n’importe quel caractère ou combinaison de caractères dans le paramètre Retraiter du fichier [!DNL Log Processing.cfg] et en enregistrant le fichier.

>[!NOTE]
>
>Pour que le retraitement se produise, le paramètre Pause du fichier [!DNL Log Processing Mode.cfg] doit être défini sur false. La valeur par défaut de ce paramètre est false. Il n’est donc pas nécessaire de modifier ce paramètre. Pour plus d&#39;informations sur [!DNL Log Processing Mode.cfg], voir [Autres fichiers de configuration](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## Retransformation {#section-02446744549940ada8eba0573ec5575f}

Chaque fois que vous modifiez des informations dans le fichier [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include], par exemple en modifiant une transformation ou en définissant une nouvelle dimension, la transformation se produit automatiquement.

Chaque fois que vous modifiez les fichiers de recherche référencés dans le fichier [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include] (y compris les fichiers de recherche pour les transformations [!DNL Categorize], [!DNL FlatFileLookup] et [!DNL ODBCLookup]), vous devez lancer la transformation en saisissant tout caractère ou combinaison de caractères dans le paramètre de retraitement du fichier [!DNL Transformation.cfg] et en enregistrant le fichier.
