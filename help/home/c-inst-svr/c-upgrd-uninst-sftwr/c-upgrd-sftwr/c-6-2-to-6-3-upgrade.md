---
description: Mise à niveau des composants du serveur pour Data Workbench 6.3.
title: Mise à niveau du serveur DWB 6.2 vers 6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
exl-id: 5106d9a3-179a-49f1-915a-c03b36ed5257
source-git-commit: b21da6d12175fa8570b1b366049baa9c8e8ea862
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Mise à niveau du serveur DWB : 6.2 vers 6.3{#dwb-server-upgrade-to}

Mise à niveau des composants du serveur pour Data Workbench 6.3.

**Serveur de mise à niveau**

Si vous disposez de profils personnalisés prioritaires sur les fichiers par défaut fournis dans le package [!DNL Base], vous devez mettre à jour ces fichiers personnalisés :

* **Mettez à jour le fichier Meta.cfg** (  [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]pour définir un chiffrement de mot de passe mis à jour pour l’unité du système de fichiers (serveur FSU) et ajouter des entrées pour les transformations Name Value Pair afin de tirer parti des  [regroupements de chaînes de requête](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0).

   1. Ouvrez le fichier [!DNL meta.cfg] sur le FSU.
   1. Remplacez le type de données **[!UICONTROL Proxy Password]** par &quot;[!DNL string"]&quot; dans la section *Configuration de la station de travail*.[!DNL EncryptedString]

      ```
        Proxy User Name = string:
        Proxy Password = EncryptedString:   (
        from Proxy Password = String)
        Use Address File = bool: true
      ```

   1. Ajoutez de nouvelles entrées pour activer les nouvelles transformations Nom Value Pair : *BuildNameValuePair* et *ExtractNameValuePairs*.

      Ouvrez un espace de travail et cliquez avec le bouton droit de la souris sur **Admin** > **Gestionnaire de profils**.

      Sous **Contexte**, cliquez sur le fichier **meta.cfg** dans la colonne **Base**, puis cliquez sur **Créer local**. Dans la colonne Table des utilisateurs , cliquez avec le bouton droit et sélectionnez **Ouvrir** > **dans la station de travail**.

      ![](assets/meta_cfg.png)

      * Dans la nouvelle fenêtre, cliquez sur **metadata** et ajoutez des modèles enfants acceptables.

         ![](assets/meta_cfg_child.png)

      * Ouvrez **transformation** et ajoutez de nouveaux modèles.

         ![](assets/meta_cfg_template.png)

* **Mise à jour pour les améliorations** de la fusion rapide. Ajoutez des paramètres ou modifiez des valeurs dans les fichiers de configuration suivants afin de tirer parti des améliorations de vitesse dans Data Workbench lors d’une transformation.

   * **Communications.cfg** (  [!DNL E:\Server\Components\Communications.cfg])

      ```
      18 = SourceListServer:
          URI = string: /SourceListServer/
          Listing Interval = int: 10 (
      <new>)
      ```

   * **Disk Files.cfg**  (à l’adresse  [!DNL E:\Server\Components] et  [!DNL E:\Server\Components for Processing Servers])

      ```
      Disk Cache Size (MB) = double: 1024
      <(from double: 256)>
      Disk Cache Read Limit (MB) = double: 768
      <(new)>
      ```

   * **Mode de traitement du journal.cfg** ( [!DNL E:\Server\Profiles\<your profile>\Dataset\Log Processing Mode.cfg])

      ```
      <(changed)
      Batch Bytes = int: 268435456
      Cloud Bytes = int: 268435456
      Real Time FIFO Bytes = int: 268435456
      ```

      ```
      (
      <new>)
      Cache Bytes = int: 32000000
      Fast Input Decision Ratio = double: 200
      Fast Input FIFO Bytes = int: 268435456
      FIFO Hash Mask = int: 16383
      Fast Merge Buffer Bytes = int: 536870912
      Slow Merge Buffer Bytes = int: 268435456
      Fast Merge Fan In = int: 64
      Key Cache Size Logarithm = int: 21
      Max Seeks = int: 512
      Output Old Buffer Bytes = int: 536870912
      Overflow FIFO Bytes = int: 67108864
      Paused = bool: false
      ```
   >[!NOTE]
   >
   >Pour tirer parti des améliorations apportées à la fusion rapide, vérifiez que vous disposez d’au moins 8 Go de RAM par DPU.

* **Mise à jour de l’intégration Adobe Target avec DWB**. Un nouveau fichier d’exportation, [!DNL ExportIntegration.exe], remplace le fichier [!DNL TnTSend.exe] existant sur le serveur Insight (`E:\Server\Scripts\TnTSend.exe`). Ce nouveau fichier d’exportation prend en charge l’intégration [Adobe Target](https://www.adobe.com/marketing/target.html) et la coordination avec le nouveau profil marketing de Principal (MMP) et [Adobe Audience Manager](https://www.adobe.com/analytics/audience-manager.html).

   Vous devrez mettre à jour les commandes suivantes pour les exports Adobe Target.

   `Command = string: TnTSend.exe`

   sur 

   ```
   <filepath>
   Command = string: ExportIntegration.exe
   </filepath>
   ```

   >[!NOTE]
   >
   >Cela affecte uniquement les exportations créées avant la version 6.3.

   Vous pouvez également essayer les méthodes suivantes pour utiliser l’ancien processus d’exportation :

   * Créez une nouvelle exportation Test&amp;Target dans le poste de travail.
   * Modifiez l’ancien export Test and Target trouvé dans [!DNL Server/Profiles/`<your profile>`/Export.]

* **Mettez à jour le profil Adobe SC.** Les modifications apportées au  [!DNL Exclude Hit.cfg] fichier nécessitent qu’un champ soit déclaré dans le  [!DNL Decoding Instructions.cfg] fichier associé.

   >[!NOTE]
   >
   >Si votre profil SC d’Adobe comprend un fichier [!DNL Decoding Instructions.cfg] personnalisé, vous devrez inclure un paramètre [!DNL DelimitedDecoder] à votre fichier personnalisé.

   ```
   0 = DelimitedDecoder:
      Delimiter = string: \t
      Fields = vector: x items
      …
         5 = string:
   Changed to:
   
   5 = string: x-hit_source
   ```

   L’ajout du champ [!DNL DelimitedDecoder] vous permet de tirer parti des mises à jour de fonctionnalités et d’éviter les éventuels problèmes de traitement des logs résultant de ces mises à jour.
