---
description: Procédez comme suit pour effectuer la mise à niveau vers Outils de données v6.5.
title: Mise à niveau 6.4 vers 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Upgrading 6.4 to 6.5{#upgrading-to}

Procédez comme suit pour effectuer la mise à niveau vers Outils de données v6.5.

## Configuration requise et recommandations pour la mise à niveau {#section-8704a9ac358246cd81233dd0982d534f}

Suivez ces exigences et recommandations lors de la mise à niveau vers Outils de données 6.5.

* Les modifications apportées au **[!DNL Components for Processing Servers\Communications.cfg]** fichier nécessitent que vous mettiez à jour ce fichier pour la version DWB 6.5. Les entrées *SourceListServer*, *SegmentExportServer* et *NormalizeServer* ont été supprimées. (Les unités de traitement de données ne doivent pas exécuter *la liste des fournisseurs*, l’exportation *de* segments ou *normaliser les serveurs*. )

* Les visualisations Correlation Chord, Correlation Matrix, Association Chord, Association Matrix, Propensity Score et Best Fit Attribution sont désormais des visualisations à plusieurs passes.

   S’il existe plusieurs visualisations à plusieurs passes dans un espace de travail, le serveur de rapports ne parvient pas à générer des rapports par défaut avec l’erreur :

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   Evitez cette erreur en mettant à jour votre [!DNL ReportServer.cfg] fichier ou en ajoutant cette ligne à votre fichier existant dans la section *Création de rapports* .

   ```
   Max Multipass Per Slice = int: n
   ```

   où n correspond au nombre maximal de visualisations à plusieurs passes prises en charge par le serveur de rapports dans un espace de travail.

