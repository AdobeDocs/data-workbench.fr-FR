---
description: Pendant le retraitement, le serveur Data Workbench reconstruit votre jeu de données comme vous l’avez spécifié dans les fichiers de configuration du jeu de données de traitement et de transformation du journal.
title: Comprendre le retraitement et la retransformation
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# Comprendre le retraitement et la retransformation{#understanding-reprocessing-and-retransformation}

{{eol}}

Pendant le retraitement, le serveur Data Workbench reconstruit votre jeu de données comme vous l’avez spécifié dans les fichiers de configuration du jeu de données de traitement et de transformation du journal.

Pour ce faire, le serveur Data Workbench (InsightServer64.exe) doit terminer la phase de traitement des journaux et la phase de transformation de la construction du jeu de données. Une fois le traitement du journal terminé, il déclenche automatiquement la transformation, mais cette dernière peut également s’effectuer indépendamment du traitement du journal.

Pendant la phase de traitement du journal, les utilisateurs de Data Workbench n’ont pas accès aux données du jeu de données. Pendant la phase de transformation, les utilisateurs de Data Workbench n’ont pas accès aux données à jour, mais les données sont échantillonnées au lieu d’être complètes. L’analyse des données peut se poursuivre pendant la transformation, mais les requêtes ne se terminent que aussi rapidement que la transformation se produit.

## Retraitement {#section-92f1e46bf1534b3dba39e9493190b8ab}

Chaque fois que vous effectuez l’une des tâches suivantes, le traitement des journaux et donc la transformation, se produit automatiquement pour reconstruire votre jeu de données comme vous l’avez spécifié dans les fichiers de configuration du jeu de données :

* Ajoutez une nouvelle source de données.
* Ajoutez un nouveau serveur Data Workbench à votre grappe dans le [!DNL Profile.cfg] fichier .
* Modifiez la variable [!DNL Cluster.cfg] fichier .
* Modifiez la variable [!DNL Log Processing.cfg] ou un [!DNL Log Processing Dataset Include] , y compris, mais sans s’y limiter, ce qui suit :

   * Ajouter un nouveau paramètre
   * Modifier une transformation
   * Modification des paramètres Heure de début ou Heure de fin

* Mettez à niveau votre [!DNL Insight Server.exe] fichier .

Vous pouvez également lancer le retraitement à tout moment en saisissant n’importe quel caractère ou combinaison de caractères dans le paramètre Retraiter du [!DNL Log Processing.cfg] et enregistrez le fichier.

>[!NOTE]
>
>Pour que le retraitement se produise, le paramètre Pause dans la variable [!DNL Log Processing Mode.cfg] doit être défini sur false. La valeur par défaut de ce paramètre est false. Il se peut donc que la modification du paramètre ne soit pas requise. Pour plus d’informations sur [!DNL Log Processing Mode.cfg], voir [Fichiers de configuration supplémentaires](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## Retransformation {#section-02446744549940ada8eba0573ec5575f}

Chaque fois que vous modifiez des informations dans la variable [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include] comme modifier une transformation ou définir une nouvelle dimension, la transformation se produit automatiquement.

Chaque fois que vous modifiez les fichiers de recherche référencés dans la variable [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include] (y compris les fichiers de recherche pour [!DNL Categorize], [!DNL FlatFileLookup], et [!DNL ODBCLookup] (transformations), vous devez lancer la transformation en saisissant n’importe quel caractère ou combinaison de caractères dans le paramètre Retraiter du [!DNL Transformation.cfg] et enregistrez le fichier.
