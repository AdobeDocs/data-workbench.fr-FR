---
description: Vous pouvez facilement créer une définition d’exportation de segment à partir de la visualisation Tableau des détails dans le client Outils de données.
solution: Analytics
title: Exportation de segments
topic: Data workbench
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Segment export{#segment-export}

Vous pouvez facilement créer une définition d’exportation de segment à partir de la visualisation Tableau des détails dans le client Outils de données.

En outre, [!DNL Segment Exports] combinez automatiquement leurs résultats à un seul serveur, plutôt que de produire des résultats partiels sur chaque unité de traitement de données que vous devez combiner à l’aide d’un processus externe. Vous pouvez créer un fichier d’exportation de segments, l’enregistrer dans le fichier [!DNL Profile Manager]et télécharger le fichier de sortie sur un serveur de votre choix.

**Pour configurer le serveur d’exportation de segments**

La [!DNL Segment Export] fonctionnalité crée un fichier de sortie unique sur le serveur d’exportation de segments, plutôt que des fichiers de sortie distincts créés sur chaque unité de traitement de données. Le serveur d’exportation de segments est généralement configuré pour s’exécuter sur le FSU.

Dans le répertoire Dataset\ du [!DNL Profile Manager], ouvrez [!DNL Segment Export.cfg] dans Workstation, puis indiquez l’adresse de votre serveur. (Votre adresse peut être une adresse IP ou un nom de domaine complet.) :

![](assets/segment_export_cfg.png)

Il s’agit de l’adresse IP du serveur Outils de données qui reçoit les résultats de l’exportation de segments. C&#39;est une configuration unique. Si la variable [!DNL Segment Export.cfg] n’est pas présente, les exportations ne s’exécutent pas.

**Pour configurer les répertoires d’exportation**

Pour des raisons de sécurité, les fichiers exécutables ou par lots qui s’exécutent après une exportation de segment doivent résider dans le répertoire Scripts\ configurables du serveur d’exportation de segments.

La sortie [!DNL .part] et finale doit résider dans le répertoire Exportations configurable. La commande à exécuter existe dans les arguments Commande et Commande. Les instances du fichier %file% dans les arguments de commande seront remplacées par le chemin du fichier de sortie.

>[!NOTE]
>
>Nouveau dans Outils de données version 5.4, le dossier \Exports est créé automatiquement. Les répertoires d’exportation précédents configurés avant la version 5.4 nécessitaient un préfixe Exports\ avant le nom de fichier pour chaque exportation de segment. L’ajout de ce préfixe est désormais redondant.

1. Dans [!DNL Communications.cfg] le serveur de destination pour [!DNL Segment Exports], ajoutez un serveur SegmentExportServer à la liste des serveurs. (Exemple illustré en rouge).

   ![](assets/communications_cfg_example.png)

   Exporte le répertoire : Indique l’emplacement des fichiers de sortie [!DNL .part] et de placement. Il peut s’agir d’un répertoire partagé.

   Répertoire des scripts : Indique le répertoire d’exécution de tous les fichiers exécutables ou par lot.

1. [!DNL Access Control.cfg], sur le même serveur, ajoutez l’accès en lecture-écriture à l’URI /SegmentExportServer/ au Groupe d’accès des serveurs de cluster :

   ![](assets/accesscontrol_cfg_example.png)

1. Modifiez vos [!DNL .export] fichiers :

   ![](assets/segment_export_query_example.png)

1. Pour chaque profil, le [!DNL Segment Export.cfg] répertoire se trouve dans le répertoire Dataset\, avec le contenu suivant :

   ```
   Segment Export = SegmentExport:
   Segment Export Server = serverInfo:
   Port = int: 80
   Address = string: 192.168.5.128 (for example) Use SSL = bool: false
   ```

1. Assurez-vous que les répertoires auxquels il est fait référence dans Exports Directory et Scripts Directory existent.

   Seuls les fichiers exécutables et par lot du répertoire Scripts peuvent être exécutés comme commande d’une exportation de segment.

**Pour créer un fichier d’exportation de segment**

1. Dans un espace de travail, créez un tableau détaillé présentant des sous-ensembles de données (Visualisation > Tableau des détails) et ajoutez des attributs.
1. Si vous le souhaitez, effectuez des sélections dans l’espace de travail. (Toute sélection ou filtre est appliquée à l’exportation.)

   ![](assets/create_segment_export_file.png)

1. Dans l’en-tête Tableau des détails, cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Create Segment Export File]**.
1. Dans [!DNL Save as], saisissez le nom du [!DNL .export] fichier.
1. Dans le [!DNL .export] fichier, configurez les paramètres selon vos besoins.

   Toutes les sélections ou tous les filtres de l’espace de travail sont incorporés dans le fichier d’exportation.

1. Save the [!DNL .export] file.

   Le fichier enregistré s’affiche dans la [!DNL Profile Manager] boîte de dialogue pour que vous puissiez l’enregistrer sur le serveur. Lorsque vous enregistrez le fichier sur le serveur, l’exportation commence.

