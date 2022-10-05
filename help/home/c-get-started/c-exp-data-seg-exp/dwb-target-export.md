---
description: Exportez des données de Data Workbench vers Adobe Target à l’aide de TargetBulkUpload.exe dans le tableau détaillé.
title: Exportation vers Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
exl-id: 41e885bb-182a-4983-98e8-65eec1da9fe9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# Exportation vers Adobe Target{#export-to-adobe-target}

{{eol}}

Exportez des données de Data Workbench vers Adobe Target à l’aide de TargetBulkUpload.exe dans le tableau détaillé.

Data Workbench vous permet d’exporter des fichiers à intégrer à Adobe Target dans le cadre d’un Adobe Experience Cloud intégré.

Le **[!DNL TargetBulkUpload]** se trouve dans la variable *Server\Scripts* dans les fichiers d’installation du serveur. Le fichier exécutable possède une logique de reprise, ainsi qu’une logique supplémentaire pour optimiser les performances.

Vous pouvez modifier la variable `TargetBulkUpload.cfg` et déplacez-le vers *Serveur/Admin/Exportation* avant d’exécuter le script de chargement. Par exemple, vous pouvez définir un intervalle de temporisation maximal sur 720 minutes (par défaut) pour que le téléchargement expire après la période spécifiée.

**Fonctionnement**

Une fois les données envoyées à Target, l’état du chargement est surveillé en permanence. Si le chargement réussit, un message de réussite est consigné. Si le chargement échoue ou est en attente, la surveillance continue. Vous pouvez configurer l’intervalle d’expiration dans la variable `TargetBulkUpload.cfg` fichier . Si le chargement est bloqué sur Target, un message est consigné et l’état peut toujours être surveillé.

Deux fichiers journaux sont générés dans la trace pour l’exportation déclenchée sous [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

Le `targetbulkuploadexportname.log` a l’état détaillé de tous les enregistrements de plusieurs lots, du serveur Edge vers lequel ils se rendent et de l’état (réussi, échec, profil introuvable, statut inconnu et bloqué). Si un lot se trouve bloqué, il n’est plus traité. Une URL de lot bloquée est disponible pour effectuer le suivi de l’état. Consultez les exemples de données suivants provenant de la variable `targetbulkuploadexportname.log.completed` fichier :

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

La valeur d’état de blocage est incrémentée avec la taille totale du lot bloqué, quel que soit le nombre de chargements réussis ou échoués. La valeur totale des lignes est également incrémentée par le même nombre de chaînes de la taille du lot bloqué.

>[!NOTE]
>
>Auparavant, les données DWB étaient exportées à l’aide de la variable [!DNL ExportIntegration.exe]. Actuellement, seules les exportations MMP, CRS et S/FTP sont utilisées avec ce fichier exécutable. L’intégration d’Adobe Target utilise désormais le [!DNL TargetBulkUpload.exe] en Data Workbench.
