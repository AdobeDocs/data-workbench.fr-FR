---
description: Mise à niveau des composants de serveur pour les outils de données 6.3.
title: DWB Server version 6.2 à 6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
translation-type: tm+mt
source-git-commit: 79d5a2f44ade88f25f7621a4738d14c43777fc9f

---


# Mise à niveau du serveur DWB : 6.2 à 6.3{#dwb-server-upgrade-to}

Mise à niveau des composants de serveur pour les outils de données 6.3.

**Serveur de mise à niveau**

Si vous avez des  personnalisées qui ont priorité sur les fichiers par défaut fournis dans le [!DNL Base] pack, vous devez mettre à jour ces fichiers personnalisés :

* **Mettez à jour le fichier** Meta.cfg ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]pour définir le chiffrement du mot de passe mis à jour pour l’unité du système de fichiers (serveur FSU), et ajoutez des entrées pour les transformations de paires de valeurs de nom afin de tirer parti des regroupements [de chaînes de ](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0).

   1. Ouvrez le [!DNL meta.cfg] fichier sur le FSU.
   1. Remplacez le type de données **[!UICONTROL Proxy Password]** de &quot; [!DNL string"] par &quot; [!DNL EncryptedString]&quot; dans la section Configuration *de* la station de travail.

      ```
        Proxy User Name = string: 
        Proxy Password = EncryptedString:   ( 
        from Proxy Password = String) 
        Use Address File = bool: true
      ```

   1. Ajouter nouvelles entrées pour activer les nouvelles transformations des paires de valeurs de nom : *BuildNameValuePair* et *ExtractNameValuePairs*.

      Ouvrez un espace de travail et cliquez avec le bouton droit de la souris sur **Admin** > Gestionnaire de ****.

      Sous **Contexte**, cliquez sur le fichier **meta.cfg** dans la colonne **Base** , puis cliquez sur **Rendre local.** Dans la colonne du tableau Utilisateur, cliquez avec le bouton droit de la souris et sélectionnez **Ouvrir** > **dans Workstation**.

      ![](assets/meta_cfg.png)

      * Dans la nouvelle fenêtre, cliquez sur **Métadonnées** et ajoutez des modèles enfants acceptables.

         ![](assets/meta_cfg_child.png)

      * Ouvrez **la transformation** et ajoutez de nouveaux modèles.

         ![](assets/meta_cfg_template.png)

* **Mise à jour pour les améliorations** de la fusion rapide. Ajouter des paramètres ou modifiez les valeurs dans les fichiers de configuration suivants pour tirer parti des améliorations de vitesse dans les Outils de données lors d’une transformation.

   * **Communications.cfg** ( [!DNL E:\Server\Components\Communications.cfg])

      ```
      18 = SourceListServer:  
          URI = string: /SourceListServer/ 
          Listing Interval = int: 10 ( 
      <new>)
      ```

   * **Disk Files.cfg** (at [!DNL E:\Server\Components] et [!DNL E:\Server\Components for Processing Servers])

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
   >Pour tirer parti des améliorations apportées à la fusion rapide, assurez-vous d’avoir au moins 8 Go de mémoire vive par unité de traitement (DPU).

* **Adobe avec mise à jour** de l’intégration DWB. Un nouveau fichier d’exportation [!DNL ExportIntegration.exe]remplace le [!DNL TnTSend.exe] fichier existant sur le serveur Insight (`E:\Server\Scripts\TnTSend.exe`). Ce nouveau fichier d’exportation prend en charge à la fois l’intégration [d’](https://www.adobe.com/marketing/target.html) Adobe et la coordination avec le nouvel  MMP (Master Marketing) et le Gestionnaire [de](https://www.adobe.com/analytics/audience-manager.html)Adobe.

   Vous devrez mettre à jour les commandes suivantes pour les exportations de  Adobe.

   `Command = string: TnTSend.exe`

   sur 

   ```
   <filepath>
   Command = string: ExportIntegration.exe 
   </filepath>
   ```

   >[!NOTE]
   >
   >Cela affectera uniquement les exportations créées avant la version 6.3.

   Vous pouvez également utiliser l’ancien processus d’exportation comme suit :

   * Créez un nouveau test et une nouvelle exportation  dans le poste de travail.
   * Modifiez l&#39;ancienne exportation Test et trouvée dans [!DNL Server/Profiles/`<your profile>`/Exportation.]

* **Mettez à jour le Adobe SC.** Les modifications apportées au [!DNL Exclude Hit.cfg] fichier nécessitent qu’un champ soit déclaré dans le [!DNL Decoding Instructions.cfg] fichier associé.

   >[!NOTE]
   >
   >Si votre Adobe SC  inclut un [!DNL Decoding Instructions.cfg] fichier personnalisé, vous devez inclure un [!DNL DelimitedDecoder] paramètre dans votre fichier personnalisé.

   ```
   0 = DelimitedDecoder: 
      Delimiter = string: \t 
      Fields = vector: x items 
      …  
         5 = string: 
   Changed to: 
   
   5 = string: x-hit_source
   ```

   L’ajout du [!DNL DelimitedDecoder] champ vous permet de tirer parti des mises à jour des fonctionnalités et d’éviter les problèmes éventuels de traitement du journal résultant de ces mises à jour.
