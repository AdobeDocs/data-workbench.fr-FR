---
description: Lors du retraitement, le serveur de l’outil de données reconstruit votre jeu de données, comme vous l’avez indiqué dans les fichiers de configuration du traitement des journaux et du jeu de données de transformation.
solution: Analytics
title: Compréhension du retraitement et de la retransformation
topic: Data workbench
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Compréhension du retraitement et de la retransformation{#understanding-reprocessing-and-retransformation}

Lors du retraitement, le serveur de l’outil de données reconstruit votre jeu de données, comme vous l’avez indiqué dans les fichiers de configuration du traitement des journaux et du jeu de données de transformation.

Pour ce faire, le serveur d’outils de données (InsightServer64.exe) doit terminer la phase de traitement du journal et la phase de transformation de la construction du jeu de données. Lorsque le traitement du journal est terminé, il déclenche automatiquement la transformation, mais la transformation peut également se produire indépendamment du traitement du journal.

Pendant la phase de traitement du journal, les utilisateurs des outils de données n’ont pas accès aux données du jeu de données. Au cours de la phase de transformation, les utilisateurs des outils de données ont accès à des données à jour, mais les données sont échantillonnées au lieu d’être complètes. L’analyse des données peut se poursuivre pendant la transformation, mais les requêtes ne se terminent que aussi rapidement que la transformation se produit.

## Retraitement {#section-92f1e46bf1534b3dba39e9493190b8ab}

Chaque fois que vous effectuez l’une des tâches suivantes, le traitement du journal et, par conséquent, la transformation, se produit automatiquement pour reconstruire votre jeu de données, comme vous l’avez spécifié dans les fichiers de configuration du jeu de données :

* Ajoutez une nouvelle source de données.
* Ajoutez un nouveau serveur de outils de données à votre grappe dans le [!DNL Profile.cfg] fichier.
* Modifiez le [!DNL Cluster.cfg] fichier.
* Modifiez le [!DNL Log Processing.cfg] fichier ou un [!DNL Log Processing Dataset Include] fichier, y compris, mais sans s’y limiter, les éléments suivants :

   * Ajouter un nouveau paramètre
   * Modification d’une transformation
   * Modification des paramètres Heure de début ou Heure de fin

* Mettez à niveau votre [!DNL Insight Server.exe] fichier.

Vous pouvez également lancer le retraitement à tout moment en saisissant n’importe quel caractère ou combinaison de caractères dans le paramètre Retraiter du [!DNL Log Processing.cfg] fichier et en enregistrant le fichier.

>[!NOTE]
>
>Pour que le retraitement se produise, le paramètre Pause du [!DNL Log Processing Mode.cfg] fichier doit être défini sur false. La valeur par défaut de ce paramètre est false. Il est donc possible que la modification du paramètre ne soit pas obligatoire. Pour plus d’informations sur [!DNL Log Processing Mode.cfg]d’autres fichiers [de configuration, voir Fichiers](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md)de configurationsupplémentaires.

## Retransformation {#section-02446744549940ada8eba0573ec5575f}

Chaque fois que vous modifiez des informations contenues dans le [!DNL Transformation.cfg] fichier ou dans un [!DNL Transformation Dataset Include] fichier, par exemple pour modifier une transformation ou définir une nouvelle dimension, la transformation se produit automatiquement.

Chaque fois que vous modifiez des fichiers de recherche référencés dans le [!DNL Transformation.cfg] fichier ou dans un [!DNL Transformation Dataset Include] fichier (y compris des fichiers de recherche pour [!DNL Categorize], [!DNL FlatFileLookup]et [!DNL ODBCLookup] des transformations), vous devez lancer la transformation en saisissant un caractère ou une combinaison de caractères dans le paramètre Retraitement du [!DNL Transformation.cfg] fichier et en enregistrant le fichier.
