---
description: Mise à niveau des composants du serveur pour Data Workbench 6.3.
title: Mise à niveau du serveur DWB 6.2 vers 6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
exl-id: 5106d9a3-179a-49f1-915a-c03b36ed5257
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Mise à niveau du serveur DWB : 6.2 vers 6.3{#dwb-server-upgrade-to}

{{eol}}

Mise à niveau des composants du serveur pour Data Workbench 6.3.

**Serveur de mise à niveau**

Si vous disposez de profils personnalisés prioritaires sur les fichiers par défaut fournis dans la variable [!DNL Base] , puis vous devez mettre à jour ces fichiers personnalisés :

* **Mise à jour du fichier Meta.cfg** ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]pour définir un chiffrement de mot de passe mis à jour pour l’unité de système de fichiers (serveur FSU) et ajouter des entrées pour les transformations de paires de valeurs de nom afin de tirer parti des [Regroupements de chaînes de requête](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0).

   1. Ouvrez le [!DNL meta.cfg] sur le FSU.
   1. Modification du type de données pour **[!UICONTROL Proxy Password]** de [!DNL string"] à &quot; [!DNL EncryptedString]&quot; dans la variable *Configuration de la station de travail* .

      ```
        Proxy User Name = string:
        Proxy Password = EncryptedString:   (
        from Proxy Password = String)
        Use Address File = bool: true
      ```

   1. Ajoutez de nouvelles entrées pour activer les nouvelles transformations Nom Value Pair : *BuildNameValuePair* et *ExtractNameValuePairs*.

      Ouvrez un espace de travail et cliquez avec le bouton droit de la souris. **Administration** > **Gestionnaire de profil**.

      Sous **Contexte**, cliquez sur le bouton **meta.cfg** dans le fichier **Base** puis cliquez sur **Rendre local**. Dans la colonne Tableau des utilisateurs , cliquez avec le bouton droit de la souris et sélectionnez **Ouvrir** > **dans Workstation**.

      ![](assets/meta_cfg.png)

      * Dans la nouvelle fenêtre, cliquez sur **metadata** et ajoutez des modèles enfants acceptables.

         ![](assets/meta_cfg_child.png)

      * Ouvrir **transformation** et ajoutez de nouveaux modèles.

         ![](assets/meta_cfg_template.png)

* **Mise à jour pour les améliorations de la fusion rapide**. Ajoutez des paramètres ou modifiez des valeurs dans les fichiers de configuration suivants afin de tirer parti des améliorations de vitesse dans Data Workbench lors d’une transformation.

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
   >Pour tirer parti des améliorations apportées à la fusion rapide, vérifiez que vous disposez d’au moins 8 Go de RAM par DPU.

* **Mise à jour de l’intégration Adobe Target avec DWB**. un nouveau fichier d&#39;export, [!DNL ExportIntegration.exe], remplace le [!DNL TnTSend.exe] sur le serveur Insight (`E:\Server\Scripts\TnTSend.exe`). Ce nouveau fichier d’exportation prend en charge les deux [Adobe Target](https://www.adobe.com/marketing/target.html) intégration et coordination avec le nouveau profil marketing de Principal (MMP) et [Adobe Audience Manager](https://www.adobe.com/analytics/audience-manager.html).

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
   * Modification de l’ancienne exportation de Test&amp;Target trouvée dans [!DNL Server/Profiles/`<your profile>`/Exporter.]

* **Mettez à jour le profil Adobe SC.** Modifications apportées au [!DNL Exclude Hit.cfg] Un champ doit être déclaré dans le fichier associé. [!DNL Decoding Instructions.cfg] fichier .

   >[!NOTE]
   >
   >Si votre profil SC d’Adobe comprend une [!DNL Decoding Instructions.cfg] , vous devez inclure une [!DNL DelimitedDecoder] du fichier personnalisé.

   ```
   0 = DelimitedDecoder:
      Delimiter = string: \t
      Fields = vector: x items
      …
         5 = string:
   Changed to:
   
   5 = string: x-hit_source
   ```

   Ajouter le [!DNL DelimitedDecoder] vous permet de tirer parti des mises à jour des fonctionnalités et d’éviter les éventuels problèmes de traitement des journaux résultant de ces mises à jour.
