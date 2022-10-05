---
description: Procédez comme suit pour effectuer la mise à niveau vers Data Workbench v6.5.
title: Mise à niveau de 6.4 vers 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
exl-id: bcfd1ab1-2fb8-4bcd-b6c9-329143274ca4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 2%

---

# Mise à niveau de 6.4 vers 6.5{#upgrading-to}

{{eol}}

Procédez comme suit pour effectuer la mise à niveau vers Data Workbench v6.5.

## Configuration requise pour la mise à niveau et Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Suivez ces exigences et recommandations lors de la mise à niveau vers Data Workbench 6.5.

* Changements dans le **[!DNL Components for Processing Servers\Communications.cfg]** Vous devez mettre à jour ce fichier pour la version DWB 6.5. Le *SourceListServer*, *SegmentExportServer*, et *NormalizeServer* les entrées ont été supprimées. (Les DPU ne doivent pas être en cours d’exécution *sourcelist*, *exportation de segments* ou *normalisation des serveurs*. )

* Les visualisations Corrélation, Corrélation, Corrélation, Corrélation, Matrice d’association, Score de propension et Attribution de l’ajustement sont désormais des visualisations à plusieurs passages.

   Lorsqu’un espace de travail comporte plusieurs visualisations à plusieurs passages, le serveur de rapports ne parvient pas à générer les rapports par défaut avec l’erreur :

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   Évitez cette erreur en mettant à jour votre [!DNL ReportServer.cfg] ou ajoutez cette ligne à votre fichier existant dans le *Reporting* .

   ```
   Max Multipass Per Slice = int: n
   ```

   où n représente le nombre maximal de visualisations à plusieurs passages prises en charge par le serveur de rapports dans un espace de travail.
