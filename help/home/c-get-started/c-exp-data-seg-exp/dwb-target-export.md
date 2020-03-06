---
description: Exportez les données des outils de données vers Adobe Target à l’aide de TargetBulkUpload.exe à partir du tableau de détails.
title: Exporter vers Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exporter vers Adobe Target{#export-to-adobe-target}

Exportez les données des outils de données vers Adobe Target à l’aide de TargetBulkUpload.exe à partir du tableau de détails.

Les outils de données vous permettent d’exporter des fichiers pour les intégrer à Adobe Target dans le cadre d’un Adobe Experience Cloud intégré.

Le **[!DNL TargetBulkUpload]** fichier se trouve dans le dossier *Server\Scripts* des fichiers d’installation du serveur. Le fichier exécutable comporte une logique de nouvelle tentative, ainsi qu’une logique supplémentaire pour optimiser les performances.

Vous pouvez modifier le `TargetBulkUpload.cfg` fichier et le déplacer vers le dossier *Serveur/Admin/Exporter* avant d’exécuter le script de téléchargement. Vous pouvez, par exemple, définir un intervalle de dépassement de délai maximal de 720 minutes (par défaut) pour que le transfert expire après la période spécifiée.

**Comment ça marche**

Une fois les données envoyées à Target, l’état du téléchargement est surveillé en permanence. Si le transfert réussit, un message de réussite est enregistré. Si le transfert échoue ou est en attente, la surveillance continue. Vous pouvez configurer l’intervalle d’expiration dans le `TargetBulkUpload.cfg` fichier. Si le téléchargement est bloqué dans Target, un message est consigné et l’état peut toujours être surveillé.

Deux fichiers journaux sont générés dans le suivi pour l’exportation déclenchée sous [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

Le `targetbulkuploadexportname.log` fichier a l’état détaillé de tous les enregistrements de plusieurs lots, du serveur Edge auquel il va se rendre et de l’état (réussite, échec, profil introuvable, état inconnu et bloqué). Au cas où un lot se trouverait bloqué, le lot n’est plus traité. Une URL de lot bloquée est disponible pour effectuer le suivi de l’état. Voir les exemples de données suivants du `targetbulkuploadexportname.log.completed` fichier :

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

La valeur d’état de blocage est incrémentée avec la taille totale du lot bloqué, quel que soit le nombre de téléchargements réussis ou ayant échoué. La valeur totale des lignes est également incrémentée du même nombre de tailles de lot bloquées.

>[!NOTE]
>
>Auparavant, les données DWB étaient exportées à l’aide de la [!DNL ExportIntegration.exe]. Actuellement, seules les exportations MMP, CRS et S/FTP sont utilisées avec ce fichier exécutable. L’intégration d’Adobe Target utilise désormais le [!DNL TargetBulkUpload.exe] dans les outils de données.

